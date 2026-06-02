# Prerequisites

One thing is required. Everything else makes the session better but will not block you.

## Required: Claude Code installed and talking

You need Claude Code working and able to hold one turn of conversation.

1. Install it: [code.claude.com/docs/quickstart](https://code.claude.com/docs/en/quickstart#step-1-install-claude-code). If you already have the Claude desktop app, Claude Code came with it.
2. Open it and ask:

> *"Tell me a joke."*

If you get a joke back, you are ready. That is the whole bar.

## Recommended pre-work

Two free tracks. Claude Code 101 takes up to 3 hours. OpenSpec takes up to 2. Skip sections you already know cold.

### Track 1: Claude Code 101 (up to 3 hrs)

Anthropic's free course. Covers install through hooks: explore → plan → code → commit, context management, CLAUDE.md, subagents, MCP.

→ [anthropic.skilljar.com/claude-code-101](https://anthropic.skilljar.com/claude-code-101)

### Track 2: OpenSpec (up to 2 hrs)

- **Spec Before You Ship**: free 8-lesson tutorial on writing specs before handing work to AI: [spec-before-you-ship.vercel.app](https://spec-before-you-ship.vercel.app/)
- **Video explainer**: down-to-earth walkthrough of the OpenSpec workflow: [youtube](https://www.youtube.com/watch?v=B7VPMKW5tnk)
- Skim the basics:
  - [Workflow diagram](https://github.com/Fission-AI/OpenSpec/discussions/294#discussion-9121778)
  - [DeepWiki overview](https://deepwiki.com/Fission-AI/OpenSpec/1-overview)

### How much should I do?

- **Devs / QA:** do both tracks. Skip what you already know cold.
- **Product / PMs:** do both. Skip anything particularly devvy you don't need (you don't have to be fluent in hooks or MCP to follow the class).

The class moves fast. Doing this prep is the difference between "I followed along" and "I built something useful."

## Optional but recommended

These let you work on something real in Module 3 instead of a toy. Skip any you can't get to.

### An OpenSpec feature to work against

Have one OpenSpec change in mind, complete or in progress. Your own repo is best. If you don't have one, the `local-orchestrator` repo works as a default, or you can have the agent define a small arbitrary feature on the spot. You only need to pick one; creating one is optional.

### A sample or two of your past work

Bring something that shows how you work, so a skill can learn your style: a user story, a code file, an architecture decision record, a manual-QA script, an AQA script. Any one is enough.

### Tessl (optional, no account needed)

We use Tessl to review skills. It runs locally and needs no login. Installing ahead of time is encouraged but optional; we have a fallback if you don't have it.

Ask your agent:

> *"Run `npx -y @tessl/cli --help` and tell me if it works."*

If it prints help, you're set. If not, no problem, bring it up in office hours.

## Verify

Ask your agent one check:

> *"Confirm Claude Code is working by telling me a joke, then tell me whether `npx -y @tessl/cli --help` runs."*

The joke is the only must-pass. The rest is bonus.

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Claude Code not found in terminal | Reinstall from the [quickstart](https://code.claude.com/docs/en/quickstart#step-1-install-claude-code); the desktop app bundles it |
| Windows blocks the install | Note it and flag it in the channel; your training coordinator handles licensing and permissions |
| `npx -y @tessl/cli` errors | Optional tool. Skip it; we use the agent-eval fallback in Module 2 and 3 |
| No OpenSpec feature ready | Use `local-orchestrator`, or have the agent define a small feature live |
| Not sure your setup is right | Paste the error into Claude Code and ask it to walk you through the fix |

> **Stuck?** Post in the channel before the session. We'd rather fix it now than spend live minutes on setup.
