# 🇨🇭 6 enjeux essentiels de souveraineté pour une administration publique suisse (on-premise)

## 1️⃣ Maîtrise des identités et de l’authentification (Identity Plane)
Même en environnement local, l’intégration de services cloud (M365, SaaS métiers, outils collaboratifs) déporte progressivement la fonction identité hors du périmètre souverain.

### Pourquoi c’est critique ?
- L’identité est la **clé du SI**.  
- Un IdP externe = dépendance opérationnelle immédiate.  
- Si Entra ID / un IdP SaaS tombe → *toute l’administration s’arrête*.

---

## 2️⃣ Localisation juridique explicite et implicite des données
Même un SI principalement on-premise peut voir ses données partir à l’étranger via :
- modules logiciels intégrés,  
- télémétrie,  
- synchronisations automatiques,  
- sauvegardes imposées par certains éditeurs.

### Enjeu :
📌 *Garantir que toutes les données sensibles — même transitoires — restent sous un cadre juridique suisse ou contractuellement maîtrisé.*

---

## 3️⃣ Capacité d’opérer en autonomie complète
Une infrastructure on-premise n’est réellement souveraine que si elle peut fonctionner même en cas :
- de perte d’accès Internet,  
- d’indisponibilité d’un fournisseur cloud,  
- de coupure d’un service externe critique (authentification, mise à jour, moteur d’autorisations).

### Enjeu :
📌 *Assurer la continuité opérationnelle sans dépendre d’un service tiers non maîtrisé.*

---

## 4️⃣ Transparence et auditabilité des composants critiques
Les outils cloud ou hybrides introduisent des angles morts techniques :

- absence de journalisation côté fournisseur,  
- impossibilité d’auditer les systèmes internes,  
- flux réseau opaques,  
- configurations imposées et non inspectables.

### Enjeu :
📌 *Pouvoir tracer, auditer et comprendre le cheminement des données et le fonctionnement réel des composants critiques.*

---

## 5️⃣ Dépendance aux API propriétaires et aux services annexes
Les éditeurs modernisent leurs plateformes en imposant des services indissociables :
- Graph API chez Microsoft,  
- services de licences en ligne,  
- connecteurs obligatoires,  
- moteurs IA non hébergeables localement,  
- workflows “cloud-only”.

### Risque :
📌 *L’organisation devient dépendante d’un écosystème qu’elle ne contrôle pas et dont la sortie devient très coûteuse.*

---

## 6️⃣ Souveraineté des compétences internes
Un SI peut être souverain techniquement, mais pas opérationnellement si l’administration dépend :
- d’un prestataire unique,  
- de compétences rares non documentées,  
- d’intégrateurs externes pour les opérations quotidiennes.

### Enjeu :
📌 *Assurer la pérennité, la formation et la capacité opérationnelle des équipes internes pour maintenir des services essentiels en autonomie.*

---

# 🏁 Synthèse
Pour une administration suisse majoritairement on-premise, la souveraineté numérique repose aujourd’hui sur :

- le **contrôle de l’identité**,  
- la **localisation réelle des données**,  
- l’**autonomie opérationnelle**,  
- l’**auditabilité**,  
- la **maîtrise des API propriétaires**,  
- la **pérennité des compétences internes**.

L’on-premise ne suffit plus :  
**la souveraineté se joue maintenant dans la maîtrise des dépendances.**
