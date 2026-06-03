# AGENTS: Skills Index

This repository is the central index and canonical source for agent skill documentation and implementation guidelines used across the AGENTS ecosystem.

Use this `README.md` as the starting point to discover, read, and update skill files. Each skill file documents domain knowledge, safe practices, and coding conventions for a focused area.

## Repo layout

- `core/` — core systems and shared skills (database, GUI, item handling).
- `platforms/` — platform-specific skills (PaperMC, FoliaMC, etc.).

Each skill file follows the pattern: `<scope>/<topic>.md` (for example: `core/database.md`).

## How to use

- Read the relevant skill file before changing implementation code.
- Keep the README as the central pointer: add new entries here when adding new skill files.
- Prefer focused, single-topic skill files over large multi-topic documents.

## Editing & contribution guidelines

- **Skill content:** keep guidance precise, cite sources for APIs, and include short, copyable examples when helpful.
- **File names:** use lowercase, hyphen-separated names (e.g., `gui_and_items.md`).
- **Commits:** use Conventional Commits. For docs, prefer `docs:` or `chore:` headers. Example: `docs: improve skills README index`.
- **Pull requests:** Link related issues, and describe the change's intent and any follow-ups required.

## Current skill index

- Platforms
  - `platforms/papermc.md` — concurrency and platform integration patterns for PaperMC.
  - `platforms/foliamc.md` — threading, RegionSchedulers, and strict concurrency rules for FoliaMC.

- Core Systems
  - `core/database.md` — async DB operations, pooling, and caching guidance.
  - `core/gui_and_items.md` — virtual inventory patterns, item serialization, and `PersistentDataContainer` rules.

## Notes for maintainers

- When adding a new skill file, add a short entry under "Current skill index" and update this README accordingly.
- This README is intentionally concise — skill files themselves should hold detailed, actionable instructions.

If you'd like, I can also add a CONTRIBUTING.md with templates and a PR checklist.
