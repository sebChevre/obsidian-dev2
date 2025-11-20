---
tags:
  - Plateformes et Solutions Métiers
  - Principes
  - Adopter
---
# Solution Cloud-Ready

<!-- description/short {start} -->
Les 12-Factor Apps définissent un cadre de bonnes pratiques pour concevoir des applications cloud natives, scalables, portables et maintenables, en favorisant la séparation des responsabilités, l’automatisation et la standardisation pour assurer leur compatibilité avec les architectures modernes et hybrides.
<!-- description/short {end} -->

## Description
Le principe des **12-Factor Apps** définit un ensemble de bonnes pratiques pour concevoir, développer et exploiter des **applications modernes, portables et résilientes**, adaptées aux environnements **cloud** et **hybrides**.  
Il vise à garantir la **scalabilité**, la **reproductibilité** et la **maintenabilité** des applications, en standardisant leur structure, leur configuration et leur mode d’exécution.  
Chaque facteur encourage la **séparation claire des responsabilités**, la **gestion externalisée des configurations**, l’**automatisation du déploiement** et la **statelessness** des processus applicatifs.  
Dans le contexte RCJU, ce principe sert de **référence pour les développements internes et les acquisitions logicielles**, afin d’assurer la compatibilité avec les architectures modernes et les plateformes PaaS.  
Il contribue directement à la **souveraineté, à la portabilité et à la durabilité** des solutions numériques mises en œuvre au sein du SI.  

- **I. Base de code** 
> Une seule base de code suivie par gestion de version (ex. Git), déployée en plusieurs environnements.

- **II. Dépendances** 
> Déclarer explicitement et isoler strictement les dépendances (ex. via `requirements.txt`, `package.json`, etc.).

- **III. Configuration** 
> Stocker la configuration dans l’environnement (variables d’environnement), jamais dans le code.

- **IV. Services externes** 
> Considérer les services externes (BDD, messagerie, cache, API) comme des ressources attachées et remplaçables sans modification du code.

- **V. Construction, publication, exécution** 
> Séparer clairement les étapes de construction (build), publication (release) et exécution (run).

- **IVI. Processus** 
> Exécuter l’application comme un ou plusieurs processus sans état (*stateless*), avec persistance gérée par des services externes.

- **VII. Port mappé** 
> Exposer les services via un port (binding), sans dépendre d’un serveur d’application externe.

- **VIII. Concurrence** 
> Mettre à l’échelle via le modèle de processus (multiplication des instances plutôt que montée en puissance verticale).

- **IX. Jetabilité** 
> Les processus doivent être jetables : démarrage rapide, arrêt propre (grâce aux signaux système).

- **X. Parité dev/prod** 
> Maintenir une parité la plus proche possible entre développement, staging et production (temps, outils, versions).

- **XI. Logs** 
> Considérer les logs comme un flux d’événements, envoyés vers la sortie standard et agrégés par l’environnement d’exécution.

- **XII. Processus d’administration** 
> Exécuter les tâches d’administration/maintenance (migrations, scripts ponctuels) en tant que processus uniques et isolés.

