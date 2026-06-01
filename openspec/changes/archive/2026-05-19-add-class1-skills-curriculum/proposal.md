## Why

Your company's AI training (SOW "Week 0 — Introduction: prompt and context engineering; Agents/Claude.md; prompts; skills") runs Tue 2026-05-27 for a mixed Dev/QA/Product audience. The team is already past OpenSpec basics, so Class 1 must move fast from fundamentals into hands-on skill creation tied to their real OpenSpec work — delivered as a self-serve, facilitator-ready workshop site in the proven format Barefoot Coders already ships.

## What Changes

- Add a Docsify workshop site under `docs/` mirroring the `tracedwax/live-coding-session-for-clasp` format exactly (vue theme, light/dark toggle, copy buttons, search, Prism bash/json/js, `_sidebar.md`, `.nojekyll`), deployable via GitHub Pages (`/docs` on `main`).
- Encode a **60-minute hard core + optional 30-minute office-hours** session: prerequisites, home/intro, workshop-flow, four modules, office-hours, facilitator guide.
- First hands-on is creating a 1–2 line **CLAUDE.md** from preferences surfaced live; the skill-build module explicitly builds on it ("small → packaged").
- **Module 3** runs 4 pre-assigned breakout rooms (manual-QA-script / AQA-test [Bryce] / estimate-with-dev-input / artifact-chunker; Jira-Confluence as stretch) building a real skill against an OpenSpec feature, reviewed with **Tessl** (`npx tessl skill review`, zero login) with an agent-eval fallback.
- Prerequisites: **only "Claude installed + tells a joke" is mandatory**; OpenSpec-feature-ready and past-work samples are optional.
- Intro level-sets AI maturity using the cited Five Levels (Shapiro/Jones, L0 Spicy Autocomplete → L5 Dark Factory) on the SOW "Dark Factory" spine.
- Every page is run through `humanizer` + `rewrite-like-trace` so the deliverable does not read as AI-generated.

## Capabilities

### New Capabilities
- `class1-curriculum-site`: The deliverable's required artifact format — Docsify-in-`docs/` structure, clasp-parity chrome, GitHub Pages deployability, local-render verifiability.
- `class1-session-content`: The required pedagogical content — page set and step-to-page mapping, 60+30 timing rule, mandatory-vs-optional prerequisites, Module 1 CLAUDE.md hands-on, 4-room breakout model, Tessl-primary-with-fallback review, cited Five Levels, no-AI-slop quality gate.

### Modified Capabilities
<!-- None — greenfield repo, no existing specs. -->

## Impact

- New repo `live-coding-session-skills-for-openspec` (local only; **not pushed until Trace authorizes**).
- New files: `docs/**` (Docsify site), `openspec/**` (this change).
- External: Tessl CLI (`@tessl/cli`, optional-but-encouraged, no account); OpenSpec (`@fission-ai/openspec`) as the authoring process.
- Source inputs (read-only): `my-bfc-life` SOW (`inputs/legal/sows/psa-and-sow.md`), Slack log, clasp repo format.
- No production systems; coaching/enablement deliverable, no acceptance testing per SOW §3.2.
