# Agentic SDLC Training — Cross-Functional Team Rollout

**Drafted:** 2026-05-20
**Revised:** 2026-05-21 — session length 60 min (was 120), office hours added
**Revised:** 2026-05-21 — every session reframed as a real micro-iteration with one embedded concept beat; "office hours" → "coaching hours" with active themed curriculum
**Revised:** 2026-05-21 — SWBAT statements added per session; facilitator risks extracted to companion facilitator-guide outline
**Revised:** 2026-05-21 — tooling pinned to VS Code + Claude Code extension; coaching hours decoupled from class (~5/week, ~1 hr each, separate); skeptic-handling removed (none in this cohort); non-technical pre-work track added
**Revised:** 2026-05-21 — S1 broadened to all roles' daily work (not ticket-specific, was leaving QA/eng watching); S2 reframed so every hat contributes to one ticket (parallel cross-functional grooming); S3 retitled to make parallel (S2) vs sequential (S3) distinction explicit
**Status:** design (pre-implementation)
**Companions:**
- `2026-05-20-sdlc-facilitator-guide.md` — outline, pending alignment on contents
- `2026-05-20-sdlc-prework-nontechnical.md` — outline, pending alignment on contents

## Audience & context

- ~15 people, four "hats": **product, design, QA, engineering**.
- **Technical mix.** Engineers work in code, terminals, and repos. Product, design, and QA in this team are **GUI-only** — they don't open terminals or write code. Both populations are accommodated; non-technical attendees have a dedicated pre-work track.
- Tool fluency: Jira-native, existing codebase, some design tooling. **Little to no exposure to agentic AI tooling.** **No skeptics in this cohort** — the group is dedicated and willing.
- **Canonical tooling:** **VS Code with the Claude Code extension.** Every cohort exercise assumes the extension UI. CLI Claude Code is available to engineers who prefer it, but is not the canonical surface.
- Pivot from prior work: the SDLC skill set in this repo (`/sdlc:capture`, `/sdlc:plan`, `/sdlc:design`, `/sdlc:qa`, `/sdlc:execute`, `/sdlc:review`) becomes **training material and a starting scaffold** — the team will adapt it, not adopt it whole.

## North Star — what "graduated" means at session 6

The team leaves the program with:

1. **Mindset shift.** "AI is hype/scary/magic" → "Claude is a tool I drive; it has a cost and a benefit and I can reason about both."
2. **Workflow v0.1.** A collaborative, Jira-integrated workflow exists and runs at least once end-to-end. Imperfect by design.
3. **Guardrails.** Explicit norms for what's safe to automate, what requires review, what stays human-only.
4. **Feedback loop.** A standing cadence for editing skills/hooks, recording learnings, and improving the workflow without an outside facilitator.
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
| S2 | Scaffolding | Parallel pod iterations — each pod refines one ticket with **all four hats contributing** |
| S3 | Scaffolding | Sequential walk — one ticket moves across all four hats in order |
| S4 | Coaching | Iteration pauses mid-flow to author a needed skill |
| S5 | Coaching → fading | Full iteration with silent facilitator |
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
  - *Engineering attendees additionally:* the repo cloned locally.
  - *Non-technical attendees:* follow the non-technical pre-work guide; pre-S1 coaching hour offered as support.

### Coaching hours pattern

Coaching hours run **separately from class** — roughly one hour, once per day, ~5 days per week. Across the program that's ~30 coaching hours supporting 6 classes (a ~5:1 ratio). Drop-in, with a posted daily focus.

- **Purpose.** Carry the content that doesn't fit the embedded-iteration format: hat-specific worked examples (the "stations" from earlier drafts), skill-anatomy deep-dives, MCP setup help, hat-pure authoring time, second-pass on a missed concept, individual hand-holding, support for the non-technical pre-work track.
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

**Concept beat (one, embedded):** *Agent* + *prompt*. Defined inside the iteration, not before.

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

**Coaching threads (week 1):** install / MCP friction (esp. for non-technical attendees coming off pre-work), second turn at the keyboard for anyone who needed more time, deeper Q&A for the curious, repeated pre-S1-style coaching for late starters.

**Success signal:** every learner has used Claude on something native to their own role and can say "an agent is X, a prompt is Y" in their own words.

---

## Session 2 — Pod micro-iteration: "all four hats around one ticket"

