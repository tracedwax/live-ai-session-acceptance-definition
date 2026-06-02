# Facilitator Guide

> For the people running the room. The [Run of Show](workshop-flow.md) is the timing; this is *how to hold it.* Format adapted from Aldric's facilitator guide — observable cues, talking points, risks, recovery.

## Cross-cutting

- **You demo the loop once, then get out of the way.** The learning is them doing it, not you explaining it.
- **Protect the one win.** If time gets tight, everyone leaves with real output — Product: *a value-bearing ticket tree (at least an Epic + 2 Stories) in their own Jira project;* QA: *sharp test cases saved.* The CLAUDE.md and the saved skill are stretch. Cut from the top of the stretch, never from the win.
- **Confirm-before-create is the safety story — say it out loud.** Before the agent creates tickets, the human reads the whole tree as a plan and says go. Tickets land in the attendee's **own project**, and a wrong one is one click to delete — that, plus the review, is what makes "let the agent touch Jira" okay. (The **Mocking Project** `MP` — https://aspenware.atlassian.net/jira/software/projects/MP/boards — is a fine sandbox backup for anyone skittish.)
- **"Every Story delivers value" is the spine.** The teaching moment is splitting by *behavior*, not layer. When you see a "frontend/backend" split, stop and fix it out loud — that's the whole point of the hour.
- **`grill me` does the hard part.** They don't need to know the right questions; `grill me` finds the gaps and the answers become ticket content. Name this when it happens.
- **Messy input is correct.** If someone apologizes for rough notes, tell them that's the ideal input. The agent does better with raw material than with a polished paragraph.
- **Meet them where they are.** Their features mix formats. We're nudging toward clear, testable, well-split tickets — not declaring their old work wrong.

## Two-room coordination

- **A (Trace) → Product. B (Zach/Chris) → QA.** Both rooms run [Section 2](section-2-breakout.md); the prompts are on the page so neither facilitator has to improvise.
- Agree the **rejoin time** before you split. When you come back, **each facilitator nominates one person** to show in [Section 3](section-3-qa.md) — don't put people on the spot cold.
- If one facilitator falls through: collapse to one room, do **Product live**, and tell QA to follow the QA prompts on the same screen. The page supports a solo run.

## Per-section

### Section 1 — Orient
**Cues it's landing:** someone reacts to Claude *reading the ticket from Jira* ("oh, it just pulled it"), and again when `grill me` surfaces a hole they hadn't thought of. Those two surprises are the hooks — name them and move.
**Fallback if flat (by ~12 min):** *"Quick — what did you just see it do? It read the feature, found what's missing, and split it into tickets that each do something. That's the whole job today."*
**Risks:**
- *Demo runs long* (it's bigger now — explore → grill → split → propose → tickets). Mitigation: rehearse it in the dry run; if it bleeds, cut the grill to **two** questions and create just **one** Story live, then describe the rest.
- *Jira won't connect live.* Mitigation: you drive on **your own** Jira; attendees connect in the room with B floating. Never spend more than 2 minutes on one person's connection in the open — move it to the breakout.

### Section 2 — Breakout
**Product cues it's landing:** someone stops trying to write tickets themselves and lets **Explore + `grill me`** surface the gaps; someone says "oh — I never decided what happens when it's empty"; the split lands on *behaviors* not layers; the Epic + Stories appear in their Jira project.
**QA cues it's landing:** people stop reading the prompt page and start typing their own follow-ups; someone says "it caught the regression I'd have missed."
**Fallback if stuck (by ~10 min in):** *"Don't write tickets yet. Dump everything, let `grill me` find the holes, then split by behavior. The tickets come last."*
**Risks:**
- *Someone has no feature.* Mitigation: hand them [CHK-3334](example-tickets.md) (or treat the whole guest-checkout example as the feature) and have them split + spec it.
- *OpenSpec / install friction (Product).* Mitigation: have Claude install it (`npm i -g @fission-ai/openspec`) in their own folder; never burn more than ~2 min — circle back.
- *They split by technical layer ("frontend/backend").* Mitigation: **the** correction to make — *"a layer ships nothing on its own. Split by what a user can see work."* Catch it every time.
- *They treat Explore as "give me the answer fast."* Mitigation: *"This phase is for thinking. Let `grill me` ask the awkward questions — that's where the tickets get complete."*
- *They try to fill in `design.md`.* Mitigation: remind them that's the **developer's**; Product owns Explore → split → Proposal → Spec.
- *One giant Story (too big).* Mitigation: point at the sizing rule — >6–8 WHEN/THEN means split it; that's one more Story.
- *Ticket-creation anxiety.* Mitigation: the plan shows exactly what it'll create, they say go, and a wrong ticket deletes in one click. Let them create one Story first. (Offer the **Mocking Project** `MP` sandbox if someone's still uneasy.)
- *Over-speccing.* Mitigation: hard rule — cover the behavior that matters, not every theoretical case. One screen of real scenarios beats ten of filler.

### Section 3 — Q&A
**Cues:** people comparing the before/after, not just praising the tool.
**Risk:** turns into tool-praise or tool-complaints. Mitigation: keep pulling back to *"what did it change about your feature — and did every ticket end up with real value?"*

### Closing
**Risk:** the kata gets skipped for time. Mitigation: it's non-negotiable — it's how next week gets designed. Even 60 seconds of "number + one line" is enough.

## Dry-run checklist

- [ ] Demo loop runs end-to-end on a real feature, including **`grill me` finding a gap** and a **confirmed ticket-tree creation** in a Jira project
- [ ] One full **Product** run on a real feature — **Explore → grill → split by behavior → Propose → create Epic + Stories + sub-tasks** — time it, note friction
- [ ] One full **QA** loop producing a test-case markdown file
- [ ] OpenSpec **install + init** tested on a non-facilitator machine, with `openspec-process.md` dropped in
- [ ] **Jira create access** confirmed; test-creating an Epic + Story + sub-task and deleting them (use the **Mocking Project** `MP` if you don't want demo tickets in a real project)
- [ ] The **capture finale** once — CLAUDE.md written, a skill saved, then re-invoked
- [ ] Jira connect tested on at least one **non-facilitator** machine
- [ ] You know your **cut line**: if you're at ~0:50 and a room isn't done, stop at "Epic + at least 2 Stories created" and skip the finale — Q&A is protected
