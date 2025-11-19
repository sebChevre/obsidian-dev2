---
created: 2025-11-19 - 18:16
tags:
  - zippo
---
- mise à jour liste entreprise
- import_anapol, correction clé fk type_mesure, et ajout ramoneur fk
- update installation (forcer la valeur boolèenne)
- maj mig_controle
- instalations merge avec cycle_vie, on a uniquement 2 comme fk (alors 3,4,5...)
	- Installations a lancer en prod sur le test
- insert localisaton (check phil)
- SyncMigrationScript .dev !!!

# Check dev<-> test

- table localite : test: no_ofs null: ok


# Gestion des localisations
- [x] tbd, à définir selon info Phil ✅ 2025-11-07


# Migration 25.09.2025
- [x] Gestion des étiquettes ✅ 2025-11-07
  - Import depuis Orcale
  - Si valeur nulle pour mesure, créer la mesure pour le type avec valeur 0

