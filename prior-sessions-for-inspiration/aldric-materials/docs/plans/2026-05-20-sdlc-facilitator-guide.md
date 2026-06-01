# Agentic SDLC Training — Facilitator Guide

**Drafted:** 2026-05-21
**Revised:** 2026-05-21 — format aligned (observable cues + talking points); no-skeptic cohort; recovery moves deferred; attendance/engagement out of scope
**Status:** sketch — observable cues and talking points filled in as first pass; recovery moves still TBD; cross-cutting guidance still TBD
**Companion to:** `2026-05-20-sdlc-training-design.md`

## What lives here vs. the design doc

The **design doc** is for stakeholders, program designers, sponsors, and the cohort. It answers *what we're doing and why* — audience, north star, principles, session structure, SWBAT, materials.

**This guide** is for facilitators. It answers *how to actually run the room*. Specifically:

- Cross-cutting guidance (silent-facilitator discipline, seeding surfacing moments, participant archetypes — minus the absent skeptic, demo recovery)
- Per-session detail: observable cues for the surfacing moment, fallback prompt, talking points, facilitator risks + mitigations, recovery moves

**Out of scope** (lives elsewhere): cohort attendance, engagement metrics, program-management logistics.

---

## Cross-cutting guidance

*[TBD — scope agreed (silent-facilitator discipline, seeding surfacing moments, participant archetypes, demo recovery). Content to be drafted.]*

---

## Per-session detail

Each session uses the same template:

- **Observable cues** — what the facilitator can see/hear that means the surfacing moment is ripe
- **Fallback prompt** — what to say if cues never arrive by ~35 min
- **Talking points** — the lines that land the concept beat (not a script — say it however feels natural)
- **Facilitator risks** — extracted from the design doc
- **Recovery moves** — *[deferred — pending alignment on which scenarios warrant documentation]*

---

### Session 1 — Tiny micro-iteration: "your own work, with Claude"

**Observable cues that the surfacing moment is ripe:**
- Facilitator's demo iteration has reached its natural endpoint (the work — whatever role's work it was — is visibly improved)
- The room is silent / watching — they have just seen something work
- At least one learner has a "wait, what?" or "huh" expression
- Facilitator can point to specific actions just taken: "you saw me read, ask, react, iterate"

