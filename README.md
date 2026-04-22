# OpenAI Codex — Starter Boilerplate

> Ready-to-use `AGENTS.md` for your project. Clone, copy, edit.

Part of [agent-anatomy](https://github.com/agent-anatomy) — boilerplates for every AI coding agent.

📊 **[View diagram →](https://agent-anatomy.github.io/graphics/codex.html)**

---

## Usage

```bash
# Install or upgrade Codex CLI
npm i -g @openai/codex@latest
# or: brew install --cask codex

git clone https://github.com/agent-anatomy/codex.git .codex-boilerplate
cp .codex-boilerplate/AGENTS.md ./AGENTS.md
# Optional: scoped instructions for a real subtree in your repo
mkdir -p ./src
cp .codex-boilerplate/src/AGENTS.md ./src/AGENTS.md
rm -rf .codex-boilerplate

# Verify Codex is loading your instructions
codex --ask-for-approval never "Summarize the current instructions."
```

Then edit `AGENTS.md` to match your project before relying on it. Replace the
commented command block with real commands that already succeed in your repo,
and delete any sections that do not apply.

---

## What's included

```
AGENTS.md                          ← root project instructions, discovered from the repo root
src/
└── AGENTS.md                      ← example scoped instructions, appended when Codex runs under src/
```

---

## What is AGENTS.md?

`AGENTS.md` is the shared project instruction file for
[OpenAI Codex](https://developers.openai.com/codex/guides/agents-md). Codex
reads it automatically when it builds the instruction chain for a run or TUI
session. In each directory, Codex checks `AGENTS.override.md` first, then
`AGENTS.md`, then any fallback filenames configured in Codex settings.

Equivalent to `CLAUDE.md` for Claude Code, or `.windsurfrules` for Windsurf.

**What to put in AGENTS.md:**
- Project description
- Exact commands that already work in the repo
- Architecture or directory map
- Coding conventions and workflow rules
- Files and paths Codex must never modify
- Nested `AGENTS.md` files only where a subtree needs narrower guidance

---

## Hierarchical AGENTS.md

Codex supports multiple `AGENTS.md` files. It discovers them from the project
root down to the current working directory, and files closer to the working
directory override broader guidance because they are appended later. In any one
directory, `AGENTS.override.md` wins over `AGENTS.md`.

```
project/
├── AGENTS.md          ← repository-wide guidance
├── src/
│   └── AGENTS.md      ← appended when working in src/
└── packages/
    └── api/
        └── AGENTS.md  ← appended after broader files when working here
```

Use this for monorepos or large repos where one subtree needs narrower rules
than the rest of the project.

Keep the combined instruction chain concise. Codex truncates project guidance at
the configured `project_doc_max_bytes` limit, which defaults to 32 KiB.

---

## What to commit vs gitignore

| File | Commit? |
|------|---------|
| `AGENTS.md` | ✅ Yes |
| Subdirectory `AGENTS.md` | ✅ Yes |
| `AGENTS.override.md` | Usually no — it shadows the normal file in the same directory |

---

## FAQ

**Does Codex read AGENTS.md automatically?**
Yes. Codex discovers instruction files automatically at the start of each run or
TUI session.

**What's the difference between AGENTS.md and a system prompt?**
`AGENTS.md` is project-scoped and committed to git — your whole team benefits. A system prompt is personal and session-specific.

**Can I have AGENTS.md in subdirectories?**
Yes. Codex walks from the project root to your current directory and includes at
most one instruction file per directory.

**Should AGENTS.md have exact commands or just descriptions?**
Exact commands. Write `pnpm test --filter api` or `make -C services/api test`,
not "run the tests". Codex executes what you write.

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
