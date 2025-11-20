---
tags:
  - Middleware
  - Principes
  - Adopter

---
# Security by Design
<!-- description/short {start} -->
Le principe de Security by Design consiste à intégrer la sécurité dès la conception des systèmes et applications afin de garantir la confidentialité, l’intégrité et la résilience du SI tout en assurant la conformité réglementaire et la réduction proactive des risques.
<!-- description/short {end} -->

## Description
Le principe de **Security by Design** impose que la sécurité soit **intégrée dès la conception** des systèmes, applications et infrastructures, et non ajoutée après coup.  
Il garantit que chaque solution mise en œuvre au sein de la RCJU respecte les exigences de **confidentialité, d’intégrité, de disponibilité et de traçabilité** des données, dès les premières phases de conception.  
Cette approche proactive vise à **réduire les risques**, à **assurer la conformité réglementaire (LPD, RGPD)** et à **renforcer la résilience du SI** face aux menaces.  
Elle s’applique à toutes les couches du cadre technologique — de l’infrastructure au développement applicatif — et à toutes les phases du cycle de vie (design, build, run).
 
- **I. Classification des données et gestion des accès**  
  > Identifier les données sensibles et appliquer le principe du *moindre privilège* (Least Privilege Access).  
  > Utiliser des mécanismes robustes d’authentification et d’autorisation (AD/Entra ID, MFA).  

- **II. Sécurisation des environnements et des configurations**  
  > Appliquer les *benchmarks* de durcissement (CIS, Microsoft Baselines).  
  > Éviter les configurations par défaut et automatiser le contrôle de conformité (IaC, Policy as Code).  

- **III. Gestion des secrets et des identités techniques**  
  > Centraliser la gestion des secrets dans des coffres-forts (Vault, Key Vault).  
  > Interdire le stockage de mots de passe ou clés dans le code ou les dépôts Git.  

- **IV. Protection des échanges et des données**  
  > Chiffrer les flux (TLS 1.2+), les données au repos et les sauvegardes.  
  > Garantir la confidentialité des échanges inter-systèmes (API, SFTP, VPN, HTTPS).  

- **V. Surveillance, audit et traçabilité**  
  > Mettre en place une journalisation complète des accès, des actions et des anomalies.  
  > Intégrer les journaux dans une solution centralisée (SIEM) et corréler les événements.  

- **VI. Sécurité dans le développement (DevSecOps)**  
  > Intégrer des contrôles de sécurité dans les pipelines CI/CD (SAST, DAST, IaC scanning).  
  > Vérifier les dépendances logicielles (SBOM, signature d’images, analyse de vulnérabilités).  

- **VII. Revue d’architecture et validation continue**  
  > Réaliser des *Threat Models* dès la conception et avant tout déploiement majeur.  
  > Soumettre les composants critiques à des revues de sécurité et des tests d’intrusion réguliers.  

- **VIII. Conformité et sensibilisation**  
  > Aligner les pratiques sur les normes ISO 27001, NIST, LPD/RGPD.  
  > Former les équipes techniques et métiers à la sécurité opérationnelle et aux bonnes pratiques.  

