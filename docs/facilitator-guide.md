# Facilitator Guide

> For the people running the room. The [Run of Show](workshop-flow.md) is the timing; this is *how to hold it.* Format adapted from Aldric's facilitator guide — observable cues, talking points, risks, recovery.

## Cross-cutting

- **You demo the loop once, then get out of the way.** The learning is them doing it, not you explaining it.
- **Protect the one win.** If time gets tight, everyone leaves with real output — Product: *a reviewed OpenSpec change uploaded to their ticket;* QA: *sharp test cases saved.* The CLAUDE.md and the saved skill are stretch. Cut from the top of the stretch, never from the win.
- **Confirm-to-push is the safety story — say it out loud.** Every time the agent writes to Jira, the human reads the diff first and says go. Model it in the demo; insist on it in the rooms. This is what makes "let the agent touch our real backlog" okay.
- **Messy input is correct.** If someone apologizes for rough notes, tell them that's the ideal input. The agent does better with raw material than with a polished paragraph.
- **Meet them where they are.** Their tickets mix formats. We're nudging toward clear, testable specs — not declaring their old tickets wrong.

## Two-room coordination

- **A (Trace) → Product. B (Zach/Chris) → QA.** Both rooms run [Section 2](section-2-breakout.md); the prompts are on the page so neither facilitator has to improvise.
- Agree the **rejoin time** before you split. When you come back, **each facilitator nominates one person** to show in [Section 3](section-3-qa.md) — don't put people on the spot cold.
- If one facilitator falls through: collapse to one room, do **Product live**, and tell QA to follow the QA prompts on the same screen. The page supports a solo run.

## Per-section

### Section 1 — Orient
**Cues it's landing:** someone reacts to Claude *reading the ticket from Jira* ("oh, it just pulled it"). That surprise is the hook — name it and move.
**Fallback if flat (by ~10 min):** *"Quick — what did you just see it do? It read your ticket and told you what's missing. That's the whole job today."*
**Risks:**
- *Demo runs long.* Mitigation: the demo is rehearsed in the dry run; if it bleeds, cut the grill to **two** questions, not zero.
- *Jira won't connect live.* Mitigation: you drive on **your** Jira; attendees connect in the room with B floating. Never spend more than 2 minutes on one person's connection in the open — move it to the breakout.

### Section 2 — Breakout
**Product cues it's landing:** someone stops trying to write the spec themselves and lets the **Explore** phase ask them questions; someone says "oh — I never decided what happens when it's empty." The OpenSpec change appears under `openspec/changes/`.
**QA cues it's landing:** people stop reading the prompt page and start typing their own follow-ups; someone says "it caught the regression I'd have missed."
**Fallback if stuck (by ~10 min in):** *"Don't write it yourself yet. Dump everything you've got and let the explore phase ask you questions. We turn it into a proposal after."*
**Risks:**
- *Someone has no ticket.* Mitigation: hand them [CHK-3334](example-tickets.md) and have them explore + spec it.
- *OpenSpec / install friction (Product).* Mitigation: have Claude install it (`npm i -g @fission-ai/openspec`) or use a pre-built workspace; never burn more than ~2 min — move on with the training repo and circle back.
- *They treat Explore as "give me the answer fast."* Mitigation: *"This phase is for thinking. Let it ask you the awkward questions — that's where the spec gets good."*
- *They try to fill in `design.md` / `tasks.md`.* Mitigation: remind them those are the **developer's**; Product owns Explore → Proposal → Spec.
- *The first proposal looks "good enough" and they stop.* Mitigation: *"Read it as the dev who has to build it — name one thing they'd still guess."* There's always one.
- *Push anxiety.* Mitigation: reassure — the draft is local; the push shows what it'll write; they say go. Let them push something small first.
- *Over-speccing.* Mitigation: hard rule — the spec covers the behavior that matters, not every theoretical case. One screen of real scenarios beats ten of filler.

### Section 3 — Q&A
**Cues:** people comparing the before/after, not just praising the tool.
**Risk:** turns into tool-praise or tool-complaints. Mitigation: keep pulling back to *"what did it change about your ticket?"*

### Closing
**Risk:** the kata gets skipped for time. Mitigation: it's non-negotiable — it's how next week gets designed. Even 60 seconds of "number + one line" is enough.

## Dry-run checklist

- [ ] Demo loop runs end-to-end on a real ticket, including a **reviewed push**
- [ ] One full **Product** run on a real ticket — **Explore → Propose → review the spec → upload to Jira** — time it, note friction
- [ ] One full **QA** loop producing a test-case markdown file
- [ ] OpenSpec **install + init** tested on a non-facilitator machine (or the live "Claude builds it" path)
- [ ] The **capture finale** once — CLAUDE.md written, a skill saved, then re-invoked
- [ ] Jira connect tested on at least one **non-facilitator** machine
- [ ] You know your **cut line**: if you're at 0:45 and a room isn't done, stop at "reviewed change/test cases uploaded" and skip the finale
