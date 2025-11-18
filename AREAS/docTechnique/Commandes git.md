## Opérations de bases

* **Initialisation**  
```
git init
```

- **Status**
```
git status
```

- **Ajout de fichier staging area**gg
```
git add . //tous les fichiers git add ligne.php //le fichier spécifié
```

* **Commit sur repo local**
```
git commit -m "Initial commit"
```

- **Consultation des logs**
```
git log
```

## Repository distant

- **Définition du repository**
```
git remote add origin https://github.com/SVG-TUD.git
```

- Pousser sur repo distant
```
git push -u origin master //u garde les paramètres
```

- Tirer le repo distant
```
git pull origin master //on va d'abord récupérer ce qui existe sur le repo
```

### Différences

- Diff entre modification et repo local
```
git diff HEAD
```