**Posture:** Scaffolding. Pods work in parallel; facilitators float; concept surfaces when the cross-hat pattern is visible across pods.

**Goal:** Each pod takes ONE real ticket and refines it with explicit contribution from **every hat in the pod** — PM intent, design UX, QA conditions, engineering feasibility. The repeated *cross-hat* structure across pods is what makes the skill concept feel inevitable.

**Students will be able to:**
- Contribute their role's perspective to a pod's collaborative grooming of one ticket (PM intent, design UX, QA conditions, eng feasibility)
- Recognize a "skill candidate" — a repeated cross-hat pattern worth naming
- Invoke an existing `/sdlc:*` skill within an iteration
- Name one recurring task in their own hat that could become a skill

**Concept beat (one, embedded):** *Skill* — a named, reusable playbook. Surfaced at the moment multiple pods have visibly cycled through all four hats in their grooming dance.

**Pre-work:** Each pod nominates one ticket to groom. The ticket should have **surface area for all four hats** — at least one of: a vague AC, an unclear UX angle, ambiguous feasibility, fuzzy intent. A ticket that only PM can speak to is the wrong choice for this exercise.

**Agenda (60 min):**
1. **Recall (3 min).** "One thing you tried this week."
2. **Frame (2 min).** "Each pod takes one ticket. *Every hat in the pod contributes* — PM intent, design UX, QA conditions, eng feasibility. The ticket leaves the session with all four lenses on it."
3. **Pods groom — round 1 (15 min).** Pods work the ticket together, each hat chiming in as Claude helps articulate their angle. Facilitators float and listen for cross-hat patterns ("OK design, your turn — what does this look like to the user?" / "QA, where could this break?").
4. **Concept beat (10 min).** Pause when ≥2 pods have visibly involved all four hats. "Notice the dance you just did? PM intent, design UX, QA conditions, eng feasibility — different ticket, same pattern. That's a *skill* candidate. Here's one we already have." Run one `/sdlc:*` skill briefly against the same kind of task.
5. **Pods groom — round 2 (20 min).** Pods invoke the skill where it fits, adapt it, or keep doing their own dance.
6. **Cross-pod share (8 min).** One ticket per pod: before and after. One observation each — specifically: *was there a hat whose contribution surprised you?*
7. **Close (2 min).** Each hat names — aloud — one recurring task *their* hat could turn into a skill.

**Coaching threads (week 2):** hat-specific worked examples on rotation across the week (product / design / QA / eng); skill-anatomy deep-dive for the curious.

**Success signal:** every pod has a ticket groomed through all four lenses; every learner — including QA and engineers — can point to a moment when their hat's contribution mattered, and a moment when a skill would have saved effort.

---

## Session 3 — Walk-the-seam micro-iteration: "one ticket moves across all four hats in sequence"

**Posture:** Scaffolding. Each role drives their segment; the whole room watches the seam.

**Goal:** A real ticket walks **sequentially** across capture → plan → design → QA → execute in real time, with each role's representative driving their segment. The whole room sees — physically — where context drops between hats. (S2 was *parallel* cross-functional grooming; S3 is *sequential* hand-off across the workflow.)

**Students will be able to:**
- Drive their role's ~7-minute segment in a cross-functional ticket walk
- Identify at least one "context drop" at a hat-to-hat seam
- Describe in one sentence what an MCP does
- Distinguish "Claude reads Jira" (in scope today) from "Claude writes to Jira" (deferred to S6 guardrails)

**Concept beat (one, embedded):** *MCP* — how Claude reads/writes existing systems (Jira today). Surfaces at the first handoff where context needs to move from one role's head into the next role's view.

**Pre-work:** Each hat group nominates one small real ticket. Group votes at session start.

**Agenda (60 min):**
1. **Recall (3 min).** "One thing you tried this week."
2. **Pick the ticket (3 min).** Facilitator pre-screened for "walks in 30 min."
3. **Frame (2 min).** "One ticket, four hats, ~30 minutes total. Each role drives ~7 min. The seam is the point."
4. **Capture + plan (10 min).** Product drives. Facilitator captures the seam on a board.
5. **Concept beat (10 min).** At the design handoff, pause. "How does design get context right now? Through Jira, manually. What if Claude could read the ticket directly?" Demo Jira MCP live: Claude pulls the ticket, summarizes, proposes a design brief.
6. **Design + QA + execute (20 min).** Each role drives ~7 min, Claude in the loop. Facilitator keeps capturing the seam.
7. **Reflect (10 min).** Where did context drop? Where did Claude actively help? Items captured for the S6 friction inventory.
8. **Close (2 min).**

