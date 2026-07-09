# Mario Relational Database

> PostgreSQL relational database for the Mario universe — one-to-one, one-to-many, and many-to-many relationships. freeCodeCamp certification.

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

## About

Built as part of freeCodeCamp's **Relational Databases** certification. A complete PostgreSQL database modeling the Mario universe, covering all major relationship types and database design concepts step by step.

## Features

- **One-to-one** — `characters` ↔ `more_info` (enforced via `UNIQUE NOT NULL` foreign key).
- **One-to-many** — `characters` → `sounds` (a character can have many sounds).
- **Many-to-many** — `characters` ↔ `actions` via the `character_actions` junction table.
- Full normalization — no duplicated data, referential integrity throughout.
- `SERIAL` columns, sequences, composite primary keys, `UNIQUE` and `NOT NULL` constraints.

## Project Structure

```
fcc-mario-database/
└── mario_database.sql   Full schema: tables, keys, constraints, sequences, and sample data
```

## Entity-Relationship Overview

```
characters(character_id PK)
  ├─ 1:1  more_info(more_info_id PK, character_id FK UNIQUE)
  ├─ 1:∞  sounds(sound_id PK, character_id FK)
  └─ ∞:∞  actions(action_id PK) via character_actions(character_id FK, action_id FK)
```

## Setup

**Requirements:** PostgreSQL, `psql` CLI.

```bash
psql -d mario_database -f mario_database.sql
```

---

**Alejandro Oviedo** · [LinkedIn](https://www.linkedin.com/in/aleoviedo071298/) · [GitHub](https://github.com/aleoviedo071298)
