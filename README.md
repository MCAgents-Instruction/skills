# AGENTS: Skills Index

This repository must be cloned under the `.agents/` directory. It is the central index and canonical source for agent skill documentation and implementation guidelines used across the AGENTS ecosystem.

Use this `README.md` as the starting point to discover and read skill files. Each skill file documents domain knowledge, safe practices, and coding conventions for a focused area.

## Directory layout

- `core/` — core systems and shared skills (database, GUI, item handling).
- `platforms/` — platform-specific skills (PaperMC, FoliaMC, etc.).

Each skill file follows the pattern: `<scope>/<topic>.md` (for example: `core/database.md`).

## How to use

- Read the relevant skill file before changing implementation code.
- Keep this README as the central pointer: add new entries here when adding new skill files.
- Prefer focused, single-topic skill files over large multi-topic documents.

## Current skills index

- Platforms
  - `platforms/papermc.md` — concurrency and platform integration patterns for PaperMC.
  - `platforms/foliamc.md` — threading, RegionSchedulers, and strict concurrency rules for FoliaMC.

- Core Systems
  - `core/database.md` — async DB operations, pooling, and caching guidance.
  - `core/gui_and_items.md` — virtual inventory patterns, item serialization, and `PersistentDataContainer` rules.
