# Specs & Test Cases with Claude: Product & QA

Welcome. This is a hands-on session. You bring one real **feature** you actually need to work; you leave with it broken into **Jira tickets a developer can build from**: **Product splits the feature into value-bearing tickets, QA writes the test cases**: and a saved way of doing it again that works *the way you work*.

> **Tooling:** We work in **Claude Code inside VS Code**: the same sidebar you've been setting up in the drop-ins. No terminal required.

## What this session is

One job, done well: **take a feature you own and, with Claude, break it into clean tickets, live.** Product explores the whole feature, splits it by behavior, and creates an **Epic + a Story per behavior + sub-tasks**: each Story backed by an OpenSpec proposal and spec, each delivering real business value. QA turns a story's acceptance criteria into **test cases**.

This is not a slides session, and it's not about learning a tool for its own sake. It's your normal work, thinking a feature through, splitting it, writing test cases, done with a teammate that reads instantly and forgets nothing.

## The win you leave with

By the time we close, you have:

1. **A real feature, turned into buildable tickets**: 
   - **Product:** a **ticket tree in your own Jira project**: an Epic, a Story per behavior (each with its business-value "Why"), sub-tasks underneath, backed by a reviewed OpenSpec proposal + specs.
   - **QA:** test cases to the team standard (drafted or cleaned up) saved to `qa-shared-tools`, plus a shared `write-test-cases` skill committed back so the team drafts to the same bar.
2. **A captured preference**: the one thing you kept insisting on, written into a `CLAUDE.md` so Claude does it that way next time without being told.
3. *(Stretch)* **Your own skill**: a saved, one-command way to do it again the way you like it.

If you only get #1, that's the session well spent.

## Who's in the room

| Room | You produce | Best fit |
|------|-------------|----------|
| **Product** | A **value-bearing ticket tree**: Epic + Stories + sub-tasks, from a real feature (Explore → split → Propose → tickets) | PM / UX |
| **QA** | Test cases to the team standard + a shared skill, in `qa-shared-tools` | QA |

We start together, split into the two rooms for the build, and come back together to compare and ask anything.

## The North Star

This session is one step toward where this whole engagement is going:

- **Mindset**: treat Claude as a teammate: know its limits, its costs, its strengths.
- **Workflow**: a Jira-integrated way of working that runs end to end.
- **Safety**: a clear sense of what's safe to push and what needs your eyes first.
- **Cadence**: a repeatable routine you actually keep using after we leave.

## How the session runs

| | |
|---|---|
| **Section 1, Orient** | All together. Level-set, a quick demo of the whole loop, connect Jira. |
| **Section 2, Breakout** | Two rooms. You do the work on your own feature. |
| **Section 3, Q&A** | All together. Show one result, ask anything. |
| **Closing** | Quick retro + rate the session. |

Facilitators: see the [Run of Show](workshop-flow.md) and [Facilitator Guide](facilitator-guide.md).

## Before you arrive

Do the [Prerequisites](prerequisites.md). One thing is required, Claude working in VS Code, and one thing makes the session real: **bring a feature you actually need to work.**

**Product:** open Claude in **your own folder** (no new repo) with **OpenSpec** installed and [`openspec-process.md`](openspec-process.md) added. **QA:** you'll work in your team's shared **`qa-shared-tools`** repo (Azure DevOps), where the standard and example live. The [Prerequisites](prerequisites.md) page has the details.
