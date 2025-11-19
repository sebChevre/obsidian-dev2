# Office 365, Azure AD, souveraineté : on se trompe de combat (et on adore ça)
*13 novembre 2025*

Je vois encore passer, toutes les semaines, des posts qui nous rejouent le grand classique :  
“Office 365 n’est pas souverain, bannissons Microsoft des entreprises !”  
C’est un peu le niveau “débat de comptoir cyber”, mais version LinkedIn : ça rassure, ça crée de l’engagement, mais ça n’aide personne à comprendre les vrais enjeux.

Parce qu’en réalité, l’équation souveraineté ≠ Office.  
La souveraineté, c’est l’endroit où se trouvent vos dépendances critiques, pas la couleur de votre suite bureautique.

Et, spoiler : si votre SI tombe parce que Word ne se lance plus, ce n’est pas un problème de souveraineté, c’est un problème de management.

Alors remettons l’église, le cloud et le DNS au milieu du village.

---

## 1️⃣ Le vrai cœur du problème : Azure AD / Entra ID, pas Word ni Teams

Soyons sérieux : Word ne va pas se réveiller un matin en transférant vos fichiers aux services de renseignement américains.  
Le problème, c’est Azure AD, devenu la colonne vertébrale de l’IT moderne.

### Pourquoi c’est là que la souveraineté se joue ?

Parce que :

- C’est le centre névralgique de vos identités.
- C’est ce qui donne l’accès à tout : SaaS, VPN, Wi-Fi, MDM, apps internes.
- C’est un point de défaillance unique : si Azure AD tombe, votre SI devient une salle d’attente.
- C’est extraterritorial par design : Cloud Act, FISA 702, Executive Orders… même hébergé en Europe, ça reste américain.
- Vous ne pouvez ni contrôler, ni auditer, ni répliquer totalement Entra ID.

On ne parle pas d’un petit risque.  
On parle d’une dépendance structurelle à un acteur étranger qui contrôle :

- vos identités,
- vos devices,
- vos accès,
- vos workflows d’authentification.

Donc oui : le sujet souveraineté n’est pas Office 365, c’est l’identity plane.  
Et ça, la plupart des débats l’oublient complètement.

---

## 2️⃣ Office 365 : l’arbre qui cache la forêt (et que tout le monde adore couper)

Soyons honnêtes : taper sur Office 365, c’est simple, visible et populaire.  
Les utilisateurs connaissent : Word, Excel, Outlook.  
Donc on se dit “Si on enlève Microsoft Office, on est souverains !”.

C’est mignon, mais… non.

Les vraies dépendances ne sont pas dans Word mais dans :

- OneDrive → stockage dans un cloud américain  
- SharePoint Online → cœur documentaire externalisé  
- Exchange Online → messagerie critique hors-sol  
- Teams → moteur collaboratif branché sur un backend US  
- Graph API → votre SI dépend de la politique produit de Redmond

Tu peux très bien :

- utiliser Outlook on-prem,
- désactiver OneDrive,
- garder les clients Office installés localement,
- filtrer la synchro cloud,
- interdire SharePoint Online,
- forcer le stockage interne.

Et continuer à être souverainement opérationnel.

Le problème n’est pas l’outil, mais l’usage.

Office n’est pas souverain ou non.  
Il est ce que votre gouvernance en fait.

---

## 3️⃣ L’usage de OneDrive : la vraie faille, la vraie dépendance

On parle trop peu de ce point-là :  
OneDrive est souvent LE trou noir de souveraineté dans Microsoft 365.

### Pourquoi ?

- C’est du stockage cloud américain,
- avec de la synchronisation automatique,
- sans traçabilité granulaire réelle côté client,
- sans maîtrise de la fragmentation,
- sous Cloud Act même si c’est “hébergé en Europe”.

Un bon sysadmin :

- désactive le lancement de OneDrive,
- bloque les connexions à onedrive.live.com,
- supprime les policies de synchro automatique,
- impose des stockages locaux, NFS ou SMB,
- met un DLP interne.

Mais ça demande une maturité technique *et* une volonté politique.  
Les deux manquent souvent.

---

## 4️⃣ Sortir d’Office : facile techniquement, très compliqué humainement

On peut sortir d’Office.  
Techniquement, c’est même relativement simple :

- LibreOffice → suite lourde mais robuste,
- OnlyOffice → meilleur pour le collaboratif local,
- Collabora Online → alternative souveraine crédible,
- Passage au format ODF,
- Phase-out des macros VBA,
- Portage vers Python, JS ou solutions internes.

Le vrai défi ?  
L’utilisateur.

L’être humain adore ce qu’il connaît.  
Changer d’outil, c’est casser un rituel.  
Et tant que l’outil fonctionne “assez bien”, aucune Direction n’a envie de prendre le risque du changement.

Le problème n’est donc pas Office.  
Le problème, ce sont :

- 20 ans d’habitudes,
- des macros héritées,
- des process collés à Excel,
- une absence de vision long terme.

Souveraineté = stratégie + gouvernance.  
Pas “changer de suite bureautique”.

---

## 5️⃣ Alors, la vraie question : la souveraineté est-elle dans Microsoft ?

On pourrait se dire “Oui, Microsoft n’est pas souverain, donc sortons-en”.  
Mais ce serait oublier la phrase la plus importante du débat :

