---
tags:
  - Plateformes et Solutions Métiers
  - Plateformes
  - Surveiller
  - Microsoft
---
# Sharepoint
<!-- description/short {start} -->
Microsoft SharePoint est une plateforme collaborative et documentaire servant de socle à la gestion, au partage et à l’archivage de l’information au sein de la RCJU, tout en intégrant des fonctionnalités de sites d’équipe, de workflows et de recherche d’entreprise.
<!-- description/short {end} -->

## Description
**Microsoft SharePoint** est une **plateforme collaborative et documentaire** permettant le stockage, la gestion et le partage de l’information au sein de la RCJU.  
Elle offre des fonctionnalités de **sites d’équipe**, de **gestion de contenu**, de **flux de travail**, et de **recherche d’entreprise**.  

La plateforme constitue le **socle de la collaboration et de la gestion documentaire** institutionnelle, avec des mécanismes de contrôle d’accès et d’archivage.  


## Périmètre d'utilisation
!!! danger
    Au sein de la RCJU, SharePoint est exploité pour plusieurs **cas d’utilisation** :
    - **Système de stockage de données** : utilisation des **listes SharePoint** comme référentiels de données structurées (suivi d’activités, registres, inventaires, etc.).  
    - **Système documentaire** : intégration avec **OneNote** pour la gestion de notes, de comptes rendus et de documentation partagée.  
    - **Plateforme applicative légère** : création de **formulaires et de petits applicatifs métiers** (collecte d’informations, validation simple) à l’aide de listes, flux et formulaires intégrés.  

    Bien que ces usages soient **pratiques pour des besoins simples ou locaux**, SharePoint montre rapidement ses **limites** dès qu’il est utilisé comme **système de stockage de données** ou **plateforme applicative** :  
    - Les **listes** ne sont pas conçues pour supporter de gros volumes de données, ni des transactions complexes.  
    - Les **formulaires** et automatisations internes offrent peu de flexibilité et sont difficiles à maintenir à grande échelle.  
    - En tant que socle applicatif, SharePoint manque de **cloisonnement fonctionnel**, de **gestion fine des dépendances** et de **gouvernance technique** adaptée aux développements métiers.  

    Ainsi, SharePoint doit être considéré avant tout comme une **plateforme documentaire et collaborative**, et non comme un environnement de développement applicatif ou de base de données.  
    Les solutions nécessitant une logique métier, une volumétrie importante ou une intégration avancée doivent être orientées vers des **plateformes dédiées** (par ex. **BizTalk**, **applications .NET**, ou **solutions spécifiques métier**).  