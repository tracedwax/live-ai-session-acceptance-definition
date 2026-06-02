# Section 2 — Breakout: do it on your own feature

> **Time: ~35 min. Two rooms.** This is the build. You saw the loop in the orient; now you do the real thing on a feature you actually own.

Two rooms, two different jobs:

- **Product** takes a whole **feature** and, with OpenSpec, breaks it into **value-bearing Jira tickets** — an Epic, a Story per behavior, and sub-tasks — each backed by a proposal and a spec a developer could build from.
- **QA** turns a story's acceptance criteria into **test cases**.

Pick your room. Copy the prompts. Change the bracketed bits.

---

## 🟦 Product room — break a feature into value-bearing Jira tickets

**You leave with:** your feature broken into **real Jira tickets in your own project** — one **Epic** (the feature), a **Story per behavior** (each with its own business-value "Why"), and **sub-tasks** under each — every Story backed by a proposal and a spec a developer could build from and QA could verify.

The move you're learning is **divide and conquer**: explore the *whole* feature, find the natural seams *between behaviors*, and let each behavior become one well-sized, independently shippable ticket. The full method is in **[The OpenSpec Process](openspec-process.md)** — keep it open.

> **What's OpenSpec?** A simple way to write down *what* you want **before** any code gets written, so the agent — and your developer — build the right thing. You own the first phases (**Explore → Proposal → Spec**); the Design and the code are the developer's.

> **The one rule for tickets:** every Story must deliver **business value** a user can observe. Split by *behavior* (`guest-checkout`, `order-confirmation-email`), **never** by technical layer ("frontend ticket", "backend ticket"). A layer has no standalone value — that's the trap we're avoiding.

### Step 0 — Open your own folder, drop in the process, turn on autosave
Open Claude in **the folder you already work in** — you're not creating a new repo, you just need a home for the work and an autosave trail. You write **no application code** — only the proposal, the specs, and the tickets. Two quick setup moves:

**a) Give Claude the process to follow.** Add the process doc to your folder so the agent reads it before writing:

> *"Add the OpenSpec process guide to this folder as `openspec-process.md`, then read it — that's the process we're following today. If OpenSpec isn't installed, install it and initialize it here."*

The process doc is the **[OpenSpec Process](openspec-process.md)** page on this site — Claude can pull it from there, or you paste it in. (Don't have it handy? Just ask Claude to recreate it from that page.)

**b) Turn on autosave (git microcommits).** Say this once and forget it:

> *"After every step we finish, make a small git commit with a one-line message. Do it automatically — I don't need to review or understand these commits."*

That's it. Think of the commits as **autosave** — you never have to touch git. They give you a clean trail of each stage and an undo button if a step goes sideways.

> If install stalls, flag it in the channel — a facilitator gets you unblocked. Don't lose live minutes to setup.

### Step 1 — Explore the *whole* feature (don't spec yet)
This is thinking time, not writing time. Dump everything about the **whole feature** and let Claude map the landscape:

> *"Let's use OpenSpec. Explore this whole feature with me before we write or split anything. Here's everything I have: [paste the feature, your notes, the refinement call, a Slack thread]. What are all the distinct behaviors this touches? What's ambiguous? What would a developer still have to guess? Ask me one thing at a time."*

Shortcut: type **`/opsx:explore`**. Answer its questions. The goal here is the **full picture** — every behavior the feature touches — *not* a spec yet. Don't rush.

Then let **`grill me`** find the holes — you don't need to know the right questions, it finds them for you:

> *"`grill me` on this feature — one question at a time. What's ambiguous, what's unspecced, what would a developer still have to guess?"*

Every question it asks is a decision that belongs in the ticket; every answer you give is something a developer would otherwise have guessed. **This is how the ticket gets complete before any code is written.** Answer the ones you can; flag the ones that need a stakeholder.

> Got a Figma frame or a Claude prototype? **Screenshot it and drag it into the chat.** That's enough.

### Step 2 — Find the seams (divide it up)
Now split the feature into independently shippable behaviors:

