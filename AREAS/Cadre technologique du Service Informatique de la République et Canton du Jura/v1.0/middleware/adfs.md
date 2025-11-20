---
tags:
  - Microsoft
  - Middleware
  - Plateformes
  - Adopter
---
# Active Directory Federation Services (ADFS)  
<!-- description/short {start} -->
Active Directory Federation Services (ADFS) est une plateforme de fédération d’identités permettant l’authentification unique (SSO) et la délégation de confiance entre l’infrastructure interne de la RCJU et des services externes.  
Elle assure la continuité de l’identité entre Active Directory et les applications internes ou cloud.  
<!-- description/short {end} -->

## Description  
Active Directory Federation Services (ADFS) est un **service de fédération d’identité** fourni par Microsoft, qui permet aux utilisateurs de la RCJU d’accéder à des applications internes et externes via une authentification unique (SSO).  

ADFS s’appuie sur **Active Directory** comme source d’identité et utilise des protocoles standard tels que **SAML**, **WS-Federation** et **OAuth** pour établir des relations de confiance (trusts) avec d’autres systèmes ou services cloud.  
Il gère les **flux d’authentification et d’autorisation** sans nécessiter la duplication des identités dans des environnements externes.  

ADFS constitue la **couche intermédiaire de fédération** entre l’annuaire interne (AD) et les services cloud (tels qu’Entra ID, Microsoft 365 ou d’autres SaaS).  
Il joue un rôle essentiel dans la **sécurité, la cohérence et la continuité** de l’identité numérique au sein de l’écosystème hybride de la RCJU.
