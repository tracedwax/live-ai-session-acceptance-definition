# Specs & Test Cases with Claude — Product & QA

Welcome. This is a hands-on hour. You bring one real ticket you actually need to work; you leave with it turned into something a developer can build from — **Product writes an OpenSpec change, QA writes the test cases** — and a saved way of doing it again that works *the way you work*.

> **Tooling:** We work in **Claude Code inside VS Code** — the same sidebar you've been setting up in the drop-ins. No terminal required.

## What this hour is

One job, done well: **take a ticket you own and, with Claude, get it from rough to ready, live.** Product turns it into an **OpenSpec change** — a proposal and a spec a developer could build from. QA turns a story's acceptance criteria into **test cases**. Each room works its own real ticket, on the part of the job that's actually theirs.

This is not a slides session, and it's not about learning a tool for its own sake. It's your normal work — thinking a story through, writing test cases — done with a teammate that reads instantly and forgets nothing.

## The win you leave with

By the time we close, you have:

1. **A real ticket, turned into something buildable** —
   - **Product:** an **OpenSpec change** on your ticket — a proposal (what & why) and a spec (the behavior), reviewed by you and uploaded to Jira.
   - **QA:** test-case drafts to our standard, saved to the shared repo.
2. **A captured preference** — the one thing you kept insisting on, written into a `CLAUDE.md` so Claude does it that way next time without being told.
3. *(Stretch)* **Your own skill** — a saved, one-command way to do it again the way you like it.

If you only get #1, that's the hour well spent.

## Who's in the room

| Room | You produce | Best fit |
|------|-------------|----------|
| **Product** | An **OpenSpec change** — proposal + spec — from a real ticket (Explore → Proposal → Spec) | PM / UX |
| **QA** | Full test-case drafts from a story's acceptance criteria | QA |

We start together, split into the two rooms for the build, and come back together to compare and ask anything.

## The North Star

This hour is one step toward where this whole engagement is going:

- **Mindset** — treat Claude as a teammate: know its limits, its costs, its strengths.
- **Workflow** — a Jira-integrated way of working that runs end to end.
- **Safety** — a clear sense of what's safe to push and what needs your eyes first.
- **Cadence** — a repeatable routine you actually keep using after we leave.

## How the hour runs

| | |
|---|---|
| **Section 1 — Orient** | All together. Level-set, a quick demo of the whole loop, connect Jira. |
| **Section 2 — Breakout** | Two rooms. You do the work on your own ticket. |
| **Section 3 — Q&A** | All together. Show one result, ask anything. |
| **Closing** | Quick retro + rate the hour. |

Facilitators: see the [Run of Show](workshop-flow.md) and [Facilitator Guide](facilitator-guide.md).

## Before you arrive

Do the [Prerequisites](prerequisites.md). One thing is required — Claude working in VS Code — and one thing makes the hour real: **bring a ticket you actually need to work.**

You don't need a code repo. **Product:** in the room, Claude sets up an OpenSpec workspace for you (it creates a fresh folder and initializes OpenSpec — or sets it up inside the [training repo](https://github.com/tracedwax/ac-training-repo)). **QA:** you'll work in the real `qa-shared-tools` repo. The [Prerequisites](prerequisites.md) page has the details.
