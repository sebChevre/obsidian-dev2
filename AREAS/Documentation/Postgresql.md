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
    file_name TEXT NOT NULL,
    obsidian_path TEXT NOT NULL,
    embedding VECTOR(3584)
);
```

```sql

CREATE EXTENSION IF NOT EXISTS "pgcrypto";

CREATE TABLE chat_memory (
    id SERIAL PRIMARY KEY,
    session_id UUID NOT NULL DEFAULT gen_random_uuid(),
    created_at TIMESTAMP DEFAULT NOW(),
    isActive BOOLEAN DEFAULT TRUE
);

CREATE TABLE chat_message (
    id SERIAL PRIMARY KEY,
    chat_memory_id INT REFERENCES chat_memory(id) ON DELETE CASCADE,
    role TEXT NOT NULL,
    content TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT NOW()
);
```

### Ajout extension `vector`
```sql
CREATE EXTENSION IF NOT EXISTS vector;
```

### Supression de la table

```sql
DROP TABLE documents;
```

### Requêtes diverses

```sql
UPDATE chat_memory SET isactive = FALSE

```
