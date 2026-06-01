## ADDED Requirements

### Requirement: 60-minute hard core plus optional 30-minute office hours
The session SHALL be designed for a 60-minute mandatory core followed by an optional 30-minute office-hours block. All mandatory content, including next-session preview and homework, SHALL fit within the core 60.

#### Scenario: Homework reachable by all attendees
- **WHEN** an attendee leaves at the 60-minute mark
- **THEN** they have already received the homework and next-session preview (these are in `module-4-debrief.md`, not `office-hours.md`)

#### Scenario: Optional content is clearly optional
- **WHEN** a reader views `office-hours.md`
- **THEN** it is explicitly labeled optional and contains only deep discussion, skill iteration, and extended Q&A

### Requirement: Mandatory vs optional prerequisites
`prerequisites.md` SHALL mark only "Claude installed and able to tell a joke" as mandatory; OpenSpec-feature-ready and past-work samples SHALL be explicitly optional.

#### Scenario: Single mandatory prerequisite
- **WHEN** a participant reads the prerequisites
- **THEN** exactly one item is labeled required (Claude + joke) and all others are labeled optional

#### Scenario: Tessl install is optional-but-encouraged, no account
- **WHEN** the Tessl prerequisite is read
- **THEN** it states installation is optional but encouraged and requires no login/account

### Requirement: Module 1 builds a CLAUDE.md from live preferences
The first hands-on activity SHALL have participants create a 1–2 line `CLAUDE.md` capturing preferences surfaced during the session.

#### Scenario: CLAUDE.md hands-on present in Module 1
- **WHEN** `module-1-prompting-context.md` is read
- **THEN** it includes a hands-on step to create a CLAUDE.md with 1–2 preferences, after prompting/context fundamentals (context rot, intent engineering)

#### Scenario: Skill module calls back to CLAUDE.md
- **WHEN** `module-3-build-a-skill.md` is read
- **THEN** it explicitly frames a skill as the packaged version of the Module 1 CLAUDE.md

### Requirement: Four-room breakout skill build against OpenSpec work
`module-3-build-a-skill.md` SHALL define four breakout rooms — manual-QA-script, AQA-test (Bryce-facilitated), estimate-with-dev-input, artifact-chunker — with Jira/Confluence-poster as a stretch, building a skill against a real or arbitrary OpenSpec feature.

#### Scenario: Rooms and stretch
- **WHEN** the breakout section is read
- **THEN** exactly four rooms are defined plus a stretch option, with a Mike-B-owned pre-assignment table and a note that switching is allowed

#### Scenario: Skill reviewed with Tessl or fallback
- **WHEN** a room finishes its skill
- **THEN** the module instructs reviewing it via `npx tessl skill review` (zero login), with an agent-eval fallback if Tessl is unavailable

### Requirement: Cited Five Levels for AI-maturity level-setting
The home/intro page SHALL present the Five Levels (L0 Spicy Autocomplete → L5 Dark Factory) with attribution and frame them on the SOW "Dark Factory" spine.

#### Scenario: Attribution present
- **WHEN** the Five Levels appear in `README.md`
- **THEN** they are attributed (Shapiro origin, Jones popularization) with a source link, and tied to the SOW Week 0→4 arc

### Requirement: No-AI-slop quality gate
Every content page SHALL be processed through the `humanizer` skill and `rewrite-like-trace` before the change is considered complete.

#### Scenario: Quality pass recorded
- **WHEN** a content page is finalized
- **THEN** the corresponding task records a humanizer + rewrite-like-trace pass

### Requirement: Verified tool commands and cited facts
Every CLI command and cited fact in the curriculum SHALL be verified against the real tool or authoritative source before delivery.

#### Scenario: Tessl invocation is runnable
- **WHEN** any page instructs running Tessl
- **THEN** the command uses the real package (`npx -y @tessl/cli ...`) with a verified subcommand, and the no-login claim matches actual behavior

#### Scenario: Five Levels named canonically
- **WHEN** the Five Levels appear
- **THEN** level numbers and names match Dan Shapiro's source (0 spicy autocomplete … 5 dark software factory), with the 0–5 span explained

#### Scenario: SKILL.md shown in real format
- **WHEN** a SKILL.md example is shown
- **THEN** it is a single file with `---`-fenced YAML frontmatter followed by a markdown body, not two separate blocks

### Requirement: Inclusive of Product and OpenSpec newcomers
The curriculum SHALL give a workable path to participants who have no code repo and to those who have never run OpenSpec, since the session is required for Product.

#### Scenario: No-repo participant can do Module 1
- **WHEN** a participant without a code repo reaches Module 1
- **THEN** they are given a concrete alternative (any folder, or `local-orchestrator`)

#### Scenario: OpenSpec newcomer can do Module 3
- **WHEN** a participant who has never run OpenSpec reaches Module 3
- **THEN** a 30-second path and a one-line "what OpenSpec is" with a link are provided, plus an explicit clone step for the default repo

### Requirement: Step-to-page mapping preserved
The 11-point session spec SHALL map onto the pages as: prerequisites (0); README/home (1); module-1 (2 + CLAUDE.md); module-2 (3–4, incl. Bryce demo + Tessl); module-3 (5–8); module-4 (brief 9 + 11); office-hours (extended 9 + 10); workshop-flow + facilitator-guide (timing, pre-assignments, cut paths).

#### Scenario: All 11 spec points are covered
- **WHEN** the full page set is reviewed against the original 11-point spec
- **THEN** every point 0–11 is present in exactly the mapped page(s) with no point dropped
