# OpenAI Codex — Starter Boilerplate

> Ready-to-use `AGENTS.md` for your project. Clone, copy, edit.

Part of [agent-anatomy](https://github.com/agent-anatomy) — boilerplates for every AI coding agent.

📊 **[View diagram →](https://agent-anatomy.github.io/graphics/codex.html)**

---

## Usage

```bash
git clone https://github.com/agent-anatomy/codex.git .codex-boilerplate
cp .codex-boilerplate/AGENTS.md ./AGENTS.md
# Optional: scoped instructions for monorepos
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

## What is AGENTS.md?

`AGENTS.md` is the instruction file for OpenAI Codex CLI. Codex reads it automatically before every session — no configuration needed. It tells Codex what your project is, how to build and test it, and what rules to follow.

Equivalent to `CLAUDE.md` for Claude Code, or `.windsurfrules` for Windsurf.

**What to put in AGENTS.md:**
- Project description
- Exact build and test commands (not vague — write the exact command)
- Coding conventions
- Files Codex must never modify
- Monorepo structure if applicable

---

## Hierarchical AGENTS.md

Codex supports multiple `AGENTS.md` files. Root file always loads. Subdirectory files load when Codex works in that subtree.

```
project/
├── AGENTS.md          ← always loaded
├── src/
│   └── AGENTS.md      ← loaded when working in src/
└── packages/
    └── api/
        └── AGENTS.md  ← loaded when working in packages/api/
```

Use this for monorepos — each package gets its own scoped instructions.

---

## What to commit vs gitignore

| File | Commit? |
|------|---------|
| `AGENTS.md` | ✅ Yes |
| Subdirectory `AGENTS.md` | ✅ Yes |

---

## FAQ

**Does Codex read AGENTS.md automatically?**
Yes. Every session, no setup required.

**What's the difference between AGENTS.md and a system prompt?**
`AGENTS.md` is project-scoped and committed to git — your whole team benefits. A system prompt is personal and session-specific.

**Can I have AGENTS.md in subdirectories?**
Yes. Codex merges root + subdirectory instructions when working in that subtree.

**Should AGENTS.md have exact commands or just descriptions?**
Exact commands. Write `npm test` not "run the tests". Codex executes what you write.

---

## Other agents

| Agent | Boilerplate |
|-------|-------------|
| Claude Code | [agent-anatomy/claude](https://github.com/agent-anatomy/claude) |
| Cursor | [agent-anatomy/cursor](https://github.com/agent-anatomy/cursor) |
| Windsurf | [agent-anatomy/windsurf](https://github.com/agent-anatomy/windsurf) |
| GitHub Copilot | [agent-anatomy/copilot](https://github.com/agent-anatomy/copilot) |
| Aider | [agent-anatomy/aider](https://github.com/agent-anatomy/aider) |
| Gemini CLI | [agent-anatomy/gemini](https://github.com/agent-anatomy/gemini) |