**Fallback prompt** (if cues haven't arrived by ~22 min):
> "Quick check — what did you just see me do? Name one thing. … That was a *prompt*. That was an *agent*."

**Talking points:**
- "You just watched me onboard a new colleague — except this colleague reads instantly and forgets nothing."
- "Two words: *agent* and *prompt*. The agent is the colleague. The prompt is the message I sent them."
- "It gets more complicated. But today, just: agent, prompt."

**Facilitator risks:**
- Eager engineer jumps to advanced usage and intimidates the room. *Mitigation:* assign them as observer in their pod.
- Tool friction eats setup. *Mitigation:* pre-S1 coaching hour 2+ days before; backup recording of the demo.
- Facilitator's iteration bleeds past 10 min and crowds the concept beat. *Mitigation:* the demo is rehearsed; if it bleeds, *cut the iteration*, not the concept beat.
- Non-technical attendee arrives unready (pre-work incomplete). *Mitigation:* facilitator assigns a "second-screen" buddy to each non-tech attendee for help during the pod lab.

**Recovery moves:** *[TBD]*

---

### Session 2 — Pod micro-iteration: "all four hats around one ticket"

**Observable cues that the surfacing moment is ripe:**
- Two or more pods have visibly involved **every hat** in their conversation (not just PM driving while others watch)
- Facilitator floating overhears cross-hat handoffs: "OK design, your turn — what does this look like?" / "QA, where could this break?" / "Eng, what would this take?"
- A pod member spontaneously notes how a different hat's contribution shifted the ticket ("wait, that AC isn't testable" / "the UX makes the eng cheaper")
- ~12–15 min into round 1, the cross-hat dance is visible across multiple pods

**Fallback prompt** (if cues haven't arrived by ~20 min):
> "Pause. Each pod, in one sentence: who in your pod has spoken so far, and about what? … You hear that? Different ticket, same dance."

**Talking points:**
- "Notice the dance you just did? PM intent, design UX, QA conditions, eng feasibility — every hat showed up."
- "A *skill* is exactly that — the named version of 'that cross-hat dance we just did.'"
- "Here's one we already have. Let me run it. Watch."
- "Round 2: use this skill, or don't, or adapt it. Up to you."

**Facilitator risks:**
- The concept beat doesn't land because no two pods did the same thing. *Mitigation:* facilitator can *seed* the moment by asking pods "what step did you just do?" until convergence emerges.
- Pods grooming at very different paces. *Mitigation:* facilitator assigns appropriate-size tickets at frame time.
- Round 2 collapses into "everyone uses the new skill the same way," losing the variation. *Mitigation:* explicitly invite divergence — "use it, ignore it, or adapt it."

**Recovery moves:** *[TBD]*

---

### Session 3 — Walk-the-seam micro-iteration: "one ticket moves across all four hats in sequence"

**Observable cues that the surfacing moment is ripe:**
- Product has finished their segment; design is about to begin
- Someone (probably the designer) reaches for Jira to look up the ticket
- The natural question surfaces: "wait, what was the description again?" or "do we have the ticket open?"
- Facilitator wants to demonstrate Claude reading Jira directly

**Fallback prompt** (if cues haven't arrived by ~25 min):
> "Hold on — design, where are you getting the context for what you're about to do? … Right now, by checking Jira. What if Claude could do that for you?"

**Talking points:**
- "We just hit the seam. Product had context in their head; design needs it now."
- "Right now you'd open Jira and read. Watch what happens when Claude does that for you."
- "That's an *MCP*. It connects Claude to systems you already use."
- "Read-only today. Writing to Jira is its own conversation — we'll have it in S6."

**Facilitator risks:**
- Eng or QA over-corrects upstream roles' choices. *Mitigation:* a visible norm — "your job here is your hat, not all hats."
- The walk stalls in one segment. *Mitigation:* hard 7-min per-segment timer.
- The MCP demo eats the time budget. *Mitigation:* pre-stage the MCP call so it runs in <2 min live.
- The "handoff that surfaces MCP" never arrives. *Mitigation:* facilitator can call the moment — "this is the kind of handoff where MCP earns its keep — let me show you."

**Recovery moves:** *[TBD]*

---

### Session 4 — Authoring micro-iteration: "the skill we need doesn't exist yet"

**Observable cues that the surfacing moment is ripe:**
- The group has just done something that took 3+ minutes and felt boilerplate
- Someone says "we should have a way to…" or "every time we…"
- The facilitator's predicted moment has arrived (they've been watching for it)
- A learner expresses mild frustration with repetition

**Fallback prompt** (if cues haven't arrived by ~20 min into round 1):
> "Look at what you just did. Imagine we had a thing called X. Want to make it now? It's just text."

**Talking points:**
- "Stop. You did that three times. We need a skill we don't have."
- "Open a markdown file in VS Code. That's all it is. Frontmatter on top, instructions below."
- "Save it. Commit it via the VS Code git panel — no terminal needed. Then re-run our iteration."

**Facilitator risks:**
- The predicted "skill-needed" moment doesn't surface. *Mitigation:* facilitator picks the ticket; the prediction should be high-confidence. If it still doesn't surface, name it: "I expected us to want X here — anyone else feel it?"
- Non-technical attendees feel intimidated by writing to a repo. *Mitigation:* they own *content*; engineers handle git mechanics. VS Code's git GUI makes commits manageable.
- The newly-authored skill is over-engineered live. *Mitigation:* hard rule — "v0.0 fits on one screen."
- The team writes the skill but never invokes it in round 2 (loses the felt difference). *Mitigation:* facilitator gently insists: "let's actually run it now."

**Recovery moves:** *[TBD]*

---

### Session 5 — Full-flow micro-iteration: "real work, silent facilitator"

**Observable cues that the surfacing moment is ripe:**
- The group has done the same micro-flow more than twice
- Someone says "this is annoying" or "can't this just happen"
- The friction inventory is starting to grow naturally
- Facilitator has been silent for 25+ min and the group is moving — but slowly

**Fallback prompt** (if cues haven't arrived by ~30 min):
> "Time check. That step you did three times — what does it want to be? A *hook* that just runs, or a *guardrail* that gates a human decision?"

**Talking points:**
- "I'm not going to step in here. I'm just watching."
- *[at the painful repeat]* "You did this three times. Want it to just happen, or always need a human gate? That's a hook versus a guardrail."
- "Don't decide yet. Capture it. We decide together next week."

**Facilitator risks:**
- Silence is harder than coaching. Facilitator rescues too eagerly. *Mitigation:* facilitator's only tools this session are clarifying questions, not answers.
- The "painful repeat" for the concept beat never arrives because the iteration is going well. *Mitigation:* if at 30 min there's no friction, pause anyway: "where would this have hurt at scale?"
- The 25-min budget is too tight. *Mitigation:* ruthless pre-scoping; explicit handoff to coaching hour for completion.

**Recovery moves:** *[TBD]*

---

### Session 6 — Meta-iteration: "the workflow is the artifact"

**Observable cues that the surfacing moment is ripe:**
- Retro is complete and friction items are consolidated into a single list
- The team is looking at the facilitator with "what's the framework" energy
- It's time to give shape to the lived experience of the program

**Fallback prompt:** N/A — the concept beat is structurally embedded in the canvas exercise; no fallback needed.

**Talking points:**
- "Plus, delta, questions. I'm capturing, not responding."
- "Now we iterate on our own workflow. Capture, plan, edit, review — same pattern, different artifact."
- "Four boxes: safe-to-auto, run-then-review, human-gate, never. Real examples from this program only — no hypotheticals."

**Facilitator risks:**
- The retro turns into a complaint session about Claude. *Mitigation:* the canvas exercise channels grievances into structure.
- The cadence gets agreed-to verbally but never written. *Mitigation:* charter is non-negotiable; do not adjourn without it.
- The group looks to the facilitator to "lead the meta-iteration." *Mitigation:* explicit framing — "I am observer today; you run it."

**Recovery moves:** *[TBD]*

---

## Open questions for alignment

Resolved this round:

- ~~Surfacing moments format~~ → **observable cues (checklist)**
- ~~Rehearsed material level~~ → **talking points (not full scripts)**
- ~~Cross-cutting guidance scope~~ → **confirmed (silent-facilitator discipline, seeding moments, participant archetypes, demo recovery)**
- ~~Attendance/engagement~~ → **out of scope (lives elsewhere)**

Still pending:

1. **Recovery moves.** Which scenarios warrant a documented recovery? Candidates: "the MCP breaks live during S3's demo," "VS Code update breaks an attendee's environment mid-session," "an attendee's ticket turns out to be inappropriate (e.g., contains sensitive data) once Claude reads it," "the predicted surfacing moment fires twice and we use both," "an authored skill in S4 produces nonsense and the team loses confidence." User said "unsure" — leaving as TBD until we decide which to write.
