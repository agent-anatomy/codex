# AGENTS.md

Use this file as a starting point, then replace the generic guidance with
repository-specific instructions before committing it to a real project. Codex
reads this file literally. Delete sections that do not apply instead of leaving
generic text behind.

## Project

Describe the repository in 2-3 sentences:

- What does this project ship?
- Who uses it?
- What outcome should Codex optimize for when making changes?

## Stack

- Language:
- Framework or runtime:
- Package manager:
- Database:
- Key tools and services:

## Commands

List only commands that already succeed from the repository root. If a command
must run from a subdirectory, write the full command so Codex can execute it
literally.

```bash
# Replace each comment below with the exact command your team uses.
# Install dependencies
# Start the main development workflow
# Run the fastest test loop for common changes
# Run the full verification gate before opening a PR
# Build production artifacts
```

Do not leave sample commands in a real project. If a command does not apply,
delete the line instead of keeping vague guidance such as "run the tests".

## Architecture

- `src/` — application source
- `tests/` — automated tests
- Document the other top-level directories Codex will need to navigate

## Rules

- Follow the existing code style and naming patterns in touched files.
- Keep changes scoped to the task; do not refactor unrelated code without a
  clear reason.
- Add or update tests when behavior changes.
- Use only the exact commands listed above; do not invent replacement commands.
- Say explicitly when a required command cannot be run in the current
  environment.
- Add narrower instructions in nested `AGENTS.md` files when a subtree needs
  extra guidance.
- Use `AGENTS.override.md` only for a stronger same-directory override; it
  replaces `AGENTS.md` in that directory.

## Do not touch

- List generated code, vendored code, lockfiles, credentials, production data,
  or any other paths Codex must avoid
