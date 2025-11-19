---
created: 2025-11-14 - 10-06
tags:
- data
---



# Démarrer un processus de gestion des données avec des moyens simples

## 1️⃣ Poser les bases – Identifier et cartographier les données
**Objectif** : savoir *quoi* on a, *où* ça se trouve, et *qui* l’utilise.

- **Inventaire des sources** :  
  - Bases de données (SQL Server, MySQL, etc.).
  - Bibliothèques SharePoint (documents bureautiques, PDF…).
  - Fichiers partagés sur d’autres plateformes éventuelles.
- **Points clés à noter** pour chaque source :  
  - Propriétaire ou responsable.
  - Type de données (clients, finances, RH, technique…).
  - Sensibilité (confidentiel, public interne…).
  - Format (CSV, DOCX, base relationnelle…).

**Outils simples** :  
- Excel / Google Sheets pour le premier inventaire.  
- PowerShell ou scripts simples pour lister automatiquement les bibliothèques SharePoint.  
- Diagrammes gratuits (ex. draw.io) pour visualiser les flux et connexions.

---

## 2️⃣ Définir la gouvernance minimale
**Objectif** : éviter le chaos en définissant quelques règles de base.

- **Rôles** :
  - **Propriétaire de données** : responsable métier du contenu.
  - **Gestionnaire technique** : s’assure de la disponibilité et sécurité.
- **Règles simples** :
  - Qui peut créer, modifier, supprimer ?
  - Où stocker quel type de fichier ?
  - Quelles conventions de nommage appliquer ?
- **Cycle de vie minimal** :
  - Archivage après X années.
  - Suppression ou anonymisation pour les données sensibles.

**Outils simples** :  
- Un document Word ou Wiki interne sur SharePoint pour publier les règles.  
- Modèles de dossiers et nomenclatures dans SharePoint.

---

## 3️⃣ Mettre en place un stockage organisé et centralisé
**Objectif** : créer *un seul endroit clair* par type de données.

- **SharePoint** :
  - Structurer en bibliothèques par domaine métier.
  - Utiliser des métadonnées (catégorie, date, statut) plutôt que de multiplier les dossiers.
- **Bases de données** :
  - Centraliser les connexions dans un inventaire sécurisé.
  - Documenter la structure (schémas, tables, relations).

**Outils simples** :  
- SharePoint natif (bibliothèques, vues filtrées).  
- Diagrammes ERD gratuits (dbdiagram.io) pour les bases.

---

## 4️⃣ Documenter et rendre accessible
**Objectif** : que toute personne sache *comment* trouver et utiliser les données.

- **Fiche d’identité des données** :
  - Nom de la source.
  - Description.
  - Responsable.
  - Accès (lien ou procédure).
- **Petit catalogue de données** :
  - Tableau simple avec toutes les fiches.
  - Hébergé sur SharePoint ou OneNote.

**Outils simples** :  
- Excel/SharePoint List comme "mini data catalog".  
- Microsoft Lists pour un suivi dynamique.

---

## 5️⃣ Lancer la démarche qualité et sécurité
**Objectif** : assurer que les données soient fiables et protégées.

- **Qualité** :
  - Détecter les doublons.
  - Standardiser certains champs (dates, noms…).
- **Sécurité** :
  - Vérifier les droits d’accès SharePoint.
  - Séparer données sensibles (ex. RH) dans des bibliothèques protégées.
- **Sauvegardes** :
  - Vérifier les politiques de backup existantes.

**Outils simples** :  
- Microsoft Purview (si inclus dans la licence Microsoft 365) pour classification automatique.  
- Scripts simples pour contrôle d’intégrité.

---

## 6️⃣ Commencer petit, mais durable
- Démarrer par **un périmètre pilote** (ex. un service métier) avant de généraliser.
- Prévoir une **réunion mensuelle** avec les responsables pour ajuster.
- Rester sur des outils déjà disponibles dans Microsoft 365 pour limiter les coûts.
