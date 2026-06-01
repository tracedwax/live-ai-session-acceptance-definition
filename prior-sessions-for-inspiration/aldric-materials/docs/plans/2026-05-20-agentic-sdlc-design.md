# Agentic Skill-Based SDLC — Design

**Date:** 2026-05-20
**Status:** Design approved, ready for implementation
**Scope:** A very simple, skill-driven software development lifecycle for Claude Code, with deliberately recognizable file names so non-experts can navigate the artifacts.

## Goal

Provide a minimal set of Claude Code slash-skills that scaffold the thinking, tracking, and execution of work in a repo, backed by a small `.sdlc/` directory of plain-markdown state files. The system covers three lanes — product, UX, engineering — without becoming heavyweight.

## Directory layout

`.sdlc/` lives in the consumer repo and holds all state.

```
.sdlc/
├── PRODUCT_VISION.md      # what & why (hand-edited)
├── TECH_VISION.md         # how, globally (hand-edited)
├── EXISTING_FEATURES.md   # what's shipped (updated by /sdlc:review)
├── ROADMAP.md             # ordered intent (hand-edited)
├── INBOX.md               # untriaged capture (written by /sdlc:capture)
├── designs/
│   └── <slug>.md          # standalone UX designs, pre-iteration
└── iterations/
    └── NNNN-<slug>/
        ├── plan.md
        ├── design.md      # optional; UX only
        ├── qa.md
        ├── execute.md
        └── review.md      # presence = iteration closed
```

No `STATE.md`. Current iteration is inferred from the filesystem: the most recent `iterations/NNNN-<slug>/` directory without a `review.md`.

## Skill set

Six skills, all repo-local at `.claude/skills/sdlc/<name>/SKILL.md`.

| Skill | Purpose | Reads | Writes |
|---|---|---|---|
| `/sdlc:capture <text>` | One-shot append of an idea/bug/thought | — | `INBOX.md` |
| `/sdlc:plan [item]` | Compose an iteration. Optional argument seeds it. Suggests related inbox items. Creates iteration dir. | `INBOX.md`, `ROADMAP.md`, `PRODUCT_VISION.md` | `iterations/NNNN-<slug>/plan.md` (+ copies in design.md from `designs/`) |
| `/sdlc:design` | Attach UX/design info to a work item (inbox or plan). Adds `[design: <ref>]` marker on the linked item. | `INBOX.md` or active `plan.md` | `designs/<slug>.md` (pre-iteration) or `iterations/NNNN-<slug>/design.md` |
| `/sdlc:qa` | For each feature in the plan, define how to verify it works and how to know it plays nice with existing features. Prefers automated scripts. | active `plan.md`, `design.md` | `iterations/NNNN-<slug>/qa.md` |
| `/sdlc:execute` | Build ordered TDD plan (unit → integration → acceptance) with file/line-precise tests and code changes, then dispatch a subagent to execute. | active `plan.md`, `qa.md`, `TECH_VISION.md`, codebase | `iterations/NNNN-<slug>/execute.md`, then subagent runs |
| `/sdlc:review` | Interactive, feature-by-feature human walkthrough with narrow questions. Bugs route to inbox. Accepted features land in EXISTING_FEATURES. Closes iteration. | active iteration files | `review.md`, `EXISTING_FEATURES.md`, `INBOX.md` |

## Lifecycle example

```
/sdlc:capture "users want CSV export"
/sdlc:capture "loading spinner flickers"
/sdlc:capture "add dark mode"

/sdlc:design "dark mode"
  → designs/dark-mode.md (UX flow, palette, toggle placement)
  → INBOX item gets [design: dark-mode] marker

/sdlc:plan "dark mode and the spinner bug"
  → creates iterations/0001-dark-mode-and-polish/plan.md
  → copies designs/dark-mode.md into iteration as design.md
  → drained inbox items removed

/sdlc:qa
  → writes iterations/0001-dark-mode-and-polish/qa.md

/sdlc:execute
  → writes iterations/0001-dark-mode-and-polish/execute.md
  → dispatches subagent to TDD the iteration

/sdlc:review
  → walks each feature; narrow questions per feature
  → bugs → INBOX, accepted features → EXISTING_FEATURES.md
  → writes review.md (iteration is now closed)
```

## Conventions & decisions

- **Naming:** file names use plain words a non-expert can recognize. `qa.md` is acceptable jargon; user originally used it.
- **No gates:** skills *suggest* and *warn* but never block. If you want to QA without a plan, you can.
- **State inference:** the filesystem is the source of truth. Current iteration = most-recent `NNNN-<slug>/` lacking `review.md`.
- **Design pull behavior:** when `/sdlc:plan` adopts a `designs/<slug>.md`, it **copies** into the iteration and leaves the original. Two sources of truth is a known minor cost; we accept it for simplicity. Mitigation: skill notes "copied from designs/<slug>.md on YYYY-MM-DD" at the top of the iteration's `design.md`.
- **Unclosed iteration handling:** `/sdlc:plan` detects an open iteration (no `review.md`) and offers: close it first, force-start a new one, or cancel.
- **No `init` skill:** skills auto-create `.sdlc/` and subdirs on first use.
- **No standalone vision skills:** `PRODUCT_VISION.md` and `TECH_VISION.md` are hand-edited prose.
- **No shell helpers initially:** skills embed bash one-liners as needed. Windows equivalents added when a Windows-without-WSL user hits friction.

## What's deliberately not included

- Technical/architecture design as a first-class artifact. If it surfaces, it lives as notes in `plan.md` or commit messages. Easy to add `tech-notes.md` later.
- Automated execution-progress tracking. The execute subagent is responsible for its own progress within its session.
- Time/effort estimates. Iterations are sized by judgment, not by planning math.
- Roles, approvals, multi-user coordination. Single-user (or single-pair) workflow.
- Distribution as a plugin. Consumers copy `.claude/skills/sdlc/` and `mkdir .sdlc`.

## Open considerations (revisit if pain arises)

- **STATE.md** — currently dropped; re-add if filesystem inference becomes ambiguous (e.g., parallel iterations).
- **designs/ two-sources-of-truth** — accepted for now; if it bites, switch to "move" semantics.
- **Cross-platform helpers** — add `.sh`/`.ps1` pairs only when a real user hits friction.
- **Roadmap maintenance skill** — no skill currently writes to `ROADMAP.md`. If hand-maintenance becomes a chore, add `/sdlc:groom`.

## Next steps

1. Implement the six skills under `.claude/skills/sdlc/`.
2. Write template files for each `.sdlc/` artifact so `/sdlc:capture` and friends have something concrete to scaffold.
3. Dogfood by running the SDLC on this repo itself: capture → plan → design → qa → execute → review.
