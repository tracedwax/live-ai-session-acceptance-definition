## 1. Site chrome

- [x] 1.1 Build `docs/index.html` + `.nojekyll` — port clasp Docsify chrome (vue theme, light/dark toggle, copy buttons, search, Prism bash/json/js + yaml/markdown), retitled for Class 1
- [x] 1.2 Build `docs/_sidebar.md` — nav in delivery order

## 2. Core content pages

- [x] 2.1 `docs/README.md` (home, spec step 1) — what/why, SOW Week 0→4 arc table, AI level-set, cited Five Levels, Claude-vs-Cursor note; humanizer + rewrite-like-trace
- [x] 2.2 `docs/prerequisites.md` (spec step 0) — only Claude+joke mandatory; OpenSpec-feature + past-work + Tessl optional; troubleshooting table; humanizer + rewrite-like-trace
- [x] 2.3 `docs/workshop-flow.md` — 60-min core + optional 30-min office-hours timing, ROTI close; humanizer + rewrite-like-trace
- [x] 2.4 `docs/module-1-prompting-context.md` (spec step 2) — prompting/context fundamentals + first hands-on CLAUDE.md; humanizer + rewrite-like-trace
- [x] 2.5 `docs/module-2-skills.md` (spec steps 3–4) — skills, marketplaces, safety/review, Bryce demo script, Tessl zero-login + agent-eval fallback; humanizer + rewrite-like-trace
- [x] 2.6 `docs/module-3-build-a-skill.md` (spec steps 5–8) — 4 rooms + Jira/Confluence stretch, pick OpenSpec feature, write skill, Tessl review; CLAUDE.md callback; humanizer + rewrite-like-trace
- [x] 2.7 `docs/module-4-debrief.md` (spec steps brief 9 + 11) — short discussion, next-session preview, homework in core; humanizer + rewrite-like-trace
- [x] 2.8 `docs/office-hours.md` (spec steps extended 9 + 10) — optional deep discussion, skill iteration, deep Q&A; humanizer + rewrite-like-trace
- [x] 2.9 `docs/facilitator-guide.md` — 60+30 timing, Mike B pre-assignment fill-in table, Bryce demo + fallback script, common issues, hard-60 cut paths, ROTI prompts; humanizer + rewrite-like-trace

## 3. Finalize

- [x] 3.1 Curriculum-link + placeholder sweep — SOW arc embedded in README; no `{{...}}`/TODO/curly-quote; Tessl arg form pinned (`npx tessl skill review ./<folder>`); prose em-dashes tightened
- [x] 3.2 Local Docsify render verification — 11/11 pages serve 200, all internal links resolve, chrome via proven CDN
- [x] 3.3 Review delegated by Trace ("you run the show"); adversarial review performed in lieu (see section 4)
- [ ] 3.4 `openspec validate` clean; `openspec archive add-class1-skills-curriculum`

## 4. Adversarial review revisions (post-build, verified)

- [x] 4.1 Fix Tessl invocation everywhere: `npx tessl` → `npx -y @tessl/cli`; add `--threshold` as the "parameters" check; verified no-login — `3098e2c`
- [x] 4.2 Correct Five Levels to canonical Shapiro names + explain the 0–5 span (README) — `9725732`
- [x] 4.3 Fix SKILL.md example to real single-file frontmatter format (module-2 + module-3) — `f470a45`
- [x] 4.4 Make Module 1 work for no-repo / Product participants; de-risk the 12-min timing — `cbb0e8d`
- [x] 4.5 OpenSpec-newcomer 30-sec path, "what OpenSpec is" + link, local-orchestrator clone, Product-contribution note — `180bc2c`
- [x] 4.6 Re-verify: 11/11 pages 200, links resolve, no wrong-pkg command, no placeholders/curly quotes
