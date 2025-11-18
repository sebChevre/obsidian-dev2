
# ✅ **Solution 1 : Utiliser plusieurs remotes dans le même repository Git**

Git permet d’ajouter plusieurs remotes à un même dossier :

```bash
git remote add origin https://github.com/ton-compte/repo1.git
git remote add backup https://github.com/ton-compte/repo2.git
```

Ensuite tu peux pousser vers les deux :

```bash
git push origin main
git push backup main
```

### ✔️ Fonctionne avec Obsidian Git ?

Partiellement.

Le plugin _Obsidian Git_ n’effectue un **push automatique que vers `origin`**.  
Pour pousser vers les autres remotes, tu dois :

- soit lancer manuellement `git push backup main` via un terminal dans ton vault
    
- soit écrire un **script externe** qui sera exécuté automatiquement
    

---

# ✅ **Solution 2 : Utiliser un remote “multiple” via Git**

Git permet aussi ceci :

```bash
git remote set-url --add origin https://github.com/ton-compte/repo1.git
git remote set-url --add origin https://github.com/ton-compte/repo2.git
```

Ensuite un simple :

```bash
git push origin main
```

…pousse **vers tous les URLs du remote origin**.

### ✔️ Fonctionne avec Obsidian Git ?

**Oui !**  
C’est la méthode la plus simple pour rester compatible avec le push automatique du plugin.

⚠️ Attention : si l’un des deux remotes échoue, le push complet échoue.

---

# 🏁 **Conclusion**

- Le plugin _Obsidian Git_ ne supporte **pas nativement** plusieurs remotes.
    
- ➤ **Solution recommandée : mettre plusieurs URLs sur le remote `origin`**  
    → ainsi `Obsidian Git` les poussera tous automatiquement.
    
- Sinon, tu peux gérer manuellement des remotes séparés.
    

---

Si tu veux, je peux t’écrire :

- commands exactes selon ta configuration
    
- un script de synchronisation automatique
    
- ou t’expliquer comment vérifier tes remotes actuels.