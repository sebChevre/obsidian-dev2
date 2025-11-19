---
created: 2025-11-19 - 16:10
tags:
  - documentation
---
Je vais décortiquer ton workflow n8n et te pointer les endroits importants / fragiles, surtout autour de la mémoire et du RAG.

Je reste dans ton vocabulaire (chat_memory, Obsidian, etc.).

---

## 1. Vue d’ensemble de ce que fait le flux

En gros, ton workflow fait :

1. **Réception d’un message** via `chatMessage` (Chat Trigger LangChain).
    
2. **Gestion de la session de chat** (table `chat_memory`) :
    
    - S’il n’y a pas de session active → en crée une.
        
    - Si l’utilisateur tape _"reset" / "nouvelle conversation" / etc._ → désactive la session et en crée une nouvelle.
        
    - Sinon → réutilise la session active.
        
3. **Récupère l’historique** de la conversation dans `chat_message` pour cette session.
    
4. **Fait une recherche sémantique** dans la table `documents` (RAG) à partir de la question utilisateur.
    
5. **Construit un gros prompt** avec :
    
    - Les docs trouvés.
        
    - Les chemins/sources Obsidian.
        
    - L’historique de la conversation.
        
    - Des instructions strictes pour le mode “assistant documentaire”.
        
6. **Appelle le modèle `gemma3n`** via `/chat/completions`.
    
7. **Enregistre le message user + la réponse assistant** dans `chat_message`.
    
8. **Répond au chat** avec le markdown du modèle.
    

Globalement : c’est un **chat RAG avec mémoire multi-tours** stockée en Postgres. 👍

---

## 2. La partie “mémoire de chat” (chat_memory / chat_message)

### a) Récupération ou création de la session

- `getChatMemory`
    
    ```sql
    SELECT id,session_id
    FROM chat_memory 
    WHERE isactive = TRUE;
    ```
    
- `isSessionsToBeInitiated`  
    Teste : _y a-t-il une ligne active ?_
    
    - **SI aucune session active** → va vers `initFirstSession`
        
    - **SINON** → va directement vers `newConversationFromPrompt`
        
- `initFirstSession`
    
    ```sql
    INSERT INTO chat_memory DEFAULT VALUES
    RETURNING id, session_id;
    ```
    
    → crée la toute première session.
    

### b) Reset sur commande utilisateur

- `newConversationFromPrompt` (IF) regarde le texte exact de `userQuery` :
    
    - `"lance une nouvelle conversation"`
        
    - `"nouvelle discussion"`
        
    - `"nouvelle conversation"`
        
    - `"reset"`
        
    - **SI la condition est vraie** → branche 1 :  
        `newSessionMemory` :
        
        ```sql
        UPDATE chat_memory SET isactive = FALSE;
        
        INSERT INTO chat_memory DEFAULT VALUES
        RETURNING id, session_id;
        ```
        
        Puis `Respond to Chat1` :
        
        > "Ok, je vais démarrer une nouvelle conversation, j'attends votre question"
        
    - **SI la condition est fausse** → branche 2 :  
        `setCurrentConversation` (c’est là qu’on choisit la session à utiliser).
        

### c) Set de la conversation actuelle

- `setCurrentConversation`
    
    - prend soit :
        
        - l’`id` renvoyé par `initFirstSession` / `newSessionMemory`
            
        - soit l’`id` de `getChatMemory` (si une session active existe déjà)
            
    
    ```js
    id: "={{ $json.chat_memory_id || $json.id   }}"
    ```
    

C’est cet `id` qui sert ensuite partout :

- `getMemoryMessages`
    
- `insertUserChatMessages`
    
- `insertAssistantChatMessage`
    

### d) Historique des messages

- `getMemoryMessages`
    
    ```sql
    SELECT * from chat_message 
    WHERE chat_memory_id = {{ $('setCurrentConversation').first().json.id }}
    ORDER BY created_at ASC;
    ```
    
- Dans `prepareBodyCompletion`, tu reconstruis la liste de messages pour l’API :
    
    ```js
    const messagesList = $items("getMemoryMessages");
    
    const messages = (messagesList && messagesList.some(i => i.json && Object.keys(i.json).length))
      ? messagesList.map(i => ({
          role: i.json.role,
          content: i.json.content
        }))
      : [];
    ```
    

