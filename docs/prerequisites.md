# Prerequisites

Two things make this hour work. The first is required. The second is what turns "I watched a demo" into "I sharpened my own ticket."

## Required: Claude Code working in VS Code

You need Claude Code running in the VS Code sidebar and able to answer you.

1. Install **VS Code**, add the **Claude Code extension**, and **sign in**. (The drop-in coaching this week walks through this if you're not there yet.)
2. Open the Claude panel and ask:

   > *"Tell me a joke."*

If you get a joke back, you're ready. That's the whole bar.

## Required for the real win: bring one ticket

Bring **one real ticket you actually need to write or sharpen.** Not a perfect one — a rough one. The rougher the better; that's the point.

- **Product:** a story whose acceptance criteria are vague, missing, or "I'll know it when I see it."
- **QA:** a story with acceptance criteria you'd need to turn into test cases.

Bring whatever you have *about* it, too: the requirements you were handed, a Slack thread, your own notes, even a **recording or transcript** of a conversation about it. Messy is fine. We feed all of it to Claude.

## Connect Jira (we'll confirm in the room)

You'll work against your **own real Jira ticket** and push to it live — so your Jira connection (the "MCP") needs to be on.

- If a drop-in already connected your Jira, you're set.
- If not, **come to a drop-in before June 2** or flag it in the channel. A facilitator can also drive the demo on their own Jira so you still see the whole loop.

> **Pushing to Jira is always confirm-first:** you review what Claude wrote **as a local draft**, then say go. Nothing reaches your ticket without you approving it.

## Get the training repo

The hands-on workspace is an open repo: **[github.com/tracedwax/ac-training-repo](https://github.com/tracedwax/ac-training-repo)**. Pick one:

- **Download the zip:** [ac-training-repo.zip](https://github.com/tracedwax/ac-training-repo/archive/refs/heads/main.zip) → unzip → **open the folder in VS Code** → start Claude there.
- **Clone it:** `git clone https://github.com/tracedwax/ac-training-repo.git`

It already includes the [example tickets](example-tickets.md), our **Test Case Standard** plus a real example (`QUAL-4510`), the `grill-me` skill, starter skills, an empty `CLAUDE.md`, and a `scratch/` folder for your drafts. It's yours to write to — unlike the read-only product repos.

## If your requirements live in SharePoint

Some of you keep requirements in **SharePoint**. If that connection is set up by June 2 we'll use it; if not, just **paste the text in**. Don't block on it.

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Claude panel not showing in VS Code | Reinstall the extension; bring it to a drop-in if it persists |
| Not signed in / auth loop | Flag in the channel — the coordinator handles licensing |
| Jira not connected | Come to a drop-in; worst case, follow on a facilitator's Jira |
| No ticket to bring | Tell your facilitator — we have [example tickets](example-tickets.md) you can work instead |

> **Stuck?** Post in the channel before the session. We'd rather fix setup now than spend live minutes on it.
