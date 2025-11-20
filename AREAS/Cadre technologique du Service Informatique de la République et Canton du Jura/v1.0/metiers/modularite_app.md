---
tags:
  - Plateformes et Solutions Métiers
  - Principes
  - Adopter
---
# Modularité applicative
<!-- description/short {start} -->
Ce principe établit une séparation stricte entre le front-end et le back-end afin de garantir l’indépendance technologique, la modularité et la maintenabilité des applications, tout en favorisant une architecture ouverte, scalable et interopérable.
<!-- description/short {end} -->

## Description
Ce principe définit la **séparation stricte entre la couche de présentation (Front-End)** et la **couche de services (API / Back-End)** dans le cycle de développement, de build et d’exécution.  
Il vise à garantir l’**indépendance technologique**, la **modularité** et la **maintenabilité** des composants applicatifs.  
Les applications modernes s’appuient sur un **front-end autonome** (Angular, React, Vue, etc.) qui consomme des données exposées via des **API REST ou GraphQL**.  
Cette séparation permet d’**industrialiser les chaînes CI/CD** distinctes, de **déployer et faire évoluer** indépendamment le front et le back, et de **mieux répartir les responsabilités** entre équipes.  
Dans le contexte RCJU, ce principe favorise une architecture **ouverte, scalable et interopérable**, compatible avec les approches *microservices* et les environnements cloud ou conteneurisés.  