> *"Based on that, split this feature into independently shippable behaviors — one bucket per behavior, named like a behavior (not a component or a layer). For each: a one-line 'Why' (the business value) and which user it serves. Then sanity-check the sizing with me against the process doc."*

Use the **[sizing reference](openspec-process.md#sizing-reference)** out loud: each bucket should be describable in one sentence, 2–4 behaviors total, testable on its own. **Bad split:** "frontend" / "backend." **Good split:** the guest-checkout example — *guest cart → confirmation email → post-purchase account prompt.* If a bucket needs "and also" to describe, it's two buckets.

> This is the heart of the hour. Get the seams right and the tickets write themselves.

### Step 3 — Propose (proposal + specs, one per behavior)
When the split feels right, turn it into OpenSpec artifacts:

> *"Create the OpenSpec change for this feature — a clear proposal (what & why) and one capability spec per behavior we identified, written as testable WHEN/THEN scenarios."*

Shortcut: type **`/opsx:propose`**. Claude generates, under `openspec/changes/<your-feature>/`:

- **`proposal.md`** — *what* the feature changes and *why* (this becomes your **Epic**)
- **`specs/<behavior>/spec.md`** — one per behavior, the required behavior as testable scenarios (each becomes a **Story**)
- It also scaffolds `design.md` and `tasks.md`. **Leave the design alone** — that's the developer's. The **tasks** become your **sub-tasks**.

### Step 4 — Review until it reads true
This is the part that matters. Read the proposal and each spec *cold* — as the developer who has to build it and the QA who has to verify it. **Where would they still have to guess?**

> *"`grill me` on this proposal and its specs — one question at a time. Push on the behaviors I'm missing, the unhappy paths, and anything a developer would still have to guess."*

Sharpen until it's true. If one spec has **more than 6–8 scenarios**, it's doing too much — ask Claude to split that behavior into two. (Each split = one more Story.)

### Step 5 — Create the Jira tickets (Epic → Stories → sub-tasks)
Now turn the artifacts into a real ticket tree in **your own Jira project** — the one your feature actually lives in. Confirm before each write:

> *"In Jira project **[YOUR-PROJECT]**, create an **Epic** from the proposal (title + the 'Why' as the description). Then create one **Story per capability spec** — each Story's description is that behavior's 'Why' (its business value) plus a link/summary of its spec. Then add the `tasks.md` items as **sub-tasks** under the right Story. Show me the full tree as a plan first — don't create anything until I say go."*

Read the plan. Check the obvious things: **does every Story name a behavior and a value?** Are there any "layer" Stories hiding (split those)? Then say **"go,"** and let it create them. Spot-check one Story in Jira when it's done.

> **The review *is* the safety** — you read the whole tree before anything is created, and a wrong ticket is one click to delete. **Want a no-risk run first?** Have Claude **print the full tree as markdown** so you can eyeball it, or point it at a **sandbox/Playground project** as a backup if you've got one.

### Step 6 — *(Stretch)* go deeper
Finished early? Push the specs further — negative paths, rollback behavior, the non-obvious edge cases — and fold them in. Or note the **dependency order** between your Stories (which must ship before which) in each Story's description, so sprint planning is already done.

---

## 🟩 QA room — test cases to the team standard, in your shared repo

**You leave with:** test cases that follow your team's **Test Case Standard** — Action / Data / Expected Result, definitive language, mapped to the AC — saved into **`qa-shared-tools`** on your branch. And, the real prize: a sharpened **shared `write-test-cases` skill** committed back, so your whole team drafts to the same bar next time.

Your team already writes test cases with Claude. So the win here isn't "can it draft one" — it's **standardizing the bar and cleaning up what already exists.**

### Step 1 — Open the team's shared repo
Everything you need — the standard, the example, the skills — lives in **`qa-shared-tools`** (Azure DevOps). Clone it and open it in VS Code:
```
git clone "https://dev.azure.com/awdenver/Aspenware%20Commerce/_git/qa-shared-tools"
```
Make a branch so nothing touches `main`: `git checkout -b qa-training/<your-name>`. Start Claude here.

> **Access:** the QA team has shared access to this repo. **No access yet?** Paste the story and the standard into Claude and work in a local folder; share once access lands.

<details>
<summary>🔒 <strong>For facilitators only</strong> — backup reference repo</summary>

Attendees play in their own shared repo (`qa-shared-tools`). If the standard, the `QUAL-4510` example, or the skills aren't reachable, the **old training repo** mirrors that structure and ships all of them as a fallback: [github.com/tracedwax/ac-training-repo](https://github.com/tracedwax/ac-training-repo) ([zip](https://github.com/tracedwax/ac-training-repo/archive/refs/heads/main.zip)). Pull what's needed from there and drop it in — don't send attendees to it.
</details>

### Step 2 — Pull the story and its AC
> *"Pull ticket [KEY] from Jira. Read its acceptance criteria and testing notes. Don't write anything yet — list what you'd need to verify it."*

(No Jira yet? Paste the ticket text instead.)

### Step 3 — Point Claude at the team standard (it's in this repo)
> *"Follow our Test Case Standard in this `qa-shared-tools` repo, and match the format of the real `QUAL-4510` example here. Show me how each AC maps to a test."*

The standard is the bar: Summary as `{Feature} | {what's tested}`, a *"Validates that… so that…"* description, **Action / Data / Expected Result** steps, definitive language (never "should"/"could"), preconditions in the first step, a negative path inline, postconditions last.

### Step 4 — Do the job your story needs
Pick the one that fits — most stories want both:

**a) Draft to the standard** (new coverage):
> *"Draft test cases for this story to our standard: happy path, edge cases, and a regression check. For each: Action / Data / Expected Result, definitive language, mapped to the AC it covers. Put the negative path before the happy path where it makes sense."*

