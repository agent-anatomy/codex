# src/ — Source Code

<!-- Scoped instructions for the src/ directory -->
<!-- These are merged with root AGENTS.md when Codex works in this subtree -->

## Structure
- `src/api/` — API routes and handlers
- `src/lib/` — shared utilities
- `src/types/` — TypeScript type definitions

## Rules
- No direct DB calls outside `src/lib/db/`
- All user input validated at the boundary in `src/api/`
- Keep business logic in `src/lib/`, not in route handlers
