# Run of Show

> **The page to keep open while you facilitate.** Everything you need to move through the hour is here or one click away. 60-minute hour, Product + QA, two rooms.

## At a glance

| Section | Time | Who | What |
|---------|------|-----|------|
| **1 — Orient** | 0:00–0:17 | Everyone | Level-set, the gentle frame, connect Jira, watch the whole loop once (live demo) |
| **2 — Breakout** | 0:17–0:47 | Two rooms | You run the loop on your own ticket. Product → story + AC. QA → test cases. |
| **3 — Q&A** | 0:47–0:55 | Everyone | Two people show a result, open questions |
| **Closing** | 0:55–1:00 | Everyone | Plus/delta retro + rate the hour |

> **Buffer:** Section 2 carries the slack. If a room is flying, push the capture finale (CLAUDE.md + a saved skill). If it's slow, cut the finale and protect the one win: **sharp AC pushed to the ticket.**

## Facilitators & rooms

| Room | Facilitator | Output |
|------|-------------|--------|
| **Product** | Facilitator A (Trace) | A user story with testable Given/When/Then AC, pushed to their own ticket |
| **QA** | Facilitator B (Zach / Chris) | Full test-case drafts from a story's AC, saved as markdown |

Open and close happen together; the split is only for the build.

## What's in the room (check before you start)

- [ ] **Claude Code in VS Code**, signed in, for every attendee
- [ ] **Jira connected (MCP)** — attendees on their own; a facilitator's Jira for the demo
- [ ] **Training repo** cloned — ships with the `grill-me` skill, the [example tickets](example-tickets.md), and a `scratch/` folder to work in
- [ ] Each attendee has **one real ticket** + whatever notes/transcript they have about it
- [ ] [Example tickets](example-tickets.md) open, to paste as "good examples"

## The spine (the whole hour in one line)

> **Dump everything you have + a good example → ask for a first pass → read it cold → if it's not good, `grill me` and build it step by step → review the draft → push to the ticket → capture the way you like it.**

Everything below is that loop, twice: once on screen in Section 1, once on your own ticket in Section 2.

## The pages

1. [Section 1 — Orient](section-1-orient.md) — level-set + the live demo
2. [Section 2 — Breakout](section-2-breakout.md) — **the activity, with every prompt** (Product + QA)
3. [Section 3 — Q&A](section-3-qa.md) — show & ask
4. [Closing](closing.md) — retro + the Return-on-Time kata
5. [Facilitator Guide](facilitator-guide.md) — cues, risks, recovery, two-room coordination
6. [Example Tickets](example-tickets.md) — the four real tickets and what each is for

## Dry-run focus

Running this as a dry run? Don't try to time all 60. Do this:

1. Section 1 demo end-to-end **once** — find where the Jira connect or the push feels shaky.
2. **One full Product loop** on a real ticket, including **confirm-to-push**. That's the riskiest live moment; rehearse it.
3. The **capture finale** once (CLAUDE.md + save a skill), so you can demo it confidently.
4. Closing kata, just to time it.

Note every spot where you'd reach for a prompt you didn't have — those go in the [prompt sections](section-2-breakout.md).

## Housekeeping (read at the top)

- **Speak up the moment a question lands.** Mid-build questions are the useful ones.
- **Nothing reaches Jira without you confirming it.** You review a local draft first, every time.
- **Messy input is the point.** Half-formed notes feed the agent better than a polished paragraph.
