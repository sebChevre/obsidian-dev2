# 🧠 Arbre sémantique pour un projet RAG – Conducteurs et élèves conducteurs (OVJ)

## Thèmes et catégories sémantiques

Voici les **niveaux d’un arbre sémantique** adapté, avec exemples de mots-clés à intégrer au moment du *tagging* ou de l’indexation.

---

### 1. 📄 Demand​es administratives

- Permis d’élève  
- Permis de conduire  
- Autorisation professionnelle  
- Formulaires PDF (inscription, duplicata, échange)  
- Demande d’échange de permis étranger  

**Mots-clés** :  
`demande`, `formulaire`, `autorisation`, `permis probatoire`, `duplicata`, `perte`, `vol`, `modification`, `authenticité`

---

### 2. 👩‍⚕️ Conditions préalables

- Cours de premiers secours  
- Examen de la vue  
- Extrait du casier judiciaire  
- Certificat médical niveau 2  

**Mots-clés** :  
`prérequis`, `certificat médical`, `cours sauveteur`, `premiers secours`, `opticien`, `vision`, `identité`, `justificatif`, `photo passeport`

---

### 3. 🧪 Examens

#### Théoriques :
- Examen de base  
- Examen professionnel OACP  
- Théorie en ligne / orale / questionnaire

#### Pratiques :
- Catégories : A, B, C, D, etc.  
- Parcours d’équilibre moto  
- Conditions d’admission  
- Annulation ou report

**Mots-clés** :  
`examen`, `théorique`, `pratique`, `catégorie`, `OACP`, `convocation`, `test`, `rendez-vous`, `reprise`, `instruction pratique`, `échec`

---

### 4. 🛵 Véhicules & équipement

- Véhicule conforme  
- Equipement de sécurité  
- Vérifications techniques (pneus, lumières, freinage, etc.)

**Mots-clés** :  
`véhicule`, `moto`, `équipement`, `casque`, `frein`, `rétroviseur`, `pneus`, `chaîne`, `catégorie B`, `instruction`

---

### 5. 🌍 Permis étrangers / internationaux

- Échange de permis étrangers  
- Pays du tableau A et B (dispenses)  
- Permis de conduire international

**Mots-clés** :  
`étranger`, `international`, `traduction`, `pays`, `certificat d’authenticité`, `frontaliers`, `permis bleu`, `format carte de crédit`

---

### 6. 📚 Supports pédagogiques

- Clés USB  
- Livres de théorie  
- Plateformes de formation en ligne

**Mots-clés** :  
`moyens didactiques`, `livre`, `théorie`, `USB`, `fahrschultheorie`, `formation`

---

### 7. 🔁 Changements et formalités

- Changement d’adresse ou de nom  
- Mise à jour de documents

**Mots-clés** :  
`changement`, `adresse`, `nom`, `domicile`, `modification`

---

### 8. 🧾 Paiements / émoluments

- Coûts pour duplicata, consultations, examens  
- Moyens de paiement

**Mots-clés** :  
`émolument`, `tarif`, `paiement`, `frais`, `facture`, `guichet`

---

## 🔎 Recommandations pour usage RAG

Pour exploiter ces éléments dans un projet de classification :

- **Chunking** des documents par section fonctionnelle (ex. : “Examen théorique”, “Conditions d’accès”).
- **Vectorisation + tagging** avec les mots-clés ci-dessus.
- Implémentation de **filtres sémantiques** dans l’index pour améliorer la récupération ciblée selon la catégorie de question (ex. : “Comment échanger mon permis marocain ?” → filtre `Permis étranger` + `Maroc`).

