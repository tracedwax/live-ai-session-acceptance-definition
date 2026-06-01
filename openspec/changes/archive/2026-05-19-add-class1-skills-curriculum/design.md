## Context

Class 1 of the engagement (SOW Week 0). Audience is mixed Dev/QA/Product, already past OpenSpec basics (per 5/12–5/18 sessions and Slack `aw-barefoot-coders`). Barefoot Coders has a proven workshop-site format: a Docsify site served from `docs/` (reference: `tracedwax/live-coding-session-for-clasp`). Constraints come from the SOW, the Slack "Class 1 session plan (skills-focused)" thread, and direct decisions captured in the `/grill-me` session (see `my-bfc-life` HITL plan `2026-05-19_class1-skills-curriculum.md`). Authoring goes through OpenSpec; Trace reviews this proposal before any `docs/` is built.

## Goals / Non-Goals

**Goals:**
- A facilitator-ready, self-serve workshop site matching clasp-repo format exactly.
- All required content + homework/next-session preview fit a 60-minute hard core; deep/iterative content lives in an optional 30-minute office-hours block.
- Hands-on ramp: tiny CLAUDE.md → packaged skill, tied to participants' real OpenSpec work.
- Deliverable does not read as AI-generated (humanizer + rewrite-like-trace on every page).

**Non-Goals:**
- Teaching OpenSpec from scratch (team is past it; it's a prerequisite/input).
- Pushing the repo or enabling GitHub Pages now (deferred to explicit Trace authorization).
- Contoso/sample codebase (killed in Slack; use local-orchestrator or own repos).
- Later-week content (intent engineering, evals, subagents) — only previewed in the debrief.

## Decisions

- **Format = Docsify in `docs/`, clasp parity.** Port clasp `index.html` chrome (vue theme, light/dark toggle, copy buttons, search, Prism bash/json/js), `.nojekyll`, `_sidebar.md`. Alternative MkDocs (pauldatta repo) rejected — Trace prefers the clasp Docsify model.
- **60 + optional 30.** Attendees fade after 60 min; not all stay for office hours, so homework/next-session preview must be in core. Alternative (90 single block) rejected by Trace.
- **Module 1 = create CLAUDE.md from live-surfaced prefs.** Smallest persistent-instruction primitive; sets the mental model that a skill is the packaged version. Module 3 explicitly calls back to it.
- **4 breakout rooms** (manual-QA-script / AQA-test [Bryce facilitates] / estimate-with-dev-input / artifact-chunker); Jira-Confluence poster = stretch (Jira-MCP deferred to coaching per Slack). Mike B pre-assigns via a fill-in table; switching allowed. Alternatives (3 rooms / all 5 / self-pick) rejected for facilitator-staffing and time fit.
- **Tessl primary, zero login, agent-eval fallback.** `npx tessl skill review ./<SKILL.md-folder>` runs local, no account. Install optional-but-encouraged. Fallback: have Claude eval the skill against written criteria (the `skills-session.md` eval pattern).
- **Prereqs: only Claude+joke mandatory.** OpenSpec-feature-ready and past-work samples are optional, clearly labeled — keeps the door open for less-prepared participants.
- **Five Levels cited** (Shapiro origin, Jones popularization) framed on the SOW "Dark Factory" spine for AI-maturity level-setting.
- **OpenSpec is the authoring process**, `@fission-ai/openspec` via npx; this change is the review gate.

## Risks / Trade-offs

- 11 spec steps in 60 min is tight → Mitigation: facilitator-guide carries explicit cut paths; prereqs are pre-work; debrief is short by design.
- Tessl not installed for some on 5/27 → Mitigation: optional-but-encouraged + built-in agent-eval fallback in Modules 2 & 3.
- Curriculum link not yet shareable → Mitigation: embed SOW Week 0→4 arc table directly; no external dependency.
- Breakout pre-assignment needs Mike B → Mitigation: ship as a fill-in table, not hardcoded; switching allowed.
- Bryce demo depends on a person → Mitigation: facilitator guide includes a fallback demo script if Bryce is unavailable.

## Migration Plan

Local-only build. Deployment (GitHub Pages `/docs` on `main`, `gh-pages`/Pages enable, repo push) is a separate, explicitly-authorized step — out of scope here. Rollback = discard the local repo.

## Open Questions

- Canonical external curriculum URL (if one exists) to optionally link from the home page — placeholder/embed used until provided.
- Exact `npx tessl skill review` argument form — pinned live during build (Steps 13–14).