Puis tu ajoutes un _dernier message user_ contenant le gros prompt RAG construit.

---

## 3. La partie RAG (embedding + Postgres + prompt)

### a) Embedding de la question

- `setUserQuery`
    
    ```js
    {
      "userQuery": {{ JSON.stringify($json.chatInput) }}
    }
    ```
    
- `embeddingUserQuery` : POST vers `/embeddings` avec :
    
    ```json
    {
      "model": "bge_multilingual_gemma2",
      "input": "<userQuery>"
    }
    ```
    

### b) Recherche sémantique Postgres

- `semanticSearch`
    
    ```sql
    SELECT id, content, obsidian_path, file_name
    FROM documents
    ORDER BY embedding <=> '[{{ $('embeddingUserQuery').item.json.data[0].embedding }}]'
    LIMIT 5;
    ```
    

Donc `documents.embedding` est un `vector`, et tu uses l’opérateur `<=>` pour la distance.

### c) Ré-embedding des documents (potentiellement inutile)

Tu fais ensuite :

- `jsonifyText` → garde `content`, `obsidian_path`, `file_name`
    
- `prepareBody` → prépare le corps pour un **nouvel appel d’embedding** des docs :
    
    ```js
    body: {
      model: "bge_multilingual_gemma2",
      input: i.json.content
    }
    ```
    
- `embeddingDocuments` → POST embeddings pour _chaque_ document.
    
- `formatObjects` :
    
    ```js
    const docs = items.map((item, idx) => {
      const embeddingData = $items("embeddingDocuments")[idx].json.data[0].embedding;
    
      return {
        content: $items('jsonifyText')[idx].json.content,
        obsidian_path: $items('jsonifyText')[idx].json.obsidian_path,
        file_name: $items('jsonifyText')[idx].json.file_name,
        embedding: embeddingData
      };
    });
    ```
    

⚠️ Mais ensuite, tu n’utilises **que `content`, `obsidian_path`, `file_name`** pour le prompt, pas les embeddings recalculés. Donc cet appel d’embedding est redondant (à moins que tu comptes les exploiter plus tard pour du reranking custom).

### d) Construction du prompt RAG

Dans `prepareBodyCompletion` :

- Concaténation des contenus :
    
    ```js
    const aggregatedDocs = $('formatObjects').first().json.docs
      .map(i => i.content)
      .join("\n\n");
    
    const aggregatedSources = $('formatObjects').first().json.docs
      .map(i => `- ${i.obsidian_path}/${i.file_name}`)
      .join("\n");
    ```
    
- Tu construis ensuite un méga prompt :
    
    - Règles : ne répondre qu’avec le contexte, pas de devinettes, mentionner si info hors contexte, etc.
        
    - Contexte = `aggregatedDocs`
        
    - Sources = `aggregatedSources`
        
    - Historique formaté en texte simple :
        
        ```js
        const formattedHistory = messages
          .map(m => `${m.role.toUpperCase()}: ${m.content}`)
          .join("\n");
        ```
        
    - Question courante = `question`
        
- Puis tu ajoutes ce prompt comme **dernier message de rôle `user`** :
    
    ```js
    messages.push({
      role: "user",
      content: content
    });
    ```
    
- Et tu appelles `/chat/completions` avec :
    
    ```json
    {
      "model": "gemma3n",
      "n": 1,
      "temperature": 0.5,
      "messages": messages
    }
    ```
    

---

## 4. Enregistrement des messages

Après `callCompletion` :

- `insertUserChatMessages` :
    
    ```sql
    INSERT INTO chat_message (chat_memory_id, role, content)
    VALUES ($1, $2, $3)
    ```
    
    avec :
    
    ```js
    queryReplacement = "=[{{ $('setCurrentConversation').first().json.id }},{{\"user\"}},\"{{$('setUserQuery').first().json.userQuery}}\"]"
    ```
    
- `insertAssistantChatMessage` :
    
    ```sql
    INSERT INTO chat_message (chat_memory_id, role, content)
    VALUES ($1, $2, $3)
    ```
    
    avec :
    
    ```js
    queryReplacement =
      "=[{{ $('setCurrentConversation').first().json.id }},\"{{ $('callCompletion').item.json.choices[0].message.role }}\",\"{{ $('callCompletion').item.json.choices[0].message.content }}\"]"
    ```
    

