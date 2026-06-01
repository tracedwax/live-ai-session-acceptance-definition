# Module 2 — Skills: Find, Vet, Demo

> **Time:** ~13 minutes.

A skill is just a prompt with a folder around it. This module shows what's in that folder, where to get skills other people wrote, how to not get burned by them, and a live build you'll watch before you do your own.

## Quick poll

In chat: have you used a skill before? Which one, and did it actually save you time? Two people share aloud.

## What a skill is

A skill is a directory the agent loads when its description matches what you're doing. The minimum is one file, `SKILL.md`: YAML frontmatter between `---` fences, then a markdown body. Here's a real, public one from [durimkryeziu/claude-skills](https://github.com/durimkryeziu/claude-skills/blob/main/skills/commit-message/SKILL.md), shown short:

```markdown
---
name: commit-message
description: Craft Git commit messages following Chris Beams' seven rules — imperative subject, 50-char limit, body explains why not how. Includes JIRA ID detection from branch names.
---

# Craft Git Commit Messages (Chris Beams style)

Source: *How to Write a Git Commit Message* by Chris Beams (https://cbea.ms/git-commit/).

## The 7 rules (non-negotiable)

1. Separate subject from body with a blank line
2. Limit the subject line to 50 characters (72 hard cap)
3. Capitalize the subject line
4. Do not end the subject line with a period
5. Use the imperative mood in the subject line
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how

### Imperative test

> "If applied, this commit will … <subject>"
```

That heritage is worth noticing: Chris Beams codified the commit-message guidance in the [subsurface README](https://github.com/torvalds/subsurface/blob/a48494d2fbed58c751e9b7e8fbff88582f9b2d02/README#L88-L115) — widely attributed to Linus Torvalds, who founded the project — about why focused, atomic commits matter. The actual SKILL.md on GitHub is longer (it adds JIRA detection, validation, and a step-by-step workflow Claude follows), but everything important about *what a skill is* fits in the lines above.

Optional folders sit next to `SKILL.md`: `scripts/` for code the skill runs, `references/` for docs it can pull in, `assets/` for templates, `evals/` for tests. The description is the most important line. It's how the agent decides to use the skill at all. Make it specific and a little pushy.

> **One-line rule:** the `description` must be a single line. A line break breaks the parser.

### The three tiers

Think of tiers as **who reuses the skill**, not how fancy it is.

| Tier | Reused by | Example |
|------|-----------|---------|
| 1 — Org | Everyone in the company | Your company brand voice; the way official partner-facing language has to read |
| 2 — Team | Just your team (e.g. QA, Product, or a specific team) | The AQA-test generator we're building in Module 3 |
| 3 — Personal | Just you | Your commit-message formatter; your standup-update phrasing |

Most of what you build today is Tier 2: encode how your best QA, dev, or PM already works so everyone gets it.

## Where skills come from

- [Anthropic's skills repo](https://github.com/anthropics/skills) — first-party examples (slack-gif-creator, brand-guidelines, skill-creator, etc.)
- [Tessl registry](https://tessl.io/registry)
- GitHub search for `SKILL.md`
- [agentskills.io](https://agentskills.io) for reference and patterns

Quality varies wildly. Treat a downloaded skill like a downloaded shell script, because that's what it can contain.

### Hands-on: install one now (2 min)

Pick any skill from the sources above and install it. Easiest path: ask your agent.

> *"Find the SKILL.md for `grill-me` in this workshop's repo at `BarefootCoders/live-coding-session-skills-for-openspec`, path `skills/grill-me/SKILL.md`. Read it to me first so I can vet it, then install it into `.claude/skills/grill-me/SKILL.md` in my current project."*

`grill-me` is a real, short skill that interviews you relentlessly about a plan, one question at a time, before you commit to it. We use it later in Module 3 to cut slop on your skill build. **Vet it first** by having the agent read it aloud (that's the rule from the previous section). Then install.

Want a different one? Same pattern: pick a skill, have the agent read it to you, install only if you can explain what it does. Anything from `anthropics/skills` is a safe bet.

## Vetting: review before you trust

A skill can carry executable code in `scripts/`. Before you enable one you didn't write, have the agent read it to you:

> *"Read every file in this skill, including everything under scripts/. Summarize exactly what it does, what it executes, and anything that touches the network, the filesystem outside the repo, or credentials. Flag anything you wouldn't run."*

If the agent can't cleanly explain what a script does, don't enable it. That review is the floor, not the ceiling.

## Live demo

Watch one of your facilitators build a skill the way they actually do it, narrating as they go. Watch for: how they write the description, how much they tell it to ask before acting, and whether they review it before trusting it. Ask them that last one directly.

<details>
<summary>What the demo covers</summary>

- Start from intent: what should this skill do, and what should it refuse to do
- Write the `SKILL.md` (description first)
- Have the agent interview the demo presenter before it writes, to cut slop
- Review the result, then check it with Tessl (next section)

</details>

## Check it with Tessl

Tessl reviews a skill locally. No login, nothing leaves your machine.

```bash
npx -y @tessl/cli skill review ./path-to-skill-folder
```

It flags description quality, structure, and common failure modes. Add `--threshold 80` to make it a pass/fail bar instead of just notes. Use it as a fast second opinion, not a guarantee.

<details>
<summary>If Tessl isn't installed (fallback)</summary>

Have the agent grade it instead:

> *"You are reviewing this skill. First list what makes a good skill of this type. Then score this skill against that list, point by point, and name the weakest part."*

This is the same eval loop you'll use in Module 3.

</details>

## Done when

- You can say in one sentence what a skill is and where its risk lives
- You watched a skill get built and Tessl-checked (or agent-checked)
- You know which tier you're about to build in Module 3
