# Prerequisites

Two things make this session work. The first is required. The second is what turns "I watched a demo" into "I worked my own feature."

## Required: Claude Code working in VS Code

You need Claude Code running in the VS Code sidebar and able to answer you.

1. Install **VS Code**, add the **Claude Code extension**, and **sign in**. (The drop-in coaching this week walks through this if you're not there yet.)
2. Open the Claude panel and ask:

   > *"Tell me a joke."*

If you get a joke back, you're ready. That's the whole bar.

## Required for the real win: bring one feature

- **Product:** bring **one real feature** — something big enough to break into a few pieces. Not a single tidy ticket; a chunk of work you'd need to split into stories ("guest checkout," "bulk export," "the new onboarding"). Vague and rough is good — that's the point.
- **QA:** bring **one story** with acceptance criteria you'd need to turn into test cases.

Bring whatever you have *about* it, too: the requirements you were handed, a Slack thread, your own notes, even a **recording or transcript** of a conversation about it. **Got a Figma frame or a Claude prototype?** A screenshot is enough — drag it into the chat. Messy is fine. We feed all of it to Claude.

## Connect Jira (we'll confirm in the room)

You'll **create real tickets in your own Jira project** live — so your Jira connection (the "MCP") needs to be on. Nothing gets created until you read the whole ticket tree and say go, and a wrong ticket is one click to delete. *(If you'd rather not touch your real backlog, a sandbox/Playground project works as a backup.)*

- If a drop-in already connected your Jira, you're set.
- If not, **come to a drop-in before June 2** or flag it in the channel. A facilitator can also drive the demo on their own Jira so you still see the whole loop.

> **Jira is configured once, globally.** You don't reconfigure it per project — just ask Claude to set the Atlassian (Jira) MCP up globally and follow its instructions.

> **Writing to Jira is always confirm-first:** Claude shows you the whole ticket tree **as a plan**, then you say go. Nothing gets created until you approve it.

## Get your workspace

**Product — open Claude in your own folder.** Use the repo you already work in — **you're not creating a new one.** It's just a home for the work and an autosave trail. You write **no application code** — only the proposal, the specs, and the tickets.

- Add two things to that folder: **OpenSpec** (`npm i -g @fission-ai/openspec`, or ask Claude to install it) and the **process doc**, [`openspec-process.md`](openspec-process.md). The process doc is a page on this site — copy it into your folder, or just ask Claude to add it. Don't fuss over this beforehand; Claude does it in [Step 0](section-2-breakout.md) of the breakout.

> **About git:** the session uses tiny git commits as **autosave** — Claude makes them automatically after each step. *You don't need to know any git.* It's just an undo trail.

**QA — work in your team's shared repo, `qa-shared-tools`** (Azure DevOps). Everything you need lives there: the Test Case Standard, the real `QUAL-4510` example, and the skills.

```
git clone "https://dev.azure.com/awdenver/Aspenware%20Commerce/_git/qa-shared-tools"
```

Open it in VS Code and **make a branch for the session** (`git checkout -b qa-training/<your-name>`) so nothing touches `main`.

> **Access:** you may need your team to add your Aspenware account to this repo — flag it early if you can't clone. **No access by session time?** Paste the story + the standard into Claude and work in a local folder; share once access lands.

## If your requirements live in SharePoint

Some of you keep requirements in **SharePoint**. If that connection is set up by June 2 we'll use it; if not, just **paste the text in**. Don't block on it.

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Claude panel not showing in VS Code | Reinstall the extension; bring it to a drop-in if it persists |
| Not signed in / auth loop | Flag in the channel — the coordinator handles licensing |
| Jira not connected | Come to a drop-in; worst case, follow on a facilitator's Jira |
| OpenSpec not installed (Product) | Ask Claude to install it (`npm i -g @fission-ai/openspec`), or come to a drop-in |
| Not sure which folder to use (Product) | Use whatever folder you already work in — no need to make a new one |
| Can't clone `qa-shared-tools` (QA) | Your team needs to add your Aspenware account — flag early; until then, paste the story + standard and work locally |
| No feature to bring | Tell your facilitator — we have [example tickets](example-tickets.md) you can break up instead |

> **Stuck?** Post in the channel before the session. We'd rather fix setup now than spend live minutes on it.
