# 🎮 Mario Relational Database (PostgreSQL)

This repository contains a complete PostgreSQL relational database project inspired by the Mario universe.  
It was created as part of the **FreeCodeCamp – Relational Databases** course.

The file **`mario_database.sql`** includes the full schema, table structure, relationships, constraints, sequences, and all data.

---

## 📂 Contents

- `mario_database.sql` — Full database dump:
  - Tables
    - `characters`
    - `more_info`
    - `sounds`
    - `actions`
    - `character_actions` (junction table)
  - Primary keys & composite keys
  - Foreign keys
  - Unique constraints
  - NOT NULL constraints
  - Sequences for SERIAL columns
  - Inserted data for all characters, actions, sounds, and info

---

## 🛠️ Database Features

### ✔️ One-to-One Relationship
- `characters` ↔ `more_info`  
  Enforced through a UNIQUE + NOT NULL foreign key.

### ✔️ One-to-Many Relationship
- `characters` → `sounds`  
  A character can have many sounds.

### ✔️ Many-to-Many Relationship
- `characters` ↔ `actions`  
  Implemented using the `character_actions` junction table.

### ✔️ Full Normalization
- No duplicated data  
- Clear foreign keys  
- Meaningful column names  
- Referential integrity ensured

---

## 🚀 How to Restore This Database

1. Make sure PostgreSQL is installed.
2. Create a new empty database (optional):
3. Restore the dump:

psql -d mario_database -f mario_database.sql

That’s it — the schema, relationships, and data will be fully restored.

## 📊 Entity-Relationship Overview

**Tables:**

* `characters(character_id PK)`
* `more_info(more_info_id PK, character_id FK UNIQUE NOT NULL)`
* `actions(action_id PK)`
* `sounds(sound_id PK, character_id FK)`
* `character_actions(character_id FK, action_id FK, PRIMARY KEY(character_id, action_id))`

**Relationships:**

* `characters` 1 → 1 `more_info`
* `characters` 1 → ∞ `sounds`
* `characters` ∞ → ∞ `actions` via `character_actions`

---

## 📘 About This Project

This database was created step-by-step while completing FreeCodeCamp’s **Relational Databases** certification.
It demonstrates:

* Table creation
* Adding/altering columns
* SERIAL and sequences
* Primary keys and composite keys
* UNIQUE and NOT NULL constraints
* Foreign keys and cascading relations
* JOIN operations
* Relational modeling

Perfect for portfolio use and demonstrating SQL + PostgreSQL skills.

---

## 👤 Author

**Alejandro Oviedo**
📍 Comodoro Rivadavia, Argentina
GitHub: [https://github.com/aleoviedo071298](https://github.com/aleoviedo071298)

---
