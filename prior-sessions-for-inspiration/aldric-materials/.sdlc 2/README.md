# .sdlc/ — the SDLC state directory

This directory is the source of truth for your project's software development lifecycle. Skills in `.claude/skills/sdlc/` read and write these files.

## Files at this level

- **`PRODUCT_VISION.md`** — what & why. Hand-edited.
- **`TECH_VISION.md`** — how, globally (stack, principles). Hand-edited.
- **`EXISTING_FEATURES.md`** — what has shipped. Updated by `/sdlc:review`.
- **`ROADMAP.md`** — ordered intent. Hand-edited.
- **`INBOX.md`** — untriaged capture. Written by `/sdlc:capture`; drained by `/sdlc:plan` and `/sdlc:review`.

## Subdirectories

- **`designs/`** — standalone UX designs attached to inbox items that haven't been planned into an iteration yet.
- **`iterations/NNNN-<slug>/`** — one directory per iteration. Files inside: `plan.md`, `design.md` (optional), `qa.md`, `execute.md`, `review.md`.

## State

There is **no separate state file**. The current iteration is the most recent `iterations/NNNN-<slug>/` directory that does **not** contain a `review.md`. Once `review.md` exists, the iteration is closed.

## Skills

| Slash | Purpose |
|---|---|
| `/sdlc:capture <text>` | Append idea to `INBOX.md` |
| `/sdlc:plan [item]` | Compose an iteration |
| `/sdlc:design` | Attach UX info to a work item |
| `/sdlc:qa` | Define verification for the iteration's features |
| `/sdlc:execute` | Build TDD plan, dispatch subagent to implement |
| `/sdlc:review` | Interactive walkthrough, close iteration |
