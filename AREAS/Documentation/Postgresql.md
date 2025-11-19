---
created: 2025-11-18 - 08-21
tags:
- potgres
- documentation
---

*Utilisation de postgresql en tant que base de données vecteurs*

### Création de la table

```sql
-- Création de la table
CREATE TABLE documents (
    id SERIAL PRIMARY KEY,
    content TEXT NOT NULL,
    obsidian_path TEXT NOT NULL,
    embedding VECTOR(3584)
);
```

