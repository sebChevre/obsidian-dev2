---
tags:
  - Infrastructure
  - Plateformes
  - Surveiller
---
# Microsoft Active Directory  
<!-- description/short {start} -->
Microsoft Active Directory est une plateforme d’annuaire centralisé permettant la gestion des identités, des accès et des politiques de sécurité au sein de l’infrastructure de la RCJU.  
Elle constitue le socle d’authentification et d’autorisation pour l’ensemble des services et systèmes internes.  
<!-- description/short {end} -->

## Description  
Microsoft Active Directory (AD) est une **plateforme d’annuaire et d’authentification** intégrée au système Windows Server.  
Elle fournit les services fondamentaux de **gestion des identités, des comptes utilisateurs, des groupes, des ordinateurs et des politiques de sécurité (GPO)** au sein du domaine RCJU.  

AD repose sur les protocoles **LDAP**, **Kerberos** et **DNS**, et assure une authentification sécurisée ainsi qu’une délégation des droits d’accès aux ressources internes (fichiers, applications, impressions, etc.).  
La solution est **hautement disponible**, répliquée sur plusieurs contrôleurs de domaine, et intégrée avec les services de fédération (ADFS) et de synchronisation vers **Entra ID (Azure AD)** pour les usages hybrides.  

Active Directory constitue le **socle d’identité et de confiance de l’infrastructure** de la RCJU, garantissant une gestion centralisée, sécurisée et cohérente des accès à l’ensemble des systèmes internes.


## Périmètre d'utilisation