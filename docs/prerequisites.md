# Prerequisites

Two things make this hour work. The first is required. The second is what turns "I watched a demo" into "I worked my own ticket."

## Required: Claude Code working in VS Code

You need Claude Code running in the VS Code sidebar and able to answer you.

1. Install **VS Code**, add the **Claude Code extension**, and **sign in**. (The drop-in coaching this week walks through this if you're not there yet.)
2. Open the Claude panel and ask:

   > *"Tell me a joke."*

If you get a joke back, you're ready. That's the whole bar.

## Required for the real win: bring one ticket

Bring **one real ticket you actually need to work.** Not a perfect one — a rough one. The rougher the better; that's the point.

- **Product:** a story you need to think through and spec — vague, missing details, "I'll know it when I see it."
- **QA:** a story with acceptance criteria you'd need to turn into test cases.

Bring whatever you have *about* it, too: the requirements you were handed, a Slack thread, your own notes, even a **recording or transcript** of a conversation about it. **Got a Figma frame or a Claude prototype?** A screenshot is enough — drag it into the chat. Messy is fine. We feed all of it to Claude.

## Connect Jira (we'll confirm in the room)

You'll work against your **own real Jira ticket** and push to it live — so your Jira connection (the "MCP") needs to be on.

- If a drop-in already connected your Jira, you're set.
- If not, **come to a drop-in before June 2** or flag it in the channel. A facilitator can also drive the demo on their own Jira so you still see the whole loop.

> **Jira is configured once, globally.** You don't reconfigure it per project — just ask Claude to set the Atlassian (Jira) MCP up globally and follow its instructions.

> **Pushing to Jira is always confirm-first:** you review what Claude wrote **as a local draft**, then say go. Nothing reaches your ticket without you approving it.

## Get your workspace

**Product — you don't need a code repo.** In the room, Claude sets one up for you: it creates a fresh folder and initializes **OpenSpec**, so you have somewhere to write your change. (It generates **no application code** — just the proposal and spec.)

- Want a head start? Install OpenSpec before June 2: `npm i -g @fission-ai/openspec` — or just ask Claude to install it in the room. The drop-ins can help.
- Optional starting point: the open **[training repo](https://github.com/tracedwax/ac-training-repo)** ([zip](https://github.com/tracedwax/ac-training-repo/archive/refs/heads/main.zip) · `git clone https://github.com/tracedwax/ac-training-repo.git`) — it ships with the [example tickets](example-tickets.md), the `grill-me` skill, and a `scratch/` folder. Open it, then have Claude set OpenSpec up inside it.

**QA — work in your real shared repo, `qa-shared-tools`:**

```
git clone "https://dev.azure.com/awdenver/Aspenware%20Commerce/_git/qa-shared-tools"
```

Open it in VS Code and **make a branch for the session** (`git checkout -b qa-training/<your-name>`) so nothing touches `main`. If the repo doesn't already have the `grill-me` and `write-test-cases` skills under `.claude/skills/`, copy them from the training repo above (and keep that repo handy for the Test Case Standard and the `QUAL-4510` example).

## If your requirements live in SharePoint

Some of you keep requirements in **SharePoint**. If that connection is set up by June 2 we'll use it; if not, just **paste the text in**. Don't block on it.

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Claude panel not showing in VS Code | Reinstall the extension; bring it to a drop-in if it persists |
| Not signed in / auth loop | Flag in the channel — the coordinator handles licensing |
| Jira not connected | Come to a drop-in; worst case, follow on a facilitator's Jira |
| OpenSpec not installed (Product) | Ask Claude to install it (`npm i -g @fission-ai/openspec`), or come to a drop-in |
| No ticket to bring | Tell your facilitator — we have [example tickets](example-tickets.md) you can work instead |

> **Stuck?** Post in the channel before the session. We'd rather fix setup now than spend live minutes on it.
