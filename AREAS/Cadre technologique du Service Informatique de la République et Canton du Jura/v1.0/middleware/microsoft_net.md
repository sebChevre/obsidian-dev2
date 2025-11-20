---
tags:
  - Microsoft
  - Ecosystème
  - Langages
  - Middleware
  - Plateformes
  - Adopter

---
# Plateforme Microsoft .NET
<!-- description/short {start} -->
.NET est une plateforme de développement unifiée de Microsoft permettant de créer, exécuter et maintenir des applications multiplateformes, performantes et sécurisées.
<!-- description/short {end} -->
!!! info "Utilisation"

    La plateforme .NET est la technologie d'exécution d'application à privilégier dans un contexte **hors containerisation**. Principalement deux modes de déploiement sont prévus: 

    - directement via une machine virtuelle
    - via [IIS](../middleware/microsoft_iis.md)

!!! danger "Restriction"

    Tous les nouveaux projet ne doivent en aucun cas se baser sur les versions **.NET Framework**, **WinForms**, **.NET Standard**. Ces solutions legacy sont à proscire pour de nouveaux projets. 

## Description
.NET se réfère à l’écosystème de Microsoft pour créer des applis web, desktop, mobiles, cloud, services, jeux, etc. 

C'est un ecosystème complet composée de:

- un runtime (CLR)
- des bibliothèques de base (BCL) 
- des SDKs/outils 


## Langages de développement
.NET prend en charge C#, F# et VB. Dans le cadre de projet de réalisation, il faudra privilégier **C#**



::timeline::

[
    {
        "title": "Launch",
        "content": "First implementation.",
        "icon": ":fontawesome-rocket:",
        "sub_title": "2022-Q1"
    },
    {
        "title": "One",
        "content": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        "icon": ":octicons-sun-16:",
        "key": "cyan",
        "sub_title": "2022-Q2"
    },
    {
        "title": "Two",
        "content": "Lorem ipsum dolor sit amet.",
        "icon": ":material-github:",
        "sub_title": "2022-Q3"
    },
    {
        "title": "Three",
        "content": "Lorem ipsum dolor sit amet.",
        "key": "pink",
        "sub_title": "2022-Q4"
    }
]

::/timeline::