**Coaching threads (week 3):** anyone who wants to walk their own ticket through the seam; Jira MCP setup help; deeper MCP exploration (read vs. write — write deferred to S6 guardrails).

**Success signal:** a shared diagram of the team's seams exists with at least three named "context drops," and the room has seen Claude+MCP visibly help at least one handoff.

---

## Session 4 — Authoring micro-iteration: "the skill we need doesn't exist yet"

**Posture:** Coaching. Learners drive; facilitator catches the surfacing moment.

**Goal:** The group writes a real skill, mid-iteration, in response to felt need. Each hat leaves with a commitment to a v0.0 they will draft this week.

**Students will be able to:**
- Contribute to drafting a skill file collaboratively in real time
- Identify the frontmatter and "How to run" sections of a skill
- Invoke the just-authored skill within the same iteration
- Commit to a specific v0.0 skill they will draft for their own hat this week

**Concept beat (one, embedded):** *Skills are text the team owns and edits.* Surfaces when the running iteration hits a step that would benefit from a not-yet-existing skill.

**Pre-work:** Each hat shows up with one repeated task in mind (carried over from S2's closing commitment).

**Agenda (60 min):**
1. **Recall (3 min).** "One thing your hat's helper should *never* do." (Seeds S6 guardrails.)
2. **Frame & pick the iteration (5 min).** Group picks a small ticket. Facilitator privately notes the moment they expect a skill to be needed.
3. **Iteration round 1 (12 min).** Group drives. Facilitator lets them hit the predicted moment.
4. **Concept beat (10 min).** "Stop. We need a thing we don't have. Let's write it together." Open a `.md` file, walk through frontmatter and "How to run" structure live, with the room's input. Save it. Commit it.
5. **Iteration round 2 (15 min).** Group resumes, invoking the new skill where it fits. Notice the difference.
6. **Cross-hat commitments (10 min).** Each hat names *their* skill — the v0.0 they will draft this week. Posted on the wall (or shared doc).
7. **Close (5 min).** Between-session prompt: "Draft your v0.0. Bring it to S5."

**Coaching threads (week 4):** hat-pure authoring with a facilitator coaching structurally; **git mechanics for non-technical attendees via VS Code's git GUI** (not the terminal); structural feedback ("does this actually capture what your hat does?").

**Success signal:** one skill exists in the repo that did not exist 60 minutes ago, written by the room; every hat has committed to a v0.0 they'll draft this week.

---

## Session 5 — Full-flow micro-iteration: "real work, silent facilitator"

**Posture:** Coaching → fading. Group drives end-to-end with their own skills; facilitator intervenes only after a 2-minute stall.

**Goal:** A real iteration runs with the team's own skills. Friction is captured, not solved. Hook/guardrail intuition is seeded — not yet decided.

**Students will be able to:**
- Drive an end-to-end iteration using the team's own skills with minimal facilitation
- Distinguish a "hook" (auto-runs) from a "guardrail" (human gate)
- Capture a friction item into the shared inventory
- Diagnose at least one painful repeat as a hook *or* guardrail candidate (not both)

**Concept beat (one, embedded):** *Hooks and guardrails — where do they come from?* Surfaces at the painful repeat. The room learns the distinction by feeling it, not by hearing it.

**Pre-work:** Each hat brings their v0.0 skill polished from the week. Each hat also brings one small deliverable they could realistically ship.

**Agenda (60 min):**
1. **Recall (3 min).** "Did your v0.0 see real work? What broke?"
2. **Pick & frame (5 min).** Group picks one deliverable. Criterion: "small enough to run in 25 minutes." Facilitator vetoes anything bigger. State the norm: "I'm silent unless you've been stuck >2 min."
3. **The iteration (25 min).** Trainees drive `/sdlc:capture` → `/sdlc:plan` → role-specific skills → `/sdlc:execute` → start of `/sdlc:review`. Facilitator captures friction silently.
4. **Concept beat (10 min).** Pause at the most painful repeat. "That step you just did three times — what does that want to be? A *hook* (it just happens) or a *guardrail* (it always gets a human gate)?" Surface the distinction; defer decisions to S6.
5. **Friction inventory completion (10 min).** Group adds anything else painful to the shared list for S6.
6. **Close (7 min).** Iteration may not be done — coaching hour can finish it. Frame S6: "Last session is *yours*. Bring everything you want to change."

**Coaching threads (week 5):** finishing the iteration if it ran long (likely); deepening the friction inventory; for the eager, sketching a candidate hook *or* guardrail (not both).

**Success signal:** a real iteration ran end-to-end (possibly continuing into coaching hour), a friction inventory exists, and the room has *felt* — not just heard — what hooks and guardrails are for.

---

## Session 6 — Meta-iteration: "the workflow is the artifact"

**Posture:** Fading. The team facilitates itself on its own workflow. The facilitator's last job is to *not* lead.

**Goal:** Institutionalize self-improvement. The team leaves with codified guardrails, edited skills, named owners, a written cadence, and a charter.

**Students will be able to:**
- Populate the four-quadrant guardrails canvas with examples from lived experience this program
- Edit a skill they own — specifically: delete something they no longer want
- Name the owner, cadence, and inbox location for ongoing improvement
- Co-author and post the team's written charter

**Concept beat (one, embedded):** *The feedback loop itself.* The same capture → plan → edit → review pattern applied to the workflow, not to product features.

**Pre-work:** Re-read the S5 friction inventory. Bring one proposed change.

**Agenda (60 min):**
1. **Quick retro (10 min).** Plus / delta / questions on the program. Facilitator captures silently — does not respond yet.
2. **Frame the meta-iteration (2 min).** "Today's artifact is our own workflow. We capture, plan, edit, review *it*."
3. **Capture (5 min).** Pull friction items from S5 + the retro into one consolidated list.
4. **Concept beat (10 min).** Present the *guardrails canvas* (four quadrants: safe-to-auto / run-then-review / human-gate / never). Group populates from lived examples this program — no hypotheticals.
5. **Plan + edit (15 min).** Hat groups trim/edit their skills based on the canvas. **Goal is deletion, not addition.** Deeper edits continue in coaching hour.
6. **Cadence decision (8 min).** Owners per skill, retro rhythm, where friction items go (`.sdlc/INBOX.md` is right there). Who runs the next retro, when.
7. **Charter (8 min).** A short written commitment (one page max). What we agreed to. Posted somewhere visible.
8. **Close (2 min).** No homework. The cadence *is* the homework now.

**Coaching threads (week 6):** deeper skill editing; one-on-one with named owners to onboard them to their ongoing responsibility; exit interviews / Level-2 data capture if leadership wants it.

**Success signal:** the team leaves with (a) edited skills they own, (b) a populated guardrails canvas, (c) a written charter naming owners and cadence — and the facilitator does *not* leave with a list of follow-ups.

---

## Materials to build

Roughly in order of dependency:

1. **Facilitator guide** — companion document at `2026-05-20-sdlc-facilitator-guide.md` (currently a structural outline pending alignment). Will carry rehearsed scripts, predicted surfacing moments and fallback prompts, facilitator risks and mitigations, anti-patterns, and recovery moves.
2. **Participant handouts** — one-pager per session with the concept, the iteration brief, and the between-session prompt.
3. **Infra runbook** — VS Code install, Claude Code extension install + authentication, Jira MCP setup against the sandbox project, repo clone (engineering attendees only). Sanity check tested by a non-engineer.
4. **Non-technical pre-work guide** — companion document at `2026-05-20-sdlc-prework-nontechnical.md` (currently an outline). GUI-only, screenshot-driven path to "ready state" for product, design, QA, and any GUI-native attendee. Supported by the pre-S1 coaching hour.
5. **Skill scaffolds** — adapted versions of the `/sdlc:*` skills with placeholders for team-specific bits. Consumed in S2 (demo'd) and S4 (authored).
6. **Coaching-hour curriculum** — weekly themes for the ~30 coaching hours; each day has a stated focus, materials, and "who this is for." Includes hat-specific worked examples on rotation.
7. **Worked examples per hat** — recorded screencast + written script. Used in coaching hours, not in main sessions. Anyone who falls behind on a hat-specific concept catches up here.
8. **Guardrails canvas template** — used in S6 (and ongoing).
9. **Charter template** — used in S6.
10. **Recall prompts** — six prompts (one mid-week between each pair of sessions). Short, single question.
11. **Evaluation instrument** — light. Pre-survey (S1), post-survey (S6), and one optional follow-up at +60 days to measure retention/adoption.

## What we will **not** do

- **No bootcamp / cert.** Adult learners adopting new tooling don't need a credential; they need wins and safety.
- **No concept-only or demo-only sessions.** Every session is a real iteration. Concepts live inside iterations, never alongside.
- **No synthetic exercises.** Every iteration uses real tickets from real backlogs. Synthetic work doesn't produce real surfacing moments.
- **No "here's the perfect workflow we built for you."** The point is they build it. We provide scaffolds.
- **No automation before friction.** Hooks come in S5/S6 from felt pain, not from a feature checklist.
- **No prescribing tools beyond Claude + Jira MCP.** Confluence MCP, code-review automation, etc. are downstream of this program.
- **No 1:1 coaching as part of the six sessions.** Offered separately if requested.

## Risks to the program itself

| Risk | Mitigation |
|------|------------|
| One role checks out early ("this is engineering's thing") | S2/S3 are explicitly cross-role. Facilitator names the risk in S1. |
| Infra/setup eats S1 | Required pre-work + dedicated pre-S1 coaching hour (especially for non-technical attendees). |
| Non-technical attendees arrive at S1 unready because pre-work was unclear or unsupported | Screenshot-driven non-technical pre-work guide; pre-S1 coaching hour; track pre-work completion before S1 and intervene early. |
| Facilitator capacity for ~30 coaching hours over 6 weeks is hard to staff | Identify two facilitators who share rotation; or compress cadence (e.g., 3/week instead of 5) if 5 isn't sustainable. Plan capacity at program kickoff, not week 3. |
| Champion runs ahead and bores the group | Channel them into mentor role within their pod. |
| Leadership treats this as "AI adoption training" and measures usage rather than outcomes | Pre-engagement with leadership to align on Level-3/Level-4 Kirkpatrick metrics, not Level-1 satisfaction or Level-2 usage. |
| Workflow drifts back to pre-Claude habits after week 8 | The S6 charter names an owner per skill and a 6-week check-in cadence. |
| The concept beat misses its natural surfacing moment | Facilitator has a pre-planned prompt to call the moment ("I expected us to want X here — anyone else feel it?") and a hard fallback at 35 min. Practiced in pilot. |
| The S1 micro-iteration is too ambitious and people drown on day one | S1 iteration scope is fixed and rehearsed: refine one ticket's description and AC. Nothing larger. |
| Coaching-hour attendance is too low and learners fall behind on stationed content | Communicate honestly in S1 that coaching hours are expected-for-catch-up. Track attendance; if it dips, re-pitch the why. |
| Facilitator doesn't have the skill to drive iteration + listen for surfacing + pause at the right time | This is not a green-facilitator format. Either assign senior facilitators or run a facilitator-prep session before S1. |

## Open decisions (defer, not block)

- **Session length.** Fixed at 60 min + 30-min coaching hour. If coaching-hour attendance is very low after S1–S2, re-pitch the "why" rather than dropping them — the embedded format depends on them.
- **Facilitator skill.** Embedded format requires a facilitator who can drive an iteration, listen for the surfacing moment, and pause at the right time. Either pre-screen for this skill or run a facilitator-prep session before S1.
- **Sync vs async between sessions.** Recommended sync recall prompts (Slack thread); could be async-only if team is remote-async.
- **Which Jira MCP.** Pick before infra runbook is built. Lock by end of design.
- **Whether to record sessions.** Default no, for psychological-safety reasons. Can be reversed by team consent. Coaching hours never recorded.
- **What "sandbox" Jira project to use.** Real project recommended (real stakes = real learning), but a forked sandbox is acceptable if real is too risky.

## Next steps (downstream of this design)

1. Confirm logistics with stakeholders (length, cadence, attendance, sandbox).
2. Pick Jira MCP and write the infra runbook.
3. Identify facilitators and run a facilitator-prep session focused on the embedded-iteration craft (surfacing moments, the 35-min fallback, silent-facilitator discipline in S5).
4. Draft S1 facilitator guide end-to-end as the prototype, including the rehearsed iteration script; iterate before drafting S2–S6.
5. Pilot S1 with a friendly subset (3–4 people) before running with the full 15. Pay special attention to whether the concept beat lands at the right moment.
6. Build S2–S6 guides in order, incorporating pilot lessons. Each guide names its predicted surfacing moment and its fallback prompt.