**👉 La souveraineté n’est pas un fournisseur. C’est un modèle d’architecture.**

La question n’est pas :  
“Utilisons-nous Microsoft ?”

La question est :  
“Sommes-nous dépendants d’un cloud étranger pour fonctionner ?”

Si votre SI :

- tombe si Azure AD tombe,
- ne s’authentifie plus sans un service US,
- dépend d’un MFA externe américain,
- stocke sa documentation dans SharePoint Online,
- vit dans Teams,
- voit ses identités dominées par Entra ID…

alors oui, vous avez un problème de souveraineté.

Mais ce problème n’a rien à voir avec Word.  
Il est dans la dépendance systémique à un cloud qui n’est pas le vôtre.

---

## 🟣 6️⃣ TEAMS : excellent pour l’externe, beaucoup moins pour l’interne (et c’est là qu’on se trompe)

S’il y a bien un outil qui crée un énorme malentendu dans les débats sur la souveraineté, c’est Microsoft Teams.

On lit partout que “Teams = dépendance, Teams = pas souverain, Teams = danger”.  
En réalité, c’est beaucoup plus nuancé.

---

### 👍 Pour l’externe : Teams est parfait

Pour les rendez-vous commerciaux, les formations, les meetings avec les partenaires, les appels clients… Teams est une bénédiction.  
Tout le monde l’a.  
Tout le monde sait s’en servir.  
Et ça marche, même si la bande passante ressemble à un tuyau d’arrosage bouché.

Et surtout :

**👉 Que la visioconférence d’un rendez-vous commercial passe par Microsoft n’a jamais compromis la souveraineté d’un SI.**  
Ce sont des données “circulantes”, pas du stockage stratégique ou des identités.

Là-dessus, Teams fait le job.

---

### 👎 Pour l’interne : c’est beaucoup plus discutable

Le problème interne n’est pas Teams en tant qu’outil de collaboration, mais la structure qu’il impose :

- La majorité des partages passent par SharePoint Online (cloud US).
- Les documents échangés sont automatiquement poussés dans OneDrive ou SPO.
- Les historiques, pièces jointes, snippets, photos → stockées dans Graph API + SPO.
- La gouvernance documentaire explose, et on perd la maîtrise du patrimoine informationnel.

**Teams = interface  
SharePoint = stockage réel**  

Et c’est le deuxième qui pose problème, pas le premier.

---

### 💬 L’erreur d’architecture : Teams comme outil principal interne

Une entreprise qui base toute sa communication interne sur Teams fait plusieurs choix implicites :

- elle accepte que ses documents critiques vivent dans un cloud étranger,
- elle délègue son patrimoine documentaire à SPO,
- elle adopte une logique full SaaS sur les conversations internes,
- elle crée une dépendance totale au Graph API.

C’est un choix possible — mais sûrement pas un choix souverain.

Teams peut être utilisé en interne, mais à condition de ne pas l’utiliser comme stockage par défaut, et de maîtriser les policies d’upload, de chat et de partage.  
Autant dire que dans 90 % des entreprises, ce n’est pas le cas.

---

## 🏰 Alternatives internes plus souveraines

### 🔐 Private Discuss

Un outil fermé, auto-hébergé, maîtrisable, déjà déployé dans des environnements sensibles (dont EDF).  
Il coche toutes les cases :

- stockage interne,
- encryption maîtrisée,
- gouvernance claire,
- pas d’extraterritorialité,
- pas de fuite automatique vers le cloud.

C’est Teams, mais version “SSI valide”.

---

### 🟧 Micollab (version On-Prem)

Moins connu du grand public, mais très solide pour :

- la téléphonie interne,
- le chat sécurisé,
- les communications unifiées,
- les environnements industriels qui n’aiment pas trop les clouds anglo-saxons.

Et surtout :  
👉 On-prem = souveraineté opérationnelle + contrôle du stockage + aucune dépendance intrusive.

---

## 🧠 Le bon modèle :

### **Teams pour l’externe / outil fermé pour l’interne**

Ce modèle hybride, parfaitement raisonnable, permet de :

- garder la compatibilité universelle (visio commerciale),
- réduire drastiquement la dépendance documentaire,
- maîtriser les flux internes,
- conserver une architecture souveraine,
- éviter de pousser les secrets internes dans SharePoint.

Il n’y a aucune contradiction à :

- faire de la visio client sur Teams  
- **ET**  
- protéger son SI interne avec Private Discuss ou Micollab.

Souveraineté ≠ rejet dogmatique  
Souveraineté = choix éclairé + maîtrise des dépendances.

---

## 🔥 Conclusion : arrêtons de taper sur Office, regardons la structure

La souveraineté numérique, ce n’est pas :

- le choix d’un éditeur,
- la suite bureautique,
- le client de messagerie.

C’est :

- où vivent les identités,
- où sont stockées les données,
- qui contrôle les API,
- qui contrôle la chaîne d’authentification,
- qui peut couper l’accès,
- qui impose les règles du jeu.

Office n’est pas une menace.  
La dépendance au cloud l’est.

Et aujourd’hui, dans beaucoup d’entreprises, la souveraineté se résume à une question très simple :  
**👉 “Que se passe-t-il si Azure AD tombe ?”**

Si la réponse est : “rien ne marche”,  
alors ce n’est pas Word le problème.
