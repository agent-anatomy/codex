# OpenAI Codex — Starter Boilerplate

> Ready-to-use `AGENTS.md` for your project. Clone, copy, edit.

Part of [agent-anatomy](https://github.com/agent-anatomy) — boilerplates for every AI coding agent.

---

## Usage

```bash
git clone https://github.com/agent-anatomy/codex.git .codex-boilerplate

cp .codex-boilerplate/AGENTS.md ./AGENTS.md

# Optional: copy subdirectory AGENTS.md for monorepos
cp .codex-boilerplate/src/AGENTS.md ./src/AGENTS.md

rm -rf .codex-boilerplate
```

Then edit `AGENTS.md` to match your project.

---

## What's included

```
AGENTS.md                          ← root instructions, always read
src/
└── AGENTS.md                      ← example scoped instructions for a subtree
```

---

## What to commit vs gitignore

| File | Commit? |
|------|---------|
| `AGENTS.md` | ✅ Yes |
| `src/AGENTS.md` | ✅ Yes |

---

## Other agents

| Agent | Boilerplate |
|-------|-------------|
| Claude Code | [agent-anatomy/claude](https://github.com/agent-anatomy/claude) |
| Cursor | [agent-anatomy/cursor](https://github.com/agent-anatomy/cursor) |
| Windsurf | [agent-anatomy/windsurf](https://github.com/agent-anatomy/windsurf) |
| More... | [agent-anatomy](https://github.com/agent-anatomy) |