**b) Level up what already exists** (the high-value move):
> *"Here are the existing test cases for this area. Normalize them to our standard: fill any empty reporting fields, flag duplicate or overlapping cases, and call out any AC that has no test covering it. Show me a table of what you'd change before changing anything."*

Read it as the QA who has to run it — **and against the standard.** What's untestable? What precondition or data is missing? Which AC has no test? Does any expected result say "should"?

### Step 5 — Grill yourself
> *"`grill me` on the test coverage for this story. One question at a time — push on edge cases and regressions I haven't thought of."*

### Step 6 — Save it to your branch
> *"Save these as `[TICKET]-test-cases.md` in our working folder and commit them to my branch. Show me the diff first."* — review, then **"go."**

Push the **branch** to share it (open a PR later) — **never push to `main`** of the shared repo. Optional: also add them to the Jira ticket — *"Post these as a comment on [KEY] — show me the text first."*

---

## ⭐ The capture finale (both rooms — stretch)

This is the part that pays off next week. After your **tickets** (Product) or **test cases** (QA) are good:

**1. Find your preference**
> *"Looking back at everything I corrected you on while we built this — what are the one or two rules I clearly care about? State them as short preferences."*

**2. Write it into CLAUDE.md**
> *"Add those to a `CLAUDE.md` in this folder. Just those lines, no preamble."*

Now Claude loads that preference automatically next time.

**3. Save it as a skill**
> *"Turn the way we just did this into a reusable skill — Product: `.claude/skills/break-feature-into-tickets/SKILL.md`; QA: `.claude/skills/write-test-cases/SKILL.md`. A one-line description and the steps we followed. Ask me one question at a time if you need to."*

Next feature, you just say *"break this feature into tickets"* (or *"write test cases for this"*) and it works **your way**.

> **QA — this is your headline, not a stretch.** Commit that `write-test-cases` skill into **`qa-shared-tools`** (on your branch, then PR it). Once it's in, the whole team drafts to the same standard with one command — that's the real win for QA, bigger than any single story's test cases.

## Done when

- Your feature is real work now: Product has a **value-bearing ticket tree in their own Jira project** — an Epic, a Story per behavior, sub-tasks — each Story backed by a reviewed proposal + spec. QA has **test cases** to the team standard, saved on a branch — and ideally a **shared `write-test-cases` skill** committed back to `qa-shared-tools`.
- *(Stretch)* one preference is in a `CLAUDE.md`.

Bring one result and one honest opinion to [Section 3](section-3-qa.md).
