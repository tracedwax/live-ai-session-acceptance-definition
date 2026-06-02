# Section 2: Breakout: do it on your own feature

> **Time: ~35 min. Two rooms.** This is the build. You saw the loop in the orient; now you do the real thing on a feature you actually own.

Two rooms, two different jobs:

- **Product** takes a whole **feature** and, with OpenSpec, breaks it into **value-bearing Jira tickets**: an Epic, a Story per behavior, and sub-tasks, each backed by a proposal and a spec a developer could build from.
- **QA** turns a story's acceptance criteria into **test cases**.

Pick your room. **Each step tells you what to accomplish and why, not what to type.** Talking to the agent in your own words *is* the skill we're here to build, so try that first. Stuck for words? Every step has a **click-to-open example prompt** you can borrow. The examples are a safety net, not the path.

> **Review before anything ships, and ask Claude and the room as you go.** **Product: don't one-shot it.** Make one artifact (the proposal, then each spec), read it, grill it, then the next; if the agent races ahead, tell it to slow down. **QA: a one-shot draft is fine**, then critique it hard and improve. Either way, judge each piece; don't collect a doc you never looked at.

> **Everyone hands on keys, please. :)** This part isn't TV. Do it on your own ticket as we go and keep your screen shared, we're all working at once, not watching one person.

---

## Product room: break a feature into value-bearing Jira tickets

**You leave with:** your feature broken into **real Jira tickets in your own project**: one **Epic** (the feature), a **Story per behavior** (each with its own business-value "Why"), and **sub-tasks** under each, every Story backed by a proposal and a spec a developer could build from and QA could verify.

The move you're learning is **divide and conquer**: explore the *whole* feature, find the natural seams *between behaviors*, and let each behavior become one well-sized, independently shippable ticket. The full method is in **[The OpenSpec Process](openspec-process.md)**: keep it open.

> **What's OpenSpec?** A simple way to write down *what* you want **before** any code gets written, so the agent, and your developer, build the right thing. You own the first phases (**Explore → Proposal → Spec**); the Design and the code are the developer's.

> **The one rule for tickets:** every Story must deliver **business value** a user can observe. Split by *behavior* (`guest-checkout`, `order-confirmation-email`), **never** by technical layer ("frontend ticket", "backend ticket"). A layer has no standalone value.

> **Each step below follows Erin's doc**, [The OpenSpec Process](openspec-process.md): Step 1 [Exploration](openspec-process.md?id=1-exploration-pm-owns), Step 2 [How to break it up](openspec-process.md?id=how-to-break-a-project-into-openspec-units), Step 3 [Proposal](openspec-process.md?id=2-proposal-pm-owns), Step 4 [Writing WHEN/THEN specs](openspec-process.md?id=writing-whenthen-specs), Step 5 [Jira + OpenSpec](openspec-process.md?id=how-jira-and-openspec-connect-step-by-step).

### Step 0: Open your own folder and get set up
Open Claude in **the folder you already work in**. You're not creating a new repo, you just need a home for the work and an autosave trail. You write **no application code** here, only the proposal, the specs, and the tickets.

