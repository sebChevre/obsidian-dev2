---
tags:
  - Microsoft
  - Middleware
  - Surveiller
  - Plateformes
---
# Microsoft BizTalk
<!-- description/short {start} -->
BizTalk est une plateforme logicielle de Microsoft, conçue pour l’intégration d’applications d’entreprise (EAI, Enterprise Application Integration).
<!-- description/short {end} -->

## Description
> BizTalk est une plateforme logicielle de Microsoft, conçue pour l’intégration d’applications d’entreprise (EAI, Enterprise Application Integration).

## Fonctionnalités principales

- *Intégration* : Connecte des applications disparates (SAP, Oracle, SQL Server, systèmes mainframe, etc.).

- *Orchestration* : Permet de modéliser, exécuter et automatiser des processus métiers complexes.

- *Messaging* : Utilise un moteur de messagerie basé sur XML pour échanger des données entre systèmes.

- *Adaptateurs* : Fournit de nombreux connectors (SAP, FTP, HTTP, SMTP, SQL Server, etc.) pour s’interfacer facilement avec d’autres technologies.

- *Surveillance & gestion* : Offre des outils pour suivre les flux, diagnostiquer des erreurs et gérer les échanges.

## Cas d’usage

Une entreprise qui utilise SAP pour la gestion de production et Salesforce pour la gestion client peut synchroniser les données automatiquement via BizTalk.

Une banque peut utiliser BizTalk pour faire communiquer un système mainframe ancien avec de nouvelles applications web.

Intégration avec des services cloud via Azure Logic Apps (Microsoft a progressivement rapproché BizTalk et Azure dans une stratégie hybride).

## Roadmap

::gantt:: no-weeks no-quarters month-width=20

- title: Jalons
  events:
    - title: Fin support Mainstream
      time: 2028-04-01
      icon: ":octicons-rocket-16:"
    - title: Fin support étendu
      time: 2030-04-01
      icon: ":octicons-sun-16:"
- title: BizTalk Server 2020
  activities:
  - title: Support mainstream
    start: 2025-01-01
    end: 2028-04-01
  - title: Support étendu
    start: 2028-04-01
    end: 2030-04-01

- title: Brasserie
  activities:
  - title: Mise en place initiale
    start: 2023-01-01
    end: 2030-01-01

::/gantt::

## Décisions

::timeline::

[
     {
        "title": "Brasserie",
        "content": "MEP Brasserie. Suppression des transformations dans BizTalk",
        "icon": ":fontawesome-rocket:",
        "sub_title": "2023"
    },
    {
        "title": "BizTalk Server 2020",
        "content": "Version actuelle.",
        "icon": ":fontawesome-rocket:",
        "sub_title": "Aujourd'hui"
    }
]

::/timeline::