# Mario Relational Database (PostgreSQL)

A complete PostgreSQL relational database project inspired by the Mario universe,
built as part of freeCodeCamp's Relational Databases certification.
`mario_database.sql` contains the full schema, relationships, constraints,
sequences, and data.

## Contents

- `mario_database.sql` — full database dump:
  - Tables: `characters`, `more_info`, `sounds`, `actions`, `character_actions` (junction table)
  - Primary keys & composite keys
  - Foreign keys, unique and `NOT NULL` constraints
  - Sequences for `SERIAL` columns
  - Sample data for all characters, actions, sounds, and info

## Database Features

- **One-to-one** — `characters` ↔ `more_info`, enforced via a `UNIQUE NOT NULL` foreign key.
- **One-to-many** — `characters` → `sounds`: a character can have many sounds.
- **Many-to-many** — `characters` ↔ `actions`, implemented via the `character_actions` junction table.
- **Full normalization** — no duplicated data, clear foreign keys, meaningful column names, referential integrity.

## Entity-Relationship Overview

```
characters(character_id PK)
more_info(more_info_id PK, character_id FK UNIQUE NOT NULL)
actions(action_id PK)
sounds(sound_id PK, character_id FK)
character_actions(character_id FK, action_id FK, PRIMARY KEY(character_id, action_id))
```

- `characters` 1 → 1 `more_info`
- `characters` 1 → ∞ `sounds`
- `characters` ∞ → ∞ `actions` (via `character_actions`)

## How to Restore

```bash
psql -d mario_database -f mario_database.sql
```

## About This Project

Built step-by-step while completing freeCodeCamp's Relational Databases
certification, covering table creation, `SERIAL`/sequences, primary and composite
keys, unique/`NOT NULL` constraints, foreign keys, joins, and relational modeling.

## Author

**Alejandro Oviedo**
Comodoro Rivadavia, Argentina
[github.com/aleoviedo071298](https://github.com/aleoviedo071298)
