# Run of Show

> **The page to keep open while you facilitate.** Everything you need to move through the session is here or one click away. 75-minute session, Product + QA, two rooms.

## At a glance

| Section | Time | Who | What |
|---------|------|-----|------|
| **1 — Orient** | 0:00–0:20 | Everyone | Level-set, the gentle frame, connect Jira, watch the whole loop once (live demo: feature → split → tickets) |
| **2 — Breakout** | 0:20–0:55 | Two rooms | Product → break a feature into Jira tickets (Explore → split → Propose → tickets). QA → test cases. |
| **3 — Q&A** | 0:55–1:10 | Everyone | Two people show a result, open questions (15 min — protect it) |
| **Closing** | 1:10–1:15 | Everyone | Plus/delta retro + rate the session |

> **Buffer:** Section 2 carries the slack. If a room is flying, push the capture finale (CLAUDE.md + a saved skill). If it's slow, cut the finale and protect the one win — Product: **a value-bearing ticket tree (Epic + Stories) in their own Jira project;** QA: **sharp test cases saved.**

> **Materials:** **Product** works in their **own folder** — needs **OpenSpec** (Claude installs live) and the [`openspec-process.md`](openspec-process.md) page dropped in; tickets go into the attendee's **own Jira project** (the **Mocking Project** `MP` is a shared sandbox backup — https://aspenware.atlassian.net/jira/software/projects/MP/boards). **QA** works in **`qa-shared-tools`** (ADO), which holds the standard, the `QUAL-4510` example, and the skills.

## Facilitators & rooms

| Room | Facilitator | Output |
|------|-------------|--------|
| **Product** | Facilitator A (Trace) | A **value-bearing ticket tree** in their own Jira project — Epic + a Story per behavior + sub-tasks — each Story backed by a reviewed proposal + spec |
| **QA** | Facilitator B (Zach / Chris) | Test cases to the team standard (drafted or normalized) saved to `qa-shared-tools`, plus a shared `write-test-cases` skill committed back |

Open and close happen together; the split is only for the build.

## What's in the room (check before you start)

- [ ] **Claude Code in VS Code**, signed in, for every attendee
- [ ] **Jira connected (MCP)** — attendees on their own; a facilitator's Jira for the demo
- [ ] **Jira write access** — each attendee can create issues in **their own project** (that's where tickets land); the **Mocking Project** (`MP`) is the shared sandbox backup
- [ ] **Product workspace** — attendee's **own folder** open with Claude (no new repo), **OpenSpec installed** (`npm i -g @fission-ai/openspec`), and [`openspec-process.md`](openspec-process.md) added (copy it from the process page, or Claude adds it)
- [ ] **QA workspace** — clone `qa-shared-tools` (`git clone "https://dev.azure.com/awdenver/Aspenware%20Commerce/_git/qa-shared-tools"`); make a branch. The standard, `QUAL-4510` example, and skills live there. **ADO access may need granting — confirm early.** QA saves on a branch, **never `main`**
- [ ] Each attendee has **one real feature** (Product) or **one story** (QA) + whatever notes/transcript they have
- [ ] [Example tickets](example-tickets.md) open, to work or paste from

## The spine (the whole session in one line)

> **Two rooms, one habit: get everything you know into Claude, let it draft, then review hard before anything ships.**
> **Product** → explore the *whole feature* → split it by behavior → propose → review until true → create Epic + Stories + sub-tasks in their own Jira project.
> **QA** → dump the story + the standard → draft test cases → grill → save.

Everything below is that habit, twice: once on screen in Section 1, once on your own feature in Section 2.

## The pages

1. [Section 1 — Orient](section-1-orient.md) — level-set + the live demo
2. [Section 2 — Breakout](section-2-breakout.md) — **the activity, with every prompt** (Product OpenSpec + QA test cases)
3. [Section 3 — Q&A](section-3-qa.md) — show & ask
4. [Closing](closing.md) — retro + the Return-on-Time kata
5. [Facilitator Guide](facilitator-guide.md) — cues, risks, recovery, two-room coordination
6. [The OpenSpec Process](openspec-process.md) — the reference doc + the decomposition method
7. [Example Tickets](example-tickets.md) — the four real tickets and what each is for

## Dry-run focus

Running this as a dry run? Don't try to time all 75. Do this:

1. Section 1 demo end-to-end **once** — find where the Jira connect or the ticket-creation feels shaky.
2. **One full Product run** on a real feature: **Explore the whole feature → split by behavior → Propose → review → create Epic + Stories + sub-tasks in a Jira project** (or print the tree and create by hand). The ticket creation is the riskiest live moment; rehearse the confirm-before-create.
3. The **capture finale** once (CLAUDE.md + save a skill), so you can demo it confidently.
4. Closing kata, just to time it.

Note every spot where you'd reach for a prompt you didn't have — those go in the [prompt sections](section-2-breakout.md).

## Housekeeping (read at the top)

- **Speak up the moment a question lands.** Mid-build questions are the useful ones.
- **Nothing gets created in Jira without you confirming it.** Claude shows the whole ticket tree as a plan; you say go.
- **Every Story must deliver business value.** Split by behavior, never by technical layer.
- **Messy input is the point.** Half-formed notes feed the agent better than a polished paragraph.
