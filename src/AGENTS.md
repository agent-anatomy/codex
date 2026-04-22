# src/AGENTS.md

This file is a scoped example. Codex reads the repository root `AGENTS.md`
first, then this file when the current working directory is `src/` or any
descendant of `src/`. Keep scoped files short and only describe rules that are
different from, or more specific than, the root instructions.

If `src/AGENTS.override.md` exists, Codex uses that file instead of
`src/AGENTS.md` for the `src/` directory. If a deeper directory also has its
own `AGENTS.md`, Codex appends that deeper file after this one.

## Scope

- Applies only to code under `src/`
- Assumes the root `AGENTS.md` already defines repository-wide commands, merge
  gates, and do-not-touch paths
- Should not repeat broad repository rules unless this subtree intentionally
  changes them

## Structure

- `src/api/` — transport layer, request parsing, response formatting
- `src/domain/` — business logic and use cases
- `src/lib/` — shared utilities, clients, and adapters
- `src/types/` — shared types and schemas

## Rules

- Validate untrusted input at the boundary before it reaches domain logic.
- Keep route or handler files thin; move reusable logic into `src/domain/` or
  `src/lib/`.
- Prefer deterministic unit tests for domain logic and integration tests for
  boundary layers.
- If `src/` needs a narrower command than the root file, put the exact command
  here instead of weakening the repository-wide rule.
