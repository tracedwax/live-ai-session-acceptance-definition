## ADDED Requirements

### Requirement: Docsify site served from docs/
The curriculum SHALL be a Docsify site located in `docs/`, deployable via GitHub Pages from `/docs` on `main`, mirroring the `tracedwax/live-coding-session-for-clasp` structure.

#### Scenario: Required files present
- **WHEN** the `docs/` directory is inspected
- **THEN** it contains `index.html`, `.nojekyll`, `_sidebar.md`, `README.md`, `prerequisites.md`, `workshop-flow.md`, four `module-*.md` files, `office-hours.md`, and `facilitator-guide.md`

#### Scenario: GitHub Pages deployable without further config
- **WHEN** GitHub Pages is pointed at `/docs` on `main`
- **THEN** the site renders with no build step (static Docsify, `.nojekyll` present)

### Requirement: Clasp-parity site chrome
`index.html` SHALL reproduce the clasp Docsify chrome: vue theme, light/dark theme toggle with persistence, per-codeblock copy buttons, full-text search, and Prism highlighting for bash, json, and javascript.

#### Scenario: Theme toggle persists
- **WHEN** a user toggles dark mode and reloads
- **THEN** the chosen theme is restored from localStorage

#### Scenario: Code blocks are copyable
- **WHEN** a user hovers a fenced code block
- **THEN** a working Copy button appears

### Requirement: Sidebar navigation in session order
`_sidebar.md` SHALL list every page in delivery order with emoji labels, matching the clasp navigation style.

#### Scenario: Navigation order
- **WHEN** the sidebar renders
- **THEN** entries appear as Home → Prerequisites → Workshop Flow → Module 1–4 → Office Hours → Facilitator Guide

### Requirement: Locally render-verifiable
The site SHALL render correctly when served locally before any deployment.

#### Scenario: Local serve passes
- **WHEN** `docs/` is served locally (e.g. `npx docsify-cli serve docs`)
- **THEN** navigation, search, theme toggle, copy buttons, and `<details>` blocks all function with no console-breaking errors