Puis `Code in JavaScript` récupère la réponse pour la renvoyer au chat.

---

## 5. Points fragiles / bugs potentiels

### 5.1. Propriété `source` dans `Code in JavaScript`

```js
const source = $node["setUserQuery"].json["source"];
```

- Dans `setUserQuery`, tu ne définis **pas** de champ `source`. Résultat → `source` sera `undefined`.
    
- Si tu n’en as pas besoin : supprime ces lignes / ce champ.
    
- Si tu veux distinguer la source (web, interne, etc.), il faut l’ajouter dès le `chatTrigger` ou dans `setUserQuery`.
    

---

### 5.2. Embeddings des documents recalculés pour rien

Tu appelles `/embeddings` deux fois :

1. Pour la _question utilisateur_ (ok).
    
2. Pour les _documents retournés par Postgres_, mais tu ne réutilises pas ces embeddings.
    

✅ Propositions :

- soit tu vires `prepareBody` → `embeddingDocuments` → `formatObjects` et tu passes directement de `semanticSearch` → `jsonifyText` → `prepareBodyCompletion`.
    
- soit tu gardes ces embeddings pour :
    
    - un **reranking custom** (cosine entre doc & question),
        
    - ou pour **stocker les nouveaux embeddings dans la DB** (mais là tu ne fais aucun UPDATE).
        

---

### 5.3. Matching exact des phrases de reset

`newConversationFromPrompt` teste des **égalité exactes** :

```js
"lance une nouvelle conversation"
"nouvelle discussion"
"nouvelle conversation"
"reset"
```

Donc :

- `"reset "` (avec un espace), `"Reset"`, `"reset la conversation"`, etc. ne fonctionneront pas.
    

✅ Amélioration possible (logique côté n8n) :

- Passer la `userQuery` en minuscules avant (dans `setUserQuery`).
    
- Utiliser un `contains` ou une regex dans les conditions.
    

---

### 5.4. Risque d’échappement de guillemets dans `queryReplacement`

Tu fais des choses de ce style :

```js
"=[{{ $('setCurrentConversation').first().json.id }},\"{{ $('callCompletion').item.json.choices[0].message.role }}\",\"{{ $('callCompletion').item.json.choices[0].message.content }}\"]"
```

Si `content` contient des guillemets `"` ou des retours ligne, tu peux casser le SQL.

✅ Plus robuste :

- Utiliser les **paramètres** natifs (placeholder `$1,$2,$3`) et laisser `queryReplacement` générer un tableau JSON simple, ou
    
- encodeURIComponent / JSON.stringify autour du content, ou
    
- stocker le JSON entier du message si besoin.
    

---

### 5.5. Historique potentiellement très long

Tu passes **toute** l’historique dans `messages` :

```js
SELECT * from chat_message ... ORDER BY created_at ASC;
```

Au bout d’un moment la requête `/chat/completions` va être :

- plus chère,
    
- plus lente,
    
- et potentiellement au-delà du contexte max.
    

✅ Idée simple : dans `getMemoryMessages`, limiter aux N derniers messages :

```sql
... 
ORDER BY created_at DESC
LIMIT 20;
```

Puis si tu veux l’ordre croissant, tu peux faire une sous-requête / réordonner côté JS.

---

## 6. Prochaines améliorations possibles

Sans changer ta logique métier, voilà ce que je ferais dans une “v2” :

1. **Supprimer les embeddings docs inutilisés** (ou les exploiter vraiment pour du reranking).
    
2. **Ajouter un `LIMIT` sur l’historique** dans `getMemoryMessages`.
    
3. **Rendre le reset plus tolérant** :
    
    - passer en lower-case la question dans `setUserQuery` ;
        
    - utiliser `contains` sur "reset", "nouvelle conversation".
        
4. **Corriger / utiliser le champ `source`** dans `Code in JavaScript`.
    
5. **Sécuriser l’INSERT des messages** (gérer guillemets / caractères spéciaux) en soignant `queryReplacement`.
    

---

Si tu veux, je peux te proposer une version _nettoyée_ du JSON avec :

- suppression des nodes inutiles,
    
- corrections de code JS dans les nodes `code`,
    
- et un `getMemoryMessages` limité (par ex. 20 derniers messages).