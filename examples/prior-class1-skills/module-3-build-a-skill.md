# Module 3: Build a Skill for Your OpenSpec Work

> **Time:** ~22 minutes, in breakout rooms. This is the build. Everything before now was setup.

In Module 1 you taught the agent one preference with a CLAUDE.md. Now you do it at scale: a packaged, reusable skill that does a real piece of your OpenSpec workflow the way your team's best person would.

## Step 1: Join your room

Four rooms. Each one is role-shaped, the table shows where your role most naturally lands. Switching is allowed; tell your facilitator if you want to.

| Room | Skill to build | Best fit for | Facilitator |
|------|----------------|--------------|-------------|
| 1 | **Manual QA script** generator from an OpenSpec change | Mostly QA | |
| 2 | **AQA test** generator from an OpenSpec change | Devs interested in test automation | |
| 3 | **Estimation helper**: size a new OpenSpec change by comparing it to past changes (and what they actually took), then fold in developer input | PMs, with a few devs in the room | |
| 4 | **OpenSpec work chunker**: take a too-big OpenSpec change and split it into smaller changes (or its tasks into commits a human can actually review) | Devs, especially anyone who reviews PRs | |

> **Pre-assignments:** your facilitator will tell you which room you're in. Switching is allowed.

> **Product folks:** Room 3 (Estimate) is yours. You bring the PM lens on what "good" looks like; the devs in the room bring the implementation reality. You don't need to write code; you drive **Step 3, Decide what the skill must do** (the "what does good look like *here*" conversation). That's the part the agent can't do without you.

<details>
<summary>Stretch: Confluence / Jira poster</summary>

If your room finishes early, build a skill that posts the generated artifact to Confluence or Jira. We're keeping the Jira MCP itself for a coaching session, so scope this one to "format and draft the post," not "wire up the integration."

</details>

## Step 2: Pick the OpenSpec feature you'll run it against

You need one feature for the skill to chew on. In order of preference:

1. An OpenSpec change in your own repo, done or in progress.
2. A change in `local-orchestrator`:
   ```bash
   git clone <local-orchestrator repo URL> && cd local-orchestrator
   ```
   (Your facilitator has the URL. Skip if you already cloned it from the prereqs.)
3. Ask the agent to define a small arbitrary feature as an OpenSpec change, right now.

Any of these works. You just need one concrete thing the skill can read.

<details>
<summary>Never run OpenSpec? 30-second path</summary>

Ask the agent:

> *"Set up OpenSpec here and create a small example change called `add-sample-feature` with a proposal, one spec, and tasks. Then show me the files."*

That gives you a real OpenSpec change to point the skill at without learning OpenSpec first. You'll learn the workflow properly in Class 1a.

</details>

## Step 3: Decide what the skill must do, before you write it

As a room, answer out loud first:

- What does a good version of this artifact look like *here*, at your company? Not in general.
- What does the skill need as input? The spec deltas? The tasks? Existing code? A past example?
- What should it refuse to do or ask about instead of guessing?

Then make the agent interview you instead of guessing. Easiest way: use the `grill-me` skill you installed in Module 2.

<details>
<summary>With grill-me installed (recommended)</summary>

Just tell the agent:

> *"Grill me on the skill we're about to build: [name and one-line description]. Walk down the decision tree one question at a time."*

`grill-me` is built for exactly this, relentless one-at-a-time questions until the design is real instead of vibes.

</details>

<details>
<summary>Without grill-me, meta-prompt fallback</summary>

> *"We're building a skill that [generates X from an OpenSpec change]. Before you write anything, ask me one question at a time about how our team does this today, what inputs you'll have, and what 'good' looks like. Stop asking when you have enough to write a precise SKILL.md."*

The interview is what cuts slop. A skill that never asks produces generic output.

</details>

## Step 4: Write the skill

Description first, and make it specific. Two paths, pick one per room:

- **Fast:** have the agent scaffold it from your Step 3 answers, then you tighten the description and the "how" section.
- **Precise:** write the `SKILL.md` by hand for full control of the questioning logic.

```markdown
---
name: <kebab-case-name>
description: <one line: what it produces, from what input, and when to use it>
---

# <Skill title>

## When to use this
...

## How to do it
...
```

Then run it against your Step 2 feature and read the output as the person who'd actually receive it. Would QA follow that script? Would a dev trust that estimate?

## Step 5: Review it with Tessl

```bash
npx -y @tessl/cli skill review ./path-to-your-skill
```

Local, no login. Read its flags and fix the description and structure issues it finds. To hold the skill to a bar, give it a passing score to clear:

```bash
npx -y @tessl/cli skill review ./path-to-your-skill --threshold 80
```

That fails the review if the skill scores under 80, which is the "review against parameters" check: a number you have to beat, not just advice you can ignore.

<details>
<summary>If Tessl isn't available (fallback)</summary>

> *"List what makes a good [manual QA script / AQA test / estimate / chunking] skill. Score ours against that list point by point. Name the single weakest part and fix only that."*

</details>

Iterate once on the weakest point. One tight loop beats five vague ones.

## Step 6: *(optional)* Save it where the team can use it

If the room finishes with time to spare, commit the skill to the shared location your facilitator names and add one line to the room's notes: what it does, and the one thing you'd improve next. If you don't get to this in the core, do it in office hours or this week.

## Done when

- The skill runs against a real OpenSpec feature and produces something the receiving role would accept
- Tessl (or the agent) reviewed it and you fixed the weakest point

Bring the result and one honest opinion to Module 4.
