# ✅ Checklist Cloud Privé (SI on-premise)

Cette checklist permet d’évaluer dans quelle mesure un SI on-premise répond aux critères d’un **cloud privé**, selon les principes du **NIST**.

| Domaine | Élément à vérifier | Critère atteint ? | Commentaires / actions nécessaires |
|----------|--------------------|------------------|------------------------------------|
| **1. Virtualisation** | Serveurs, stockage et réseau virtualisés (VMware, Hyper-V, OpenStack, etc.) | ☐ Oui / ☐ Non / X Partielement|  |
|  | Mutualisation des ressources physiques entre plusieurs services | ☐ Oui / ☐ Non |  |
| **2. Provisionnement à la demande** | Portail en libre-service pour créer et gérer des VM, environnements ou conteneurs | ☐ Oui / X Non / ☐ Partiellement|  |
|  | API ou interface pour provisionner automatiquement des ressources | ☐ Oui / ☐ Non |  |
| **3. Élasticité** | Possibilité d’ajouter/retirer dynamiquement des ressources selon la charge | ☐ Oui / ☐ Non |  |
|  | Orchestration automatique (autoscaling, load balancing, Kubernetes, etc.) | ☐ Oui / ☐ Non |  |
| **4. Facturation / Mesure d’usage** | Suivi de la consommation (CPU, RAM, stockage, réseau) par service/utilisateur | ☐ Oui / ☐ Non |  |
|  | Système de refacturation interne (showback/chargeback) | ☐ Oui / ☐ Non |  |
| **5. Accès réseau étendu** | Accès via des protocoles standards (HTTP, SSH, API REST) | ☐ Oui / ☐ Non |  |
|  | Authentification centralisée (AD, LDAP, SSO, IAM) | ☐ Oui / ☐ Non |  |
| **6. Automatisation** | Déploiement via Infrastructure as Code (Ansible, Terraform, etc.) | ☐ Oui / ☐ Non |  |
|  | Orchestration des déploiements applicatifs (CI/CD, pipelines, GitOps) | ☐ Oui / ☐ Non |  |
| **7. Gouvernance et sécurité** | Gestion centralisée des identités et des accès (IAM, rôles, politiques) | ☐ Oui / ☐ Non |  |
|  | Chiffrement des données au repos et en transit | ☐ Oui / ☐ Non |  |
|  | Journalisation et supervision centralisées (logs, métriques, alertes) | ☐ Oui / ☐ Non |  |
| **8. Normalisation et interopérabilité** | Standardisation des environnements (modèles de VM, containers, API) | ☐ Oui / ☐ Non |  |
|  | Compatibilité avec des plateformes PaaS / Cloud public (hybridation possible) | ☐ Oui / ☐ Non |  |
k
---

## Interprétation des résultats

| Score estimé | Niveau de maturité |
|---------------|--------------------|
| **0–30 %** | Infrastructure traditionnelle (non cloud) |
| **30–70 %** | Transition vers le cloud privé |
| **70–100 %** | Cloud privé mature |

