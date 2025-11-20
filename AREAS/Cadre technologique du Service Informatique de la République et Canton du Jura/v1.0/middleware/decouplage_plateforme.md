---
tags:
  - Middleware
  - Principes
  - Adopter

---
# Découplage des plateformes intégrées
<!-- description/short {start} -->
Le principe de découplage des plateformes intégrées consiste à garantir l’indépendance et l’évolutivité de chaque système via des interfaces clairement définies, afin de préserver la souplesse, la maintenabilité et la résilience du SI.
<!-- description/short {end} -->

## Description
Le principe de **découplage des plateformes intégrées** vise à éviter les **dépendances fortes ou bidirectionnelles** entre deux systèmes applicatifs ou technologiques.  
Chaque plateforme doit être capable de **fonctionner, évoluer et être remplacée indépendamment** des autres, via des interfaces et des contrats d’échange bien définis.  
Ce principe est essentiel pour assurer la **souplesse du SI**, faciliter la **modernisation progressive**, et réduire le **risque d’effet domino** lors d’une évolution technique ou d’une migration.  
Dans le contexte RCJU, ce principe prend toute son importance face aux intégrations où un couplage bidirectionnel crée une dépendance mutuelle difficile à maintenir.

- **I. Isolation fonctionnelle et technique**  
  > Concevoir chaque plateforme comme un composant indépendant, disposant de son propre cycle de vie.  
  > Éviter les dépendances croisées (ex. un système qui héberge à la fois la logique métier et la présentation d’un autre).

- **II. Communication par interfaces standardisées**  
  > Utiliser des APIs REST, des connecteurs standards ou des bus d’intégration pour échanger des données.  
  > Documenter et versionner les contrats d’interface pour garantir la compatibilité dans le temps.

- **III. Réduction des dépendances bidirectionnelles**  
  > Interdire ou limiter les intégrations circulaires (ex. SharePoint consommé par K2 et hébergeant en retour des composants K2).  
  > Favoriser des schémas de communication unidirectionnels et asynchrones.

- **IV. Autonomie des cycles de vie**  
  > Chaque plateforme doit pouvoir être mise à jour ou remplacée sans impacter le fonctionnement des autres.  
  > Les dépendances fortes doivent être identifiées, documentées et accompagnées d’un plan de désimbriquement.

- **V. Interopérabilité et pérennité**  
  > Privilégier les architectures orientées services (SOA, microservices, API-first).  
  > Éviter les connecteurs propriétaires et favoriser les standards ouverts (REST, JSON, OData, OAuth2).

- **VI. Gouvernance des intégrations**  
  > Soumettre tout couplage technique à une revue d’architecture.  
  > Mettre en place une cartographie des dépendances applicatives et la maintenir à jour.

---

### ⚠️ Recommandation stratégique RCJU
> Le **découplage des plateformes intégrées** est une condition indispensable à la **maîtrise du patrimoine applicatif** et à la **modernisation du SI RCJU**.  
> Les solutions fortement couplées doivent être **identifiées**, **contenues** et **désimbriquées** progressivement au profit d’architectures **interopérables et modulaire**.  
> Ce principe doit guider les décisions d’acquisition, d’intégration et de développement logiciel.