

!!! success "Le cloud computing, ce n’est pas 'mettre des serveurs ailleurs'"
    Beaucoup d’organisations pensent qu’en migrant leurs serveurs vers une infrastructure virtualisée ou hébergée, elles “font du cloud”.  
    Mais **non** : le cloud computing repose sur **un modèle d’exploitation et de consommation** différent.

## Les cinq caractéristiques essentielles d’un environnement Cloud selon le NIST

Selon la définition du **National Institute of Standards and Technology (NIST)**, un environnement Cloud véritable doit présenter **cinq caractéristiques fondamentales**.  
Ces propriétés garantissent que le modèle de service respecte les principes de flexibilité, d’efficacité et de gouvernance attendus dans un contexte institutionnel tel que celui de la RCJU.

---

### 1. **Self-service à la demande**
Un environnement Cloud doit permettre aux utilisateurs — qu’ils soient techniques ou métiers — de **provisionner eux-mêmes des ressources informatiques** (machines virtuelles, espaces de stockage, environnements applicatifs, etc.) **sans intervention manuelle** de la part de l’équipe IT.  
Cette autonomie ne signifie pas absence de contrôle : le cadre de gouvernance doit définir des **quotas, des modèles de déploiement standardisés et des processus d’approbation automatisés**.  
L’objectif est d’accélérer la mise à disposition des services tout en conservant la maîtrise des coûts et de la sécurité.

---

### 2. **Accès réseau étendu**
Les services Cloud doivent être **accessibles de manière ubiquitaire**, via des **réseaux standards** et des **protocoles ouverts** (principalement HTTPS, TLS, REST, etc.).  
L’accès doit être possible depuis différents types de terminaux — postes de travail, tablettes, appareils mobiles — sans dépendance à un environnement spécifique.  
Ce principe assure la **mobilité, l’agilité et la continuité de service**, tout en reposant sur des mécanismes d’authentification et de sécurisation conformes aux standards de la RCJU (Entra ID, MFA, accès conditionnel).

---

### 3. **Mutualisation des ressources**
L’infrastructure Cloud repose sur un **modèle de ressources partagées et virtualisées**.  
Les capacités de calcul, de stockage et de réseau sont regroupées dans des pools logiques, puis allouées dynamiquement selon les besoins.  
Cette mutualisation garantit une **optimisation des ressources**, une **meilleure résilience** et une **économie d’échelle**, tout en assurant la **séparation logique et la sécurité des données** entre locataires (tenants) dans les environnements publics ou hybrides.  
Dans le contexte RCJU, ce principe implique une vigilance accrue sur la **localisation et la souveraineté des données**.

---

### 4. **Élasticité rapide**
Un environnement Cloud doit pouvoir **ajuster automatiquement ses capacités** (CPU, mémoire, bande passante, stockage, instances applicatives) **en fonction de la demande réelle**.  
Cette élasticité, à la hausse comme à la baisse, permet d’absorber des pics d’activité sans surdimensionner les ressources permanentes.  
Elle contribue à la **continuité de service**, à la **performance perçue par les utilisateurs** et à une **maîtrise fine des coûts** (paiement à l’usage).  
Pour la RCJU, ce principe soutient la mise en place de services adaptatifs et durables, limitant la surconsommation énergétique et les coûts d’exploitation.

---

### 5. **Mesurabilité et transparence de la consommation**
Chaque ressource ou service Cloud doit être **suivi, mesuré et tracé** de manière automatisée.  
Les indicateurs de consommation (CPU, stockage, bande passante, licences, sessions, etc.) permettent une **facturation à l’usage** ou un **reporting de consommation interne**.  
Cette capacité de mesurabilité renforce la **transparence**, la **responsabilisation des unités consommatrices** et la **gouvernance financière** des services numériques.  
Dans le cadre RCJU, elle soutient le pilotage budgétaire et la mise en œuvre d’un **FinOps public** adapté aux contextes institutionnels.

!!! success ""
    Pour obtenir ces propriétés, il faut **plus que de la technologie** :  il faut **changer la manière dont on gère, délivre et consomme l’IT**.

---

