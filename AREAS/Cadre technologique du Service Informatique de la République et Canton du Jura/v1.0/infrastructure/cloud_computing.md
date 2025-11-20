---
tags:
  - Infrastructure
  - Principes
  - Evaluer
---
# Cloud Computing
<!-- description/short {start} -->
Le Cloud Computing est un modèle de fourniture de services informatiques offrant à la demande des ressources mutualisées, automatisées et élastiques via le réseau, selon différents modèles de service et modes de déploiement.
<!-- description/short {end} -->

## Description
> Le Cloud Computing, c’est un **modèle de fourniture de services informatiques** permettant d’obtenir, via le réseau, des ressources **mutualisées, automatisées, élastiques et mesurées**, selon différents **modèles de service** (IaaS, PaaS, SaaS) et **modes de déploiement** (privé, public, hybride).

## Caractéristiques
- **I. Libre-service à la demande (On-demand self-service)** 
> L’utilisateur peut provisionner des ressources (VM, stockage, application) **automatiquement**, sans intervention humaine côté fournisseur.

- **II. Accès réseau large (Broad network access)** 
> Les services sont accessibles via le réseau (souvent Internet ou réseau interne) depuis **divers terminaux** (PC, tablette, mobile, API).

- **III. Mutualisation des ressources** 
> Les ressources physiques sont **partagées dynamiquement** entre plusieurs clients ou services (multi-tenant), avec isolation logique.

- **IV. Élasticité rapide** 
> Les ressources peuvent être **ajoutées ou retirées rapidement** selon la demande (scalabilité automatique).

- **V. Mesurabilité du service** 
> L’utilisation est **mesurée et surveillée**, **permettant la facturation à l’usage** (pay-per-use) ou le **showback interne**.

## Mode de service


## Mode de déploiement

## Mais aussi...
# ☁️ Le cloud computing : bien plus qu’une infrastructure


C’est un **modèle d’exploitation complet**, qui combine **technologie + automatisation + organisation + culture**.

---

## 1. Le cloud computing, ce n’est pas “mettre des serveurs ailleurs”

Beaucoup d’organisations pensent qu’en migrant leurs serveurs vers une infrastructure virtualisée ou hébergée, elles “font du cloud”.  
Mais **non** : le cloud computing repose sur **un modèle d’exploitation et de consommation** différent.

Selon le **NIST**, un environnement cloud doit posséder **5 caractéristiques essentielles** :

| # | Caractéristique | Enjeux |
|---|------------------|--------|
| 1️⃣ | **Self-service à la demande** | Les utilisateurs provisionnent leurs ressources sans passer par l’IT |
| 2️⃣ | **Accès réseau étendu** | Les services sont accessibles via Internet ou un réseau privé |
| 3️⃣ | **Mutualisation des ressources** | Les ressources sont partagées, virtualisées et optimisées |
| 4️⃣ | **Élasticité rapide** | Les capacités augmentent ou diminuent automatiquement selon la charge |
| 5️⃣ | **Mesurabilité** | L’utilisation est suivie, mesurée et éventuellement facturée à l’usage |

👉 Pour obtenir ces propriétés, il faut **plus que de la technologie** :  
il faut **changer la manière dont on gère, délivre et consomme l’IT**.

---

## 2. Les couches nécessaires pour “faire du cloud”

### 🧱 **1. La couche technique (infrastructure)**
- Virtualisation, stockage, réseau convergé  
- Outils comme **VMware**, **Nutanix**, **OpenStack**, **Kubernetes**  
- Permet la **mutualisation** et **l’élasticité**  
➡️ C’est la base, mais insuffisante seule.

---

### **2. La couche logicielle (automatisation & orchestration)**
- Automatisation du provisioning, du scaling, et de la configuration  
- Portail self-service pour les utilisateurs internes  
- API et scripts (**Terraform**, **Ansible**, **CI/CD**, etc.)  
➡️ Apporte la **rapidité et l’autonomie** typiques du cloud.

---

### **3. La couche organisationnelle (processus & gouvernance)**
- L’IT devient **fournisseur de services**, non plus “gardien des serveurs”  
- Mise en place de **catalogues de services** et de **chargeback/showback**  
- Gestion du cycle de vie des ressources (création, usage, suppression automatique)  
➡️ Fait passer l’IT à une **logique orientée service**.

---

### **4. La couche culturelle (mindset & collaboration)**
- Approche **DevOps** : collaboration entre développement et exploitation  
- **Culture produit** plutôt que projet  
- **Automatisation**, **responsabilisation** et **“fail fast”**  
- Approche **as-a-service** : tout doit être consommable à la demande  
➡️ C’est la **transformation culturelle** qui permet au cloud de tenir ses promesses.

---

## 💡 3. En résumé

| **Dimension** | **Exemples d’éléments à mettre en place** | **Objectif** |
|----------------|--------------------------------------------|--------------|
| **Technologique** | Virtualisation, API, stockage objet, conteneurs | Moderniser l’infrastructure |
| **Automatisation** | Terraform, Ansible, pipelines CI/CD | Rapidité, cohérence |
| **Organisationnelle** | Catalogue de services, chargeback, ITSM agile | Orienter l’IT vers le service |
| **Culturelle** | DevOps, agilité, ownership, innovation | Accélérer et responsabiliser |

---

## 🧭 4. En conclusion

➡️ Une **infrastructure moderne seule (même HCI ou virtualisée)** ≠ cloud computing.  
➡️ Le **cloud computing**, c’est :
- une **infrastructure flexible** (technologie),  
- une **gestion automatisée et mesurée** (outils et processus),  
- une **organisation orientée service** (gouvernance),  
- une **culture agile et collaborative** (personnes et mentalité).

> 💬 *« Le cloud, ce n’est pas un endroit, c’est une manière de faire de l’IT. »*

---


