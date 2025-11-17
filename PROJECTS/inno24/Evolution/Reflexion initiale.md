#inno24 
# 1) Architecture documentaire (simple, extensible)

## 1.1. Découpage par domaines (namespaces)

Crée **un index Elasticsearch par grand domaine** + un index “référentiels partagés” :

- `civ-automobile`, `civ-impot`, `civ-environnement`, `civ-sport`, `civ-culture`
    
- `civ-law` (textes légaux / directives), `civ-faq` (FAQ transverses validées)
    

> Avantage : on **contient sémantiquement** les résultats et on applique des **politiques spécifiques** par domaine (synonymes, filtres, boosts).

## 1.2. Métadonnées **obligatoires**

Ajoute des champs normalisés (contrôle fort) — _tous_ les documents doivent les avoir:

- `domain` : {automobile, impot, environnement, sport, culture, …}
    
- `audience` : {particulier, professionnel, mixte} → défaut = **particulier**
    
- `doc_type` : {loi, procédure, FAQ, page_info, tarifs, formulaire, communiqué}
    
- `jurisdiction` : {confederation, canton, commune} (si pertinent)
    
- `valid_from`, `valid_to` : dates de validité (pour gérer versions)
    
- `source_rank` : score d’autorité (loi=3, site officiel=2, autre public=1)
    
- `permit_scope` (ex. dans automobile) : {standard, professionnel, mixte, n/a}
    
- `permit_category` : {A, A1, B, BE, C, D, Taxi, …}
    
- `language` : {fr, de, it, en}
    
- `action_url` : lien(s) officiels vers la prestation/démarche
    
- `last_reviewed_by` / `last_reviewed_at` (traçabilité éditoriale)
    

> Ces champs permettent des **filtres stricts** au moment du retrieval, évitant l’intrusion des “permis professionnels” quand la question concerne le “standard”.

## 1.3. Vocabulaire contrôlé (mini-ontologie pragmatique)

Un fichier JSON/YAML central qui pose les **labels canoniques + alias** :