# Module 1: Prompting, Context & Your First CLAUDE.md

> **Time:** ~12 minutes. Ends with a file you keep.

Most bad agent output is a context problem, not a model problem. This module fixes the two cheapest things: how you ask, and what the agent knows about you.

> **No code repo? You're fine.** Product folks: open any folder the agent can work in. A docs folder, a notes folder, or a fresh empty one all work. If you want something real, clone `local-orchestrator`. CLAUDE.md and prompting are not code-only; the exercises below have a non-code path.

## What you'll walk away with

- A feel for why a vague prompt and a precise one produce very different output
- A working `CLAUDE.md` in a folder you use, with one or two of your real preferences in it

## Step 1: Run a vague prompt, then a precise one

Pick one small task. Ask for it the lazy way first, then ask for the same thing with intent and a done condition. Use whichever pair fits your role:

<details>
<summary>Dev / QA example</summary>

> Lazy: *"add error handling here"*
>
> Precise: *"Add error handling to `parseConfig`. Constraints: throw a typed error, don't swallow exceptions, don't add a new dependency. Done when: invalid input throws `ConfigError` with the bad key named and the existing tests still pass."*

</details>

<details>
<summary>Product example (no code)</summary>

> Lazy: *"write acceptance criteria for this feature"*
>
> Precise: *"Write acceptance criteria for [feature]. Format: Given/When/Then. Constraints: every criterion testable by QA without asking me a question, no UI wording, name the edge cases. Done when: a developer could build it and QA could verify it from this alone."*

</details>

The second one works because it states the **outcome** and the **done condition**, not just the verb. Anthropic's prompting guidance says the same thing: be explicit, give the model the success criteria ([prompting docs](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview)).

> What you just did is prompt craft for one task. The bigger discipline, making the **business's** purpose **machine-readable and machine-actionable** so an autonomous system stays on the rails, is what Nate B. Jones calls **intent engineering**, and it lives with Product and leadership, not in a single prompt. Goals, values, tradeoffs, decision boundaries written down clearly enough that the agent can't accidentally wander into "disastrous." We pick that up in Class 1a. For now, see his [Klarna piece](https://natesnewsletter.substack.com/p/klarna-saved-60-million-and-broke) or the [4-skills framework](https://www.youtube.com/watch?v=BpibZSMGtdY) on YouTube.

## Step 2: Context rot is real

The agent does not get smarter as the conversation gets longer. It gets noisier. Stale instructions, dead ends, and three abandoned attempts all sit in the window competing with what you actually want. This is **context rot**: quality degrades as the context fills with low-signal material.

Practical rules:

- Start a fresh session when you switch tasks. Don't drag a 200-message thread into a new problem.
- Put stable, high-signal information somewhere persistent instead of re-pasting it every time.
- Reference files by path and let the agent read them, rather than pasting huge blobs you'll never reuse.

That "somewhere persistent" is the next step.

## Step 3: Hands-on: write your first CLAUDE.md

`CLAUDE.md` is a file Claude Code reads automatically at the start of every session in that folder. It is the smallest possible way to stop repeating yourself. Whatever you just had to correct the agent on, put it here once.

Create it from a preference that actually came up in the last ten minutes. Keep it to one or two lines. Real, not aspirational.

<details>
<summary>How to create it (let the agent do it)</summary>

> *"Create a CLAUDE.md in this folder with these rules: 1) Use our existing test framework, never add a new one without asking. 2) Keep functions under 40 lines. Keep it short, just those two rules, no preamble."*

Or write it by hand:

```markdown
# CLAUDE.md

- Use the existing test framework. Don't add a new one without asking.
- Prefer small functions. Flag anything over ~40 lines.
```

</details>

> **Why this matters for the rest of the class:** A CLAUDE.md is a preference the agent always loads. A skill, which you build in Module 3, is the same idea scaled up: a packaged, reusable instruction set the agent pulls in when it's relevant. You just built the small version.

## Done when

- You ran the same task vague and precise and saw the difference
- A `CLAUDE.md` exists in your working folder with one or two of your real rules

<details>
<summary>Optional 30-second proof (only if time)</summary>

Start a fresh Claude Code session in that folder and ask it to do something the rule touches. Watch it obey without being told. Skip this if the room is moving; it's a confidence check, not a requirement.

</details>

Keep that file. Module 3 builds on it.
