---
created: 2025-11-13 - 07-14
tags:
 - git
---
## Appliquer un fichier `.gitignore` après coup




### 1. Modifier ton `.gitignore`

Assure-toi qu’il contient bien les bons chemins/patterns à ignorer.  
Exemple :

```gitignore
# Ignorer les fichiers de logs
*.log

# Ignorer le dossier build
/build/

# Ignorer les fichiers temporaires
*.tmp
```

### 2. Mise à jour

```bash
git rm -r --cached .
git add .
git commit -m "Appliquer .gitignore après coup"
```

## Supprimer les tags gits

### Supprime tous les tags locaux
```
git tag -d $(git tag -l)
```


### Supprimer du dépôt distant (origin)
```
git push origin --delete $(git tag -l)
```