Get two things in place, and you can simply ask Claude to do both: **pull the process doc into your folder** (it's the [OpenSpec Process](openspec-process.md) page on this site) so the agent follows our method, and **turn on autosave** so it makes a tiny git commit after each step. Autosave means you never touch git; it's just an undo trail.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

Give Claude the process to follow:
> *"Add the OpenSpec process guide to this folder as `openspec-process.md`, then read it. If OpenSpec isn't installed, install it and initialize it here."*

Turn on autosave (say it once):
> *"After every step we finish, make a small git commit with a one-line message. Do it automatically, I don't need to review these."*
</details>

> If install stalls, flag it in the channel, a facilitator gets you unblocked. Don't lose live minutes to setup.

### Step 1: Explore the *whole* feature (don't spec yet)
This is thinking time, not writing time. Get **everything** you know in front of the agent, the ticket, your notes, the refinement call, a Slack thread, even a screenshot of a Figma frame, and ask it to map the landscape: every distinct behavior the feature touches, and what's still ambiguous. **Don't rush to a spec.** The full picture is the goal.

Then let **`grill me`** find the holes. You don't need to know the right questions, that's its job. Every question it asks is a decision that belongs in the ticket; every answer is something a developer would otherwise have guessed. **This is how the ticket gets complete before any code is written.** Answer what you can; flag what needs a stakeholder.

> Typing **`/opsx:explore`** kicks off the same thing. Got a Figma frame or a prototype? Screenshot it and drag it into the chat.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

> *"Let's use OpenSpec. Explore this whole feature with me before we write or split anything. Here's everything I have: [paste your feature, notes, refinement call, Slack thread]. What are all the distinct behaviors this touches? What's ambiguous? Ask me one thing at a time."*

then run the `grill-me` skill on the feature and answer its questions.
</details>

### Step 2: Find the seams (divide it up)
Get the agent to **split the feature into independently shippable behaviors**: one bucket per behavior, each named like a behavior (not a component or a layer), each with a one-line "Why" (its business value). Then check the sizing out loud against the [sizing reference](openspec-process.md#sizing-reference): one sentence each, 2-4 behaviors, testable on its own.

**Bad split:** "frontend" / "backend." **Good split:** the guest-checkout example, *guest cart → confirmation email → post-purchase account prompt.* If a bucket needs "and also" to describe, it's two buckets.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

> *"Split this feature into independently shippable behaviors, one bucket per behavior, named like a behavior (not a component or a layer). For each, give a one-line 'Why' (the business value) and which user it serves. Then sanity-check the sizing with me against the process doc."*
</details>

### Step 3: Write the proposal, then stop and review it
Don't generate everything at once. Have the agent draft **just the proposal**, the *what* and *why* (`proposal.md`, which becomes your **Epic**), and nothing else yet. Then **read it cold** as the developer who has to build it: is the scope right? is the "Why" true? anything missing, or sneaked in that you didn't intend? Grill it, and **ask the room**, your facilitator and the people next to you are part of this review. Don't move on until the proposal is right; a wrong proposal makes wrong specs.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

> *"Draft just the OpenSpec proposal for this feature, the what and why, as `proposal.md`. Don't write specs, design, or tasks yet, I want to review the proposal first."*

then run the `grill-me` skill on the proposal and answer its questions.
</details>

### Step 4: Write the specs one behavior at a time
Now go behavior by behavior. For **each** one, have the agent write **that single spec** (`specs/<behavior>/spec.md`) as testable WHEN/THEN scenarios, then **review it before you touch the next**: where would a developer still guess? what are the unhappy paths? If a spec runs past **6-8 scenarios**, it's doing too much, split it (that's one more Story). One artifact, one review, then the next. Use the `grill-me` skill and the people in the room here.

> Leave `design.md` to the developer. When the specs are solid, you can ask Claude to break them into a short **tasks** list, those become your sub-tasks in Step 5.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

> *"Write the spec for just the `[behavior]` capability as testable WHEN/THEN scenarios. Stop after this one so I can review it before the next."*

then run the `grill-me` skill on the spec and answer its questions.
</details>

### Step 5: Create the Jira tickets, in reviewable chunks
Build the tree in **your own Jira project**, and here too go in pieces you can check: create the **Epic** from the proposal, then **one Story per spec** (its "Why" is the description), then a few **sub-tasks** per Story from the tasks list. **Make the agent show the plan first**, then read it: does every Story name a behavior and a value? Any "layer" Stories hiding? Only then say go, and spot-check in Jira after.

> **The review *is* the safety:** you see the tree before anything is created, and a wrong ticket is one click to delete.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

> *"In my Jira project [your project key], first create just the Epic from the proposal (title + the 'Why' as the description) and show it to me. Then propose one Story per spec, each Story's description is that behavior's 'Why' plus a summary of its spec, and the tasks as sub-tasks. Show me the full tree as a plan before creating anything else."*
</details>

<details>
<summary>Rather not touch your real backlog?</summary>

Two safe options: ask Claude to **print the full tree as markdown** so you can eyeball it before anything is created, or create it in the **[Mocking Project (`MP`)](https://aspenware.atlassian.net/jira/software/projects/MP/boards)**, a shared sandbox where throwaway tickets do no harm.
</details>

### Step 6: *(Stretch)* go deeper
Finished early? Push the specs further, negative paths, rollback behavior, the non-obvious edge cases, and fold them in. Or note the **dependency order** between your Stories (which must ship before which) in each Story's description, so sprint planning is already done.

---

## QA room: test cases to the team standard, in your shared repo

**You leave with:** test cases that follow your team's **Test Case Standard**: Action / Data / Expected Result, definitive language, mapped to the AC, saved into **`qa-shared-tools`** on your branch. And a shared **`write-test-cases` skill** committed back, so your whole team drafts to the same bar next time.

Your team already writes test cases with Claude. So the win here isn't "can it draft one", it's **standardizing the bar and cleaning up what already exists.**

> **What good looks like:** four real test cases to reference for shape, [QUAL-4510](https://aspenware.atlassian.net/browse/QUAL-4510), [QUAL-4207](https://aspenware.atlassian.net/browse/QUAL-4207), [QUAL-1380](https://aspenware.atlassian.net/browse/QUAL-1380), [QUAL-4961](https://aspenware.atlassian.net/browse/QUAL-4961).

### Step 1: Open your clone of the shared repo
You already have **`qa-shared-tools`** (Azure DevOps) cloned, that's where you'll save your work. Open it in VS Code, make a branch so nothing touches `main` (or just ask Claude to make the branch), and start Claude there. Your bar is the team's **[Test Case Standard](https://aspenware.atlassian.net/wiki/spaces/QA/pages/4137582614/Test+Case+Standard)** in Confluence.

<details>
<summary>Need to clone it fresh? Click here</summary>

```
git clone "git@ssh.dev.azure.com:v3/awdenver/Aspenware Commerce/qa-shared-tools"
```
SSH (HTTPS is painful). New to SSH on Azure DevOps? Ask Claude to walk you through adding a key.
</details>

> **The `QUAL-4510` example and a starter `write-test-cases` skill** aren't assumed to be in your repo; your facilitator provides them from the session materials. The standard itself is the Confluence page linked above.

<details>
<summary><strong>For facilitators only</strong>: example repo as a stand-in</summary>

Attendees play in their own shared repo (`qa-shared-tools`) and follow the [Test Case Standard](https://aspenware.atlassian.net/wiki/spaces/QA/pages/4137582614/Test+Case+Standard) in Confluence.

The **example repo** mirrors the real one (standard, `QUAL-4510`, starter `write-test-cases` skill). Until we have access to `qa-shared-tools`, **clone the example repo and work in it as if it were the real repo**, once access lands, we'll drop a copy into the real one:

```
git clone git@github.com:tracedwax/ac-training-repo.git
```

Pull the `QUAL-4510` example or the starter skill from here into an attendee's branch if their repo doesn't have them. Don't send attendees to this repo, it's a facilitator stand-in.
</details>

### Step 2: Pull your own ticket
You brought a ticket and you have the Jira MCP, so pull it straight in. Have the agent read the acceptance criteria and testing notes; **don't let it write test cases yet.**

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

> *"Pull my ticket from Jira. Read its acceptance criteria and testing notes. Don't write anything yet."*

(No Jira MCP yet? Paste the ticket text instead.)
</details>

### Step 3: Grill yourself on what it takes to test this
Before a single test case gets written, use **`grill me`** to draw out what you actually need: the data and accounts, the preconditions and environment, the edge cases, and what "done and correct" even means for this story. You don't have to know all of it up front, that's the whole point of grilling, it pulls the gaps out of you and the ticket.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

Run the `grill-me` skill to surface what it takes to test this story, and answer its questions before writing anything.
</details>

### Step 4: Draft to the team's bar
Now have the agent write to **your team's standard**, not a generic one. Point it at the [Test Case Standard](https://aspenware.atlassian.net/wiki/spaces/QA/pages/4137582614/Test+Case+Standard) (it includes a worked example), and have it map each AC to a test. The bar: Summary as `{Feature} | {what's tested}`, a *"Validates that… so that…"* description, **Action / Data / Expected Result** steps, definitive language (never "should"/"could"), preconditions first, a negative path inline, postconditions last. If cases already exist, **level them up** instead: normalize to the standard, fill empty reporting fields, flag duplicates.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

Draft new coverage:
> *"Draft test cases for this story to our Test Case Standard (https://aspenware.atlassian.net/wiki/spaces/QA/pages/4137582614/Test+Case+Standard): happy path, edge cases, a regression check. Action / Data / Expected Result, definitive language, mapped to the AC each covers."*

Level up existing cases, if there are any:
> *"Here are the existing test cases for this area. Normalize them to our standard: fill empty reporting fields, flag duplicates, and call out any AC with no test. Show me a table of what you'd change before changing anything."*
</details>

### Step 5: Critique it, then improve it
Don't trust the first draft. Turn the agent on its own work: **what might be wrong here?** What's untestable, what data is missing, which AC has no coverage, where does an expected result hedge with "should"? Then have it fix what the critique surfaces. `grill me` is great for this second pass too.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

> *"Critique these test cases against our standard, what's untestable, missing, or duplicated."* Then run the `grill-me` skill on the gaps and improve them.
</details>

### Step 6: Save it to your branch
Save the test cases to your branch and commit, reviewing the diff before it lands. Push the branch to share (open a PR later); **never push to `main`.** Optionally drop them on the Jira ticket too.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

> *"Save these as `[TICKET]-test-cases.md` in our working folder and commit them to my branch. Show me the diff first."* then review and say go.

Optional: *"Post these as a comment on my ticket, show me the text first."*
</details>

---

## The capture finale (both rooms: stretch)

This is the part that pays off next week. After your **tickets** (Product) or **test cases** (QA) are good, capture the way *you* like to work so next time is faster:

1. **Find your preference.** Ask the agent what one or two rules you kept correcting it on.
2. **Write it into a `CLAUDE.md`** in your folder, so Claude loads it automatically next time.
3. **Save it as a skill**, so a single phrase reruns the whole move your way.

<details>
<summary>Here's an example you can use, only if you're stuck</summary>

> *"Looking back at everything I corrected you on while we built this, what are the one or two rules I clearly care about? State them as short preferences."*

> *"Add those to a `CLAUDE.md` in this folder. Just those lines, no preamble."*

> *"Turn the way we just did this into a reusable skill, Product: `.claude/skills/break-feature-into-tickets/SKILL.md`; QA: `.claude/skills/write-test-cases/SKILL.md`. A one-line description and the steps we followed. Ask me one question at a time if you need to."*
</details>

> **QA: commit the skill back.** Put your `write-test-cases` skill into **`qa-shared-tools`** (on your branch, then PR it) so the whole team drafts to the same standard with one command.

## Done when

- Your feature is real work now: Product has a **value-bearing ticket tree in their own Jira project** (an Epic, a Story per behavior, sub-tasks), each Story backed by a reviewed proposal + spec. QA has **test cases** to the team standard, saved on a branch, and ideally a **shared `write-test-cases` skill** committed back to `qa-shared-tools`.
- *(Stretch)* one preference is in a `CLAUDE.md`.

Bring one result and one honest opinion to [Section 3](section-3-qa.md).
