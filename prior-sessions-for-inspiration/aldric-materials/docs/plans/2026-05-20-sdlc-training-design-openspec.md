# Agentic SDLC Training — Cross-Functional Team Rollout (OpenSpec variant)

**Drafted:** 2026-05-20
**Revised:** 2026-05-21 — session length 60 min (was 120), office hours added
**Revised:** 2026-05-21 — every session reframed as a real micro-iteration with one embedded concept beat; "office hours" → "coaching hours" with active themed curriculum
**Revised:** 2026-05-21 — SWBAT statements added per session; facilitator risks extracted to companion facilitator-guide outline
**Revised:** 2026-05-21 — tooling pinned to VS Code + Claude Code extension; coaching hours decoupled from class (~5/week, ~1 hr each, separate); skeptic-handling removed (none in this cohort); non-technical pre-work track added
**Revised:** 2026-05-21 — S1 broadened to all roles' daily work (not ticket-specific, was leaving QA/eng watching); S2 reframed so every hat contributes to one ticket (parallel cross-functional grooming); S3 retitled to make parallel (S2) vs sequential (S3) distinction explicit
**Variant:** 2026-05-21 — copied from `2026-05-20-sdlc-training-design.md` and reworked to use **OpenSpec** (https://openspec.dev / Fission-AI/OpenSpec) as the workflow scaffold in place of the `/sdlc:*` skills.
**Status:** design (pre-implementation)
**Companions:**
- `2026-05-20-sdlc-facilitator-guide.md` — outline, pending alignment (some session-specific content will need an OpenSpec pass before pilot)
- `2026-05-20-sdlc-prework-nontechnical.md` — outline, pending alignment (OpenSpec install step needs adding)

## Audience & context

- ~15 people, four "hats": **product, design, QA, engineering**.
- **Technical mix.** Engineers work in code, terminals, and repos. Product, design, and QA in this team are **GUI-only** — they don't open terminals or write code. Both populations are accommodated; non-technical attendees have a dedicated pre-work track.
- Tool fluency: Jira-native, existing codebase, some design tooling. **Little to no exposure to agentic AI tooling.** **No skeptics in this cohort** — the group is dedicated and willing.
- **Canonical tooling stack:**
  - **VS Code with the Claude Code extension** — the IDE surface
  - **OpenSpec** (`@fission-ai/openspec`) — the spec-driven workflow. Slash commands (`/opsx:propose`, `/opsx:apply`, `/opsx:archive`, plus the expanded set), `openspec/specs/` and `openspec/changes/` as living artifact directories
  - **Jira MCP** — context bridge from existing backlog into Claude
- **Workflow adoption** — the team adopts OpenSpec as an **opinionated framework**, not a starter scaffold to adapt. They learn `/opsx:*`, write `proposal.md` / `design.md` / `tasks.md` / specs themselves, and the workflow that emerges is theirs only in *what they propose*, not in the shape of the tooling.

## North Star — what "graduated" means at session 6

The team leaves the program with:

1. **Mindset shift.** "AI is hype/scary/magic" → "Claude is a tool I drive; it has a cost and a benefit and I can reason about both."
2. **Workflow v0.1.** A collaborative, Jira-integrated, OpenSpec-driven workflow exists and runs at least once end-to-end (propose → review → apply → archive). Imperfect by design.
3. **Guardrails.** Explicit norms for what's safe to auto-apply, what requires review, what stays human-only.
4. **Feedback loop.** A standing cadence for editing specs, archiving completed changes, recording learnings, and improving the workflow without an outside facilitator.
5. **Progressive self-enablement.** Each role knows the next step *they* can take to deepen their own usage, and how to teach a peer.

What we are **not** trying to produce: experts. Six 60-minute sessions cannot produce expertise — Dreyfus would call this "advanced beginner" at best. We're producing a team that can keep getting better on its own.

## Learning design principles

Drawn from established adult-learning research and applied to AI-tooling rollouts:

- **Andragogy (Knowles).** Adults need to know *why*, learn by solving real problems, bring prior experience worth surfacing, and want autonomy. Every exercise uses one of *their* Jira tickets, not synthetic examples.
- **Cognitive apprenticeship (Collins, Brown, Newman).** Model → scaffold → coach → fade. The facilitator's posture changes across the six sessions; learners' authorship grows.
- **Deliberate practice (Ericsson).** Narrow reps with immediate, specific feedback. Not "try the tool and see what happens."
- **Cognitive load theory (Sweller).** One new concept per session. Worked examples precede novel problems. We resist the urge to demo the whole platform on day one.
- **Spacing + retrieval.** Sessions are spaced ~1 week apart with real work in between. Between-session prompts ask learners to *recall and apply*, not just re-read.
- **70-20-10.** Most learning happens on the job. Sessions exist to unblock, not to transmit. Between-session work is where competence forms.
- **Psychological safety (Edmondson).** First wins must be cheap and visible. Public failure must be safe. Facilitator names this explicitly in S1.
- **Lab over lecture.** No session is more than 25% presentation. The rest is paired or group practice.

## Cognitive-apprenticeship arc

Every session is a real micro-iteration. The posture changes; the format doesn't.

| Session | Posture | Iteration shape |
|---------|---------|------------------|
| S1 | Modeling | Facilitator drives a tiny iteration; learners try a small piece in their own environment |
| S2 | Scaffolding | Parallel pod iterations — each pod drafts a **change proposal** with all four hats contributing |
| S3 | Scaffolding | Sequential walk — one change moves through `/opsx:propose` → review → `/opsx:apply` → `/opsx:archive` across all four hats |
| S4 | Coaching | Iteration pauses mid-flow to author a needed **spec** (or spec delta) |
| S5 | Coaching → fading | Full iteration with silent facilitator; **review gates** between propose and apply surface |
| S6 | Fading | Meta-iteration: the workflow itself is the artifact |

## The embedded micro-iteration pattern

Every session is a real iteration on the team's actual work with **one concept beat** embedded inside it. No demo sessions, no concept-only sessions, no synthetic exercises.

The session shape:

```
Recall                 (3 min)    — "one thing from the week"
Frame the iteration    (2–5 min)  — what we're doing today; what counts as done
Iteration, round 1     (10–25 min) — the work begins
Concept beat           (~10 min)  — surfaces when the iteration naturally needs it
Iteration, round 2     (10–25 min) — work continues, informed by the concept
Wrap                   (2–5 min)  — micro-share or preview
```

**The craft is catching the surfacing moment.** The concept beat lands when the group has just felt the need for it — not on a fixed minute. If the iteration is going so well that no surfacing moment arrives, the facilitator pauses at the 35-min mark and *asks* the question that would have surfaced it. The beat lands; the iteration absorbs the pause.

**Why this works.** Worked examples and abstract concepts decay fast. Concepts attached to a felt moment — "we just needed X" — stick. This is cognitive load theory plus Knowles' problem-centered learning, compounded.

**Why this is demanding.**
- Facilitator skill is high. They must drive an iteration, listen for the surfacing moment, and pause at the right time without breaking flow. Not a green-facilitator format.
- Each iteration must be *real*. Synthetic tickets do not produce real surfacing moments. Pre-screen ruthlessly.
- Coaching hours carry significant content load. Their attendance is no longer optional-luxury — it is expected-for-catch-up. Plan and communicate accordingly.

## Logistics (recommendation)

- **Cadence:** weekly, six consecutive weeks.
- **Class length:** 60 minutes per week.
- **Coaching hours:** ~1 hour, ~5 days per week, **separate from class** (see *Coaching hours pattern* below). Total support time: ~30 coaching hours across 6 weeks.
- **Format:** in-person preferred; remote works if breakouts are well-managed. All 15 attend all sessions (the cross-functional fabric is the point).
- **Between sessions:** 60–90 min of real-work application, with a single recall prompt sent mid-week. **At 60-min session length, between-session work carries more of the load.** This is non-negotiable — protect that time with leadership.
- **Room setup:** pods of 3–4 mixing hats. Re-mix every session.
- **Required infra by S1:**
  - *All attendees:* VS Code installed; Claude Code extension installed and authenticated; Jira MCP configured against a sandbox project; one warm Jira ticket selected.
  - *Engineering attendees additionally:* the repo cloned locally; **OpenSpec installed (`npm install -g @fission-ai/openspec`) and `openspec init` already run** on the sandbox repo.
  - *Non-technical attendees:* follow the non-technical pre-work guide; pre-S1 coaching hour offered as support. They do **not** need OpenSpec installed locally — they will interact with `openspec/specs/` and `openspec/changes/` via the VS Code file explorer and via slash commands paired with an engineer.

### Coaching hours pattern

Coaching hours run **separately from class** — roughly one hour, once per day, ~5 days per week. Across the program that's ~30 coaching hours supporting 6 classes (a ~5:1 ratio). Drop-in, with a posted daily focus.

- **Purpose.** Carry the content that doesn't fit the embedded-iteration format: hat-specific worked examples (the "stations" from earlier drafts), OpenSpec deep-dives, MCP setup help, hat-pure authoring time, second-pass on a missed concept, individual hand-holding, support for the non-technical pre-work track.
- **Themed by week.** Each week's coaching hours connect to that week's class concept beat.
- **Themed by day (example pattern, adjust to team calendar).** Monday: class recap / catch-up. Tuesday–Thursday: rotating hat-specific worked examples (product / design / QA / eng). Friday: open hours.
- **Pre-S1 coaching hour.** Dedicated to non-technical attendees getting to ready state. May be repeated if the cohort needs it.
- **Attendance.** Honest framing: the embedded format depends on coaching hours for catch-up. We don't expect everyone every day, but we expect everyone to drop in *something* every week.
- **Facilitator load.** ~30 coaching hours over 6 weeks is roughly half of a full-time role. Plan capacity accordingly (see Risks).
- **Each session below lists its coaching threads** — the topics that week's coaching hours pick up.

---

## Session 1 — Tiny micro-iteration: "your own work, with Claude"

**Posture:** Modeling. Facilitator drives most of the iteration; learners try one small piece on their own role's work.

**Goal:** Shift mindset from "AI is opaque/scary/magic" to "Claude is a colleague I onboard." Every learner ends having used Claude on a piece of work native to their own role — not someone else's.

**Students will be able to:**
- Use Claude on a piece of work native to their role and produce something they didn't have before
- Define "agent" and "prompt" in their own words
- Describe the program's safety norm ("breaking in this room is the best place")
- Name one thing that worked and one that surprised them

**Concept beat (one, embedded):** *Agent* + *prompt*. Defined inside the iteration, not before. **OpenSpec is not introduced yet** — S1 is "first contact with Claude," tooling-agnostic.

**Pre-work:** Install VS Code + Claude Code extension (non-technical attendees: follow the non-technical pre-work guide). Bring one small, non-urgent thing from your day-to-day work. Examples by hat:
- *Product:* a Jira ticket whose description or AC could be sharper
- *Design:* a user-flow note, screen description, or design rationale you're polishing
- *QA:* a vague acceptance criterion you'd like to turn into testable assertions, or a flaky test you're triaging
- *Engineering:* a piece of code you'd like to understand, refactor, or document better

**Agenda (60 min):**
1. **Frame & safety (4 min).** Name fears, name goal, state the norm: "If it breaks in this room, that's the best place for it to break."
2. **Set up the iteration (3 min).** Facilitator opens *their own* role's work — whatever that is — screen shared. "We are going to do one small useful thing with Claude on this. Yours will look different — same shape, different content."
3. **Facilitator drives the iteration (10 min).** Live, narrating: open the work, ask Claude for a useful move, react, iterate. Includes one deliberate dead-end and recovery.
4. **Concept beat (10 min).** "What just happened? You saw an *agent* taking *prompts*. Two words. Defined inside what you just watched." Each learner names one piece of what the facilitator just did in their own words.
5. **Pod try (20 min).** Pods of 3 (mixed hats). Each learner takes ~6 min at the keyboard on *their own* piece of work — whatever role-native thing they brought. Partners observe. Facilitators float.
6. **Micro-share (8 min).** One sentence each: what worked or surprised. Questions go to coaching hour.
7. **Close & preview (5 min).** Between-session prompt: "Try once more on something real this week. Bring one story."

**Coaching threads (week 1):** install / MCP friction (esp. for non-technical attendees coming off pre-work), second turn at the keyboard for anyone who needed more time, deeper Q&A for the curious, repeated pre-S1-style coaching for late starters. **OpenSpec install for engineers** happens here if it didn't land in pre-work.

**Success signal:** every learner has used Claude on something native to their own role and can say "an agent is X, a prompt is Y" in their own words.

---

## Session 2 — Pod micro-iteration: "draft a change proposal"

**Posture:** Scaffolding. Pods work in parallel; facilitators float; concept surfaces when the cross-hat pattern shows up in pods' draft proposals.

**Goal:** Each pod takes ONE real ticket and turns it into the start of an **OpenSpec change proposal** — a `proposal.md` (rationale + scope), first-cut spec scenarios in Given-When-Then, and notes-toward `design.md` and `tasks.md`. **Every hat in the pod contributes**: PM rationale, design UX scenarios, QA verification scenarios, engineering feasibility notes.

**Students will be able to:**
- Contribute their role's perspective to a draft OpenSpec change proposal (PM rationale, design UX scenarios, QA verification scenarios, eng feasibility)
- Recognize what a Given-When-Then scenario looks like in plain English
- Watch or run `/opsx:propose` and see what it produces in `openspec/changes/<id>/`
- Name one part of their hat's contribution that surprised them

**Concept beat (one, embedded):** **Change proposal** — a versioned package of intent (proposal + scenarios + design + tasks) that lives in `openspec/changes/`. Not a ticket, not a chat — a structured cross-hat artifact. Surfaced at the moment multiple pods have visibly populated their proposal with contributions from all four hats.

**Pre-work:** Each pod nominates one ticket worth proposing as a change. Ticket should have **surface area for all four hats** AND be small enough that "a draft proposal" is plausible in 30 min of pod work.

**Agenda (60 min):**
1. **Recall (3 min).** "One thing you tried this week."
2. **Frame (2 min).** "Each pod takes one ticket → starts a change proposal. Every hat contributes. By the end, your `proposal.md` has rationale + scenarios + technical notes — all in one place."
3. **Pods draft — round 1 (15 min).** A facilitator demonstrates `/opsx:propose` once on a sample ticket to show what gets created. Pods then run it on their own ticket and start populating `proposal.md` + spec scenarios. Each hat contributes their angle. Facilitators float and listen for cross-hat handoffs ("OK design, what does this look like to the user?" / "QA, where could this break?").
4. **Concept beat (10 min).** Pause when ≥2 pods have visibly involved all four hats in their proposal file. "Notice the dance? PM rationale, design scenarios, QA scenarios, eng notes — all converging in one file. That's a *change proposal*. It lives in `openspec/changes/`. It's a package, not a thread."
5. **Pods draft — round 2 (20 min).** Pods iterate on their proposals. Encouraged: try running `/opsx:apply` once just to see what happens — the goal isn't to ship, it's to see the link from proposal to action.
6. **Cross-pod share (8 min).** One proposal per pod: show the file. One observation each — specifically: *was there a hat whose contribution surprised you?*
7. **Close (2 min).** Each hat names — aloud — one recurring task *their* hat could turn into a sharper section of a future proposal.

**Coaching threads (week 2):** hat-specific examples of "what does PM rationale look like" / "what does a Given-When-Then scenario look like for design / QA / eng"; OpenSpec install and `openspec init` catch-up; the difference between a `change` and a `spec`.

**Success signal:** every pod has a draft change proposal in `openspec/changes/<id>/` with contributions from all four hats; every learner — *including QA and engineers* — can point to a moment when their hat's contribution mattered.

---

## Session 3 — Walk-the-seam micro-iteration: "one change moves through the OpenSpec lifecycle"

**Posture:** Scaffolding. Each role drives their segment; the whole room watches the seam.

**Goal:** One real change walks **sequentially** from `/opsx:propose` → human review → `/opsx:apply` → `/opsx:archive` in real time, with each role's representative driving their segment. The whole room sees — physically — where context drops between hats. (S2 was *parallel* cross-functional proposal-drafting; S3 is *sequential* hand-off across the OpenSpec lifecycle.)

**Students will be able to:**
- Drive their role's ~7-minute segment in a sequential OpenSpec walk-through
- Identify at least one "context drop" at a hat-to-hat seam
- Describe in one sentence what an MCP does
- Distinguish "Claude reads Jira" (in scope today) from "Claude writes to Jira" (deferred to S6 guardrails)

**Concept beat (one, embedded):** *MCP* — how Claude reads/writes existing systems (Jira today). Surfaces at the first handoff where context needs to move from one role's head into the next role's view (typically the proposal-to-review handoff).

**Pre-work:** Each hat group nominates one small real ticket. Group votes at session start. Engineers verify the sandbox repo has OpenSpec initialized and at least one example spec present for context.

**Agenda (60 min):**
1. **Recall (3 min).** "One thing you tried this week."
2. **Pick the ticket (3 min).** Facilitator pre-screened for "walks in 30 min."
3. **Frame (2 min).** "One ticket, four hats, ~30 minutes total. Each role drives ~7 min. The seam is the point."
4. **Propose + plan (10 min).** Product drives `/opsx:propose`. Facilitator captures the seam on a board.
5. **Concept beat (10 min).** At the proposal-to-review handoff, pause. "How does design get context to review the proposal? Right now — through Jira, manually. What if Claude could read the ticket directly to inform the proposal?" Demo Jira MCP live: Claude pulls the ticket, summarizes, proposes additions to the spec scenarios.
6. **Design + QA review, then apply (20 min).** Design adds UX scenarios. QA adds verification scenarios. Engineer drives `/opsx:apply` for one or two tasks. Facilitator keeps capturing the seam.
7. **Reflect (10 min).** Where did context drop? Where did Claude+MCP actively help? Items captured for the S6 friction inventory.
8. **Close (2 min).** Brief preview: archive will happen later (S5 or in coaching hour); the point today was the seam.

**Coaching threads (week 3):** anyone who wants to walk their own ticket through the OpenSpec lifecycle; Jira MCP setup help; deeper MCP exploration (read vs. write — write deferred to S6 guardrails); `/opsx:archive` for those curious to close the loop.

**Success signal:** a shared diagram of the team's seams exists with at least three named "context drops," and the room has seen Claude+MCP visibly help at least one handoff.

---

## Session 4 — Authoring micro-iteration: "writing the spec that doesn't exist yet"

**Posture:** Coaching. Learners drive; facilitator catches the surfacing moment.

**Goal:** The group writes a real **spec** (or spec delta), mid-iteration, in response to felt need. Each hat leaves with a commitment to a v0.0 spec contribution they will draft this week.

**Students will be able to:**
- Contribute to drafting an OpenSpec `spec.md` file collaboratively in real time
- Identify the three structural sections of a spec: *Purpose*, *Requirements* (using SHALL language), *Scenarios* (in Given-When-Then format)
- Distinguish a *spec* (capability requirements, long-lived) from a *spec delta* (per-change diff, archived into the spec)
- Commit to a specific v0.0 spec or spec-delta they will draft for their own hat this week

**Concept beat (one, embedded):** **Specs are the team's living requirements.** They live in `openspec/specs/<capability>/spec.md`. They have a stable shape (Purpose / Requirements with SHALL / Scenarios with Given-When-Then). Spec deltas — generated as part of each change — accumulate into specs on `/opsx:archive`. Surfaces when the running iteration hits behavior that *would have been unambiguous* if a spec for that capability existed.

**Pre-work:** Each hat shows up with one repeated thing in mind — a capability the team keeps re-explaining, or a behavior nobody can quite agree on the definition of.

**Agenda (60 min):**
1. **Recall (3 min).** "One piece of behavior your hat wishes had a written-down truth." (Seeds S6 guardrails.)
2. **Frame & pick the iteration (5 min).** Group picks a small ticket. Facilitator privately notes the moment they expect a spec gap to surface.
3. **Iteration round 1 (12 min).** Group drives — likely a `/opsx:propose` and start of review. Facilitator lets them hit the predicted moment.
4. **Concept beat (10 min).** "Stop. We just disagreed about what X actually means — twice. Let's write the spec for it together." Open `openspec/specs/<capability>/spec.md`, walk through the three sections (Purpose / Requirements / Scenarios), and draft a v0.0 with the room's input. Save it. Commit it.
5. **Iteration round 2 (15 min).** Group resumes, now with the spec to reference. Notice the difference: ambiguity drops.
6. **Cross-hat commitments (10 min).** Each hat names *their* spec or spec-delta — the v0.0 they will draft this week. Posted on the wall (or shared doc).
7. **Close (5 min).** Between-session prompt: "Draft your v0.0. Bring it to S5."

**Coaching threads (week 4):** hat-pure authoring (specs and spec deltas) with a facilitator coaching structurally; **SHALL language and Given-When-Then practice** — these are formal styles that take a moment to get used to; git mechanics for non-technical attendees via VS Code's git GUI (not the terminal); structural feedback ("does this spec actually pin down what your hat cares about?").

**Success signal:** one spec exists in the repo that did not exist 60 minutes ago, written by the room; every hat has committed to a v0.0 spec or spec-delta they'll draft this week.

---

## Session 5 — Full-flow micro-iteration: "real work, silent facilitator"

**Posture:** Coaching → fading. Group drives end-to-end with their own specs and OpenSpec workflow; facilitator intervenes only after a 2-minute stall.

**Goal:** A real change runs through the full lifecycle (`/opsx:propose` → review → `/opsx:apply` → `/opsx:archive`) using the team's own specs. Friction is captured, not solved. Intuition about *what should be gated vs. what can fly* is seeded — not yet decided.

**Students will be able to:**
- Drive an end-to-end OpenSpec change with minimal facilitation
- Distinguish a step that *should always pause for human review* from one that *can run unattended*
- Capture a friction item into the shared inventory
- Diagnose at least one painful repeat as a candidate for a review-gate adjustment (looser or tighter)

**Concept beat (one, embedded):** **Review gates** — between propose and apply, what does our team always pause to look at, and what can fly? The room learns the distinction by feeling it — encountering a step they instinctively want gated, or one they wish they could just skip past. Decisions deferred to S6.

**Pre-work:** Each hat brings their v0.0 spec polished from the week. Each hat also brings one small deliverable they could realistically ship.

**Agenda (60 min):**
1. **Recall (3 min).** "Did your v0.0 see real work? What broke?"
2. **Pick & frame (5 min).** Group picks one deliverable. Criterion: "small enough to walk through the full lifecycle in 25 minutes." Facilitator vetoes anything bigger. State the norm: "I'm silent unless you've been stuck >2 min."
3. **The iteration (25 min).** Trainees drive `/opsx:propose` → human review → `/opsx:apply` → start of `/opsx:archive`. Facilitator captures friction silently.
4. **Concept beat (10 min).** Pause at the moment a review-gate question arises — typically when someone says "wait, should we really just apply this?" or "couldn't we skip reviewing this part?" "That instinct you just had — that's a *review gate* question. Where does our team want a pause, and where can things fly? We decide together next week."
5. **Friction inventory completion (10 min).** Group adds anything else painful to the shared list for S6.
6. **Close (7 min).** Iteration may not be done — coaching hour can finish it. Frame S6: "Last session is *yours*. Bring everything you want to change."

**Coaching threads (week 5):** finishing the change (apply + archive) if it ran long (likely); deepening the friction inventory; for the eager, sketching one review-gate decision in writing.

**Success signal:** a real OpenSpec change ran end-to-end (possibly continuing into coaching hour), a friction inventory exists, and the room has *felt* — not just heard — which steps want gates and which want to fly.

---

## Session 6 — Meta-iteration: "the workflow is the artifact"

**Posture:** Fading. The team facilitates itself on its own workflow. The facilitator's last job is to *not* lead.

**Goal:** Institutionalize self-improvement. The team leaves with codified review gates, edited specs, named owners, a written cadence, and a charter.

**Students will be able to:**
- Populate the four-quadrant review-gates canvas with examples from lived experience this program
- Edit a spec they own — specifically: trim or sharpen a Requirements line or a Scenario
- Name the owner, cadence, and inbox location for ongoing improvement
- Co-author and post the team's written charter

**Concept beat (one, embedded):** **The feedback loop itself.** The same propose → review → edit → archive pattern applied to the *workflow*, not to product changes. The team retros on the program by running an OpenSpec-shaped reflection on what they built.

**Pre-work:** Re-read the S5 friction inventory. Bring one proposed change to the workflow.

**Agenda (60 min):**
1. **Quick retro (10 min).** Plus / delta / questions on the program. Facilitator captures silently — does not respond yet.
2. **Frame the meta-iteration (2 min).** "Today's artifact is our own workflow. We propose, review, edit, archive *it*."
3. **Capture (5 min).** Pull friction items from S5 + the retro into one consolidated list.
4. **Concept beat (10 min).** Present the *review-gates canvas* (four quadrants: safe-to-auto-apply / propose-then-review / human-gate-required / never-let-apply-fly). Group populates from lived examples this program — no hypotheticals.
5. **Specs edit sprint (15 min).** Hat groups trim/edit their specs based on the canvas. **Goal is precision, not addition** — sharpen a SHALL, tighten a scenario, delete what didn't pay off. Deeper edits continue in coaching hour.
6. **Cadence decision (8 min).** Owners per spec area, retro rhythm, where friction items go (a `friction-inbox.md` is a reasonable convention, or use Jira). Who runs the next retro, when.
7. **Charter (8 min).** A short written commitment (one page max). What we agreed to. Posted somewhere visible.
8. **Close (2 min).** No homework. The cadence *is* the homework now.

**Coaching threads (week 6):** deeper spec editing; one-on-one with named owners to onboard them to their ongoing responsibility; `/opsx:archive` walkthroughs for any changes still open; exit interviews / Level-2 data capture if leadership wants it.

**Success signal:** the team leaves with (a) edited specs they own, (b) a populated review-gates canvas, (c) a written charter naming owners and cadence — and the facilitator does *not* leave with a list of follow-ups.

---

## Materials to build

Roughly in order of dependency:

1. **Facilitator guide** — companion document at `2026-05-20-sdlc-facilitator-guide.md` (currently a structural outline pending alignment, written against the prior /sdlc:* variant). Needs an **OpenSpec pass** before pilot — observable cues and talking points reference "skill" in S2 and S4; those need updating to "change proposal" and "spec" respectively.
2. **Participant handouts** — one-pager per session with the concept, the iteration brief, and the between-session prompt.
3. **Infra runbook** — VS Code install, Claude Code extension install + authentication, **OpenSpec install (`npm install -g @fission-ai/openspec`) and `openspec init`** on the sandbox repo, Jira MCP setup against the sandbox project, repo clone (engineering attendees only). Sanity check tested by a non-engineer.
4. **Non-technical pre-work guide** — companion document at `2026-05-20-sdlc-prework-nontechnical.md` (currently an outline). GUI-only, screenshot-driven path to "ready state." Does **not** need OpenSpec installed locally — non-tech attendees view `openspec/specs/` and `openspec/changes/` via VS Code's file explorer.
5. **OpenSpec scaffolds** — `openspec init` already run on the sandbox repo; a starter `openspec/specs/` with **two example specs** populated for reference (one PM-flavored, one eng-flavored, both showing Purpose / Requirements / Scenarios); one sample completed change in `openspec/archive/` showing the full lifecycle. Consumed in S2 (referenced), S3 (walked through), S4 (extended).
6. **Coaching-hour curriculum** — weekly themes for the ~30 coaching hours; each day has a stated focus, materials, and "who this is for." Includes hat-specific worked examples (writing PM rationale, design UX scenarios in GWT, QA verification scenarios in GWT, eng tasks in `tasks.md`) on rotation across the week.
7. **Worked examples per hat** — recorded screencast + written script per hat for the OpenSpec authoring activities. Used in coaching hours, not main sessions.
8. **Review-gates canvas template** — used in S6 (and ongoing). Four quadrants: safe-to-auto-apply / propose-then-review / human-gate-required / never-let-apply-fly.
9. **Charter template** — used in S6.
10. **Recall prompts** — six prompts (one mid-week between each pair of sessions). Short, single question.
11. **Evaluation instrument** — light. Pre-survey (S1), post-survey (S6), and one optional follow-up at +60 days to measure retention/adoption.

## What we will **not** do

- **No bootcamp / cert.** Adult learners adopting new tooling don't need a credential; they need wins and safety.
- **No concept-only or demo-only sessions.** Every session is a real iteration. Concepts live inside iterations, never alongside.
- **No synthetic exercises.** Every iteration uses real tickets from real backlogs. Synthetic work doesn't produce real surfacing moments.
- **No "here's the perfect workflow we built for you."** OpenSpec provides the *workflow shape*; the team owns *what they propose, review, and archive*.
- **No automation before friction.** Review-gate decisions come in S5/S6 from felt pain, not from a feature checklist.
- **No prescribing tools beyond the canonical stack** (Claude Code in VS Code, OpenSpec, Jira MCP). Confluence MCP, code-review automation, etc. are downstream of this program.
- **No 1:1 coaching as part of the six sessions.** Offered separately if requested.
- **No teaching the team to author their own Claude Code skills.** OpenSpec ships the slash commands; the team's authoring focus is on specs and change proposals, not on writing new `/opsx:*` skills.

## Risks to the program itself

| Risk | Mitigation |
|------|------------|
| One role checks out early ("this is engineering's thing") | S2/S3 are explicitly cross-role. Facilitator names the risk in S1. |
| Infra/setup eats S1 | Required pre-work + dedicated pre-S1 coaching hour (especially for non-technical attendees and for OpenSpec install for engineers). |
| Non-technical attendees arrive at S1 unready because pre-work was unclear or unsupported | Screenshot-driven non-technical pre-work guide; pre-S1 coaching hour; track pre-work completion before S1 and intervene early. |
| Facilitator capacity for ~30 coaching hours over 6 weeks is hard to staff | Identify two facilitators who share rotation; or compress cadence (e.g., 3/week instead of 5) if 5 isn't sustainable. Plan capacity at program kickoff, not week 3. |
| Champion runs ahead and bores the group | Channel them into mentor role within their pod. |
| Leadership treats this as "AI adoption training" and measures usage rather than outcomes | Pre-engagement with leadership to align on Level-3/Level-4 Kirkpatrick metrics, not Level-1 satisfaction or Level-2 usage. |
| Workflow drifts back to pre-OpenSpec habits after week 8 | The S6 charter names an owner per spec area and a 6-week check-in cadence. |
| The concept beat misses its natural surfacing moment | Facilitator has a pre-planned prompt to call the moment ("I expected us to want X here — anyone else feel it?") and a hard fallback at 35 min. Practiced in pilot. |
| The S1 micro-iteration is too ambitious and people drown on day one | S1 iteration scope is fixed and rehearsed: refine one piece of role-native work. Nothing larger. OpenSpec is not introduced in S1. |
| Coaching-hour attendance is too low and learners fall behind on stationed content | Communicate honestly in S1 that coaching hours are expected-for-catch-up. Track attendance; if it dips, re-pitch the why. |
| Facilitator doesn't have the skill to drive iteration + listen for surfacing + pause at the right time | This is not a green-facilitator format. Either assign senior facilitators or run a facilitator-prep session before S1. |
| OpenSpec slash-command names or workflow profiles drift between releases (docs and CLI sometimes diverge) | Version-pin OpenSpec in the infra runbook. Verify command names against the *installed* version before drafting facilitator materials. Test all sessions against the pinned version. |
| The team treats OpenSpec as ceremony rather than as a way to share intent | S5's silent-facilitator iteration is where this surfaces. If proposals are being written perfunctorily, name it in S6 retro and adjust review-gates in the canvas. |

## Open decisions (defer, not block)

- **Session length.** Fixed at 60 min + 30-min coaching hour. If coaching-hour attendance is very low after S1–S2, re-pitch the "why" rather than dropping them — the embedded format depends on them.
- **Facilitator skill.** Embedded format requires a facilitator who can drive an iteration, listen for the surfacing moment, and pause at the right time. Either pre-screen for this skill or run a facilitator-prep session before S1.
- **Sync vs async between sessions.** Recommended sync recall prompts (Slack thread); could be async-only if team is remote-async.
- **Which Jira MCP.** Pick before infra runbook is built. Lock by end of design.
- **Which OpenSpec version.** Lock to a specific `@fission-ai/openspec` version before infra runbook and facilitator materials are written. CLI flow and slash-command names should match what attendees will actually use.
- **Whether to record sessions.** Default no, for psychological-safety reasons. Can be reversed by team consent. Coaching hours never recorded.
- **What "sandbox" Jira project to use.** Real project recommended (real stakes = real learning), but a forked sandbox is acceptable if real is too risky.
- **Whether the sandbox repo gets a freshly `openspec init`-ed state, or is pre-seeded with example specs and one archived change.** Recommended: pre-seeded — gives the room a reference to point at in S2 without authoring from scratch.

## Next steps (downstream of this design)

1. Confirm logistics with stakeholders (length, cadence, attendance, sandbox).
2. Pick Jira MCP and pin OpenSpec version. Write the infra runbook.
3. Identify facilitators and run a facilitator-prep session focused on the embedded-iteration craft (surfacing moments, the 35-min fallback, silent-facilitator discipline in S5) **and** on OpenSpec command fluency.
4. Update the companion facilitator guide for the OpenSpec variant — observable cues and talking points in S2 (change proposal, not skill) and S4 (spec, not skill) need rewriting.
5. Update the companion non-technical pre-work guide for the OpenSpec variant — add a note that they don't install OpenSpec but will see `openspec/` in VS Code.
6. Draft S1 facilitator guide end-to-end as the prototype, including the rehearsed iteration script; iterate before drafting S2–S6.
7. Pilot S1 with a friendly subset (3–4 people) before running with the full 15. Pay special attention to whether the concept beat lands at the right moment.
8. Build S2–S6 guides in order, incorporating pilot lessons. Each guide names its predicted surfacing moment and its fallback prompt.
