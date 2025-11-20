---
tags:
  - Microsoft
  - Middleware
  - Surveiller
  - Plateformes
---

# Internet Information Services (IIS)
<!-- description/short {start} -->
IIS est le serveur applicatif historique de Microsoft et une composante essentielle du SI de la RCJU, dont l’usage comme conteneur applicatif pour les nouvelles solutions doit être évalué avec discernement selon les besoins et les architectures cibles.
<!-- description/short {end} -->

!!! info "Utilisation"

    IIS est le serveur applicatif de base utilisé à la RCJU. Il remplit diverses fonctions:

    - Reverse proxy
    - Hébergement d'applications web
    - Cluster pour plateforme fonctionelle dédiée (Guichet Virtuel, Sharepoint)
    - Intégration avec l'écosystème Microsoft (AD, Authentification Windows)


!!! danger "Périmètre"

    Dans le cas de nouvelles solutions, il y aura lieu de challenger l'utilisation de IIS. En effet, le concept de serveur applicatif
    centralisé regroupant plusieurs applications (sites) est un concept à remplacer par des principes plus atomiques et indépendants (containerisation)


## Description
IIS reste le serveur applicatif historique de Microsoft. Et il demeure une brique essentielle du SI de la RCJU.

Pour ce qui est des nouvelles solutions métiers, nottament (acuisition ou développement custom), l'utilisation de IIS en tant que container applicatif doit être 
finement étudié.

### Intégration avec ASP.NET Core 
Pour les applis .NET modernes :

- IIS ne traite plus directement les requêtes .NET Core
- Il agit comme reverse proxy vers Kestrel
- Recommandé toutefois a des fin sd'intégration (SSL, authentification, gestion centralisée)

### Alternatives potentielles

- nginx, sous forme de container
- Apache HTTP Server, sous forme de container

### Liens SNJU
!!! success
    **2.1**: La plateforme IIS permet d'héberger des applications et prestations de manière maitrisée dans un écosystème connu

    **2.4**: La maitrise et l'expérience interne de la plateforme permet de proposer des composants maitrisée assurant ainsi une confiance dans les application déployées

!!! warning 
    **1.3**: Le concept même de serveur applicatif centralisé, ne permet pas une modularite et une évolutivité accrue. Le partage des dépendances entre les différents sites d'un serveur IIS, nottament, est un frein à l'évolutivité. Il conviendra de gérer cet aspect dés le design des solutions hébergées sur IIS

    **1.4**: Toujours pour la même raison, les ressources utilisées pour exécuter les services IIS ne dont pas en liens avec les ressources effectivement utilisées par les composants hébergées. 

    




