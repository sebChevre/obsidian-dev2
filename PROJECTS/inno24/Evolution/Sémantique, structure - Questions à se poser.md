#inno24 
# 1) Objectifs & périmètre

- Quel est l’objectif prioritaire : **précision** (zéro hallucination), **rappel** (ne rien manquer), **latence/coût**, ou **couverture multi-domaines** ?
    
- Public visé : tout public, niveau “grand public” ? Langues supportées (FR/DE/IT/EN) ?
    
- Peut-on poser des **questions de clarification** à l’utilisateur final quand la requête est ambiguë ?
    

# 2) Contenus & sources

- Liste des sources actuelles (site officiel, lois, FAQ, autres sites publics). Y a-t-il des **niveaux d’autorité**/priorités entre sources (p. ex. loi > site cantonal > blog) ?
    
- Fréquence de mise à jour ? Faut-il gérer la **version “en vigueur à la date X”** des textes (validité temporelle) ?
    
- As-tu un **exemple de document** par source (ou un échantillon anonymisé) ?
    

# 3) Elasticsearch actuel

- Version d’Elasticsearch ? Utilisez-vous **BM25 uniquement**, **ELSER**, **denses embeddings** (kNN), **hybride** (lexical + vectoriel), ou un **re-ranker** (Cohere/Elastic LTR) ?
    
- **Mapping** actuel : champs stockés, analyzers (stemming, stopwords, synonyms), normalizers, language analyzers ?
    
- **Chunking** actuel (taille en tokens, overlap), champs de métadonnées présents (ex.: `domain`, `audience`, `jurisdiction`, `law_reference`, `permit_type`, `effective_from/to`) ?
    
- Avez-vous déjà un **dictionnaire de synonymes** (ex.: “permis”, “licence”, “cat. B”, “conduite auto”) ?
    

# 4) Taxonomie / Ontologie

- Existe-t-il une **taxonomie officielle** (ex.: domaines = “automobile”, “impôt”, “environnement”… ; sous-domaines ; types de prestations ; publics “particulier / professionnel”) ?
    
- Souhaitez-vous une **ontologie** plus fine (entités : `Permis`, `Catégorie`, `Titulaire`, `Condition`, `Prestation`, `Tarif`, `Âge`, `Véhicule`) et un **contrôle de vocabulaire** (labels canoniques + alias) ?
    
- Doit-on distinguer **audience** (citoyen vs professionnel) et **intention** (information, procédure, formulaire, tarif, délai) ?
    

# 5) Politique de routage & filtres

- Peut-on **forcer par défaut** le routage des questions citoyennes vers `audience:particulier` (et exclure `audience:professionnel` sauf mention explicite) ?
    
- Voulez-vous une **liste blanche**/noire de sources par domaine ? (ex.: pour “permis B”, exclure les documents `permit_scope:professionnel` sauf demande explicite)
    
- Quelles **règles de tie-break** si plusieurs sources se contredisent ?
    

# 6) Pile LangChain / Agents

- Quels **agents** et **tools** utilisez-vous (retriever, web, calcul, règles…) ? Un **router** d’intentions (multi-retrievers) est-il déjà en place ?
    
- Modèle d’**embedding** actuel (nom exact) et LLM de génération ?
    
- Paramètres clés : `k` (topK), filtres ES déjà utilisés, prompt de **reformulation de requête** (query rewriting), **guardrails** (instructions système) ?
    
- Faites-vous du **RAG multi-étapes** (classif d’intent → extraction d’entités → filtres → retrieval → réécriture → rerank → réponse) ?
    

# 7) Interface & UX

- L’UI peut-elle afficher **citations**, **source badges**, **panneaux de désambiguïsation** (ex.: “Parlez-vous du permis B (voiture) ou des permis professionnels C/D/Taxi) ?”) et **filtres visibles** (audience, domaine) ?
    
- Faut-il renvoyer des **liens de démarches** (formulaires, RDV) + **mises en garde juridiques** ?
    

# 8) Qualité, évaluation, métriques

- Disposez-vous d’un **jeu d’évaluation** (questions → bonnes réponses + sources) ?
    
- KPIs suivis : précision @1, taux de désambig, taux de refus “je ne sais pas”, feedback utilisateur, temps de réponse ?
    
- Exemples précis de **mauvaises réponses** (logs) là où le pro vs standard se mélange.
    

# 9) Contraintes & conformité

- Contraintes de **latence/coût** ?
    
- Exigences **juridiques** (langage non contraignant, horodatage des références, neutralité) et **accessibilité** (WCAG) ?
    
- Pas de données personnelles → OK, mais doit-on filtrer **PNR**, **numéros** sensibles si l’utilisateur en fournit ?
    

# 10) Extension multi-domaines

- Ordre d’arrivée des prochains domaines (impôt, environnement, sport…) ?
    
- Pour chaque domaine, existe-t-il déjà des **schémas de métadonnées** internes ou des **lexiques** officiels ?
    

---

## Ce que je proposerai ensuite (aperçu, pour te montrer la direction)

- Une **stratégie “Namespace + Ontologie + Routage”** :
    
    - **Namespaces/indices** par grand domaine (`automobile`, `impot`, `environnement`…), plus un index `shared_law`.
        
    - **Métadonnées obligatoires** (ex.: `domain`, `audience`, `permit_scope`, `jurisdiction`, `effective_from/to`, `source_rank`, `language`, `doc_type`).
        
    - Un **router d’intentions** (LLM ou règle) qui choisit le **retriever** + **filtres ES** adaptés (par défaut `audience:particulier`).
        
    - **Hybrid retrieval** (BM25 + vecteurs) + **re-ranking** par autorité/actualité + **policy de désambig**.
        
    - **Query rewriting** (normalisation, expansion via synonymes contrôlés).
        
    - **Garde-fous** côté génération (réponses cadrées, citations, “je ne sais pas” si doute, oracles de règles).
        
- Un **schéma de métadonnées** et une **liste de labels canoniques** (ex.: `permit_scope = {standard, professionnel}` ; `permit_category = {A, A1, B, BE, C, D, Taxi…}`) pour filtrage strict.
    
- Un **process d’ingestion** qui tague automatiquement les docs (NER + règles + vérification humaine légère pour les cas ambigus).
    
- Un **plan d’évaluation** (jeu de tests, métriques) + boucles d’amélioration.