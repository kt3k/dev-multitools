---
name: update-domain-docs
description: |
  Update or create DDD documentation based on the current state of the codebase.
  Generates bounded context maps, glossaries, and aggregate documentation.
---

## Update DDD Docs Skill

Generate or update Domain-Driven Design documentation to keep it in sync with the current codebase.

### Execution Flow

1. **Assess current state**: Check if DDD documentation already exists (e.g., `docs/ddd/`, `DOMAIN.md`, context maps, glossaries). Read the codebase to understand the current domain model.

2. **Generate/update documents**:

   - **Context Map** (`docs/ddd/context-map.md`):
     - List all bounded contexts discovered in the codebase
     - Document relationships between contexts (upstream/downstream, shared kernel, anti-corruption layer, etc.)
     - Note integration patterns used

   - **Glossary** (`docs/ddd/glossary.md`):
     - Canonical list of ubiquitous language terms with definitions
     - Update from current code — add new terms, remove obsolete ones, fix inconsistencies

   - **Aggregate Documentation** (`docs/ddd/aggregates/`):
     - One file per aggregate root
     - Document: purpose, invariants, entities contained, value objects, domain events emitted
     - Include key code references

3. **Diff and confirm**: Before writing, show the user what will be created or changed. Apply changes only after approval.

### Output Structure

```
docs/ddd/
├── context-map.md
├── glossary.md
└── aggregates/
    ├── <aggregate-1>.md
    ├── <aggregate-2>.md
    └── ...
```

### Guidelines

- Keep documentation concise and developer-focused — not academic.
- Reference actual code paths so docs stay grounded.
- If existing DDD docs are found, update them incrementally rather than replacing wholesale.
- Always ask for user confirmation before writing files.
