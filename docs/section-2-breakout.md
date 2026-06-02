# Section 2 — Breakout: do it on your own ticket

> **Time: ~30 min. Two rooms.** This is the build. You saw the loop in the orient; now you do the real thing on a ticket you actually own.

Two rooms, two different jobs:

- **Product** turns a rough ticket into an **OpenSpec change** — a proposal and a spec a developer could build from.
- **QA** turns a story's acceptance criteria into **test cases**.

Pick your room. Copy the prompts. Change the bracketed bits.

---

## 🟦 Product room — turn a ticket into an OpenSpec change

**You leave with:** an **OpenSpec change** for your ticket — a **proposal** (what & why) and a **spec** (the behavior a developer could build and QA could verify) — reviewed by you and uploaded to your Jira ticket.

The crux of the Product track is the three OpenSpec phases you own: **Explore → Proposal → Spec.** The **Design** and the code are the developer's — they'll redo these phases in the real repo, which is quick once your thinking is captured.

> **What's OpenSpec?** A simple way to write down *what* you want **before** any code gets written, so the agent — and your developer — build the right thing. The phases live at **[openspec.dev](https://openspec.dev/)**. Today you do the first three.

### Step 1 — Let Claude build you a workspace
You don't need a code repo. Ask Claude to make one:

> *"Create a fresh folder for this work and set up OpenSpec in it. We're going to write a change proposal — no application code. If OpenSpec isn't installed, install it first."*

Claude scaffolds it (the `openspec/` structure and the `/opsx:` commands). Already have the **training repo** open? Just set OpenSpec up right there.

> If install stalls, flag it in the channel — a facilitator gets you unblocked. Don't lose live minutes to setup.

### Step 2 — Phase 1: Explore (think it through)
This is thinking time, not writing time. Dump everything and let Claude be a thinking partner:

> *"Let's use OpenSpec — explore this with me before we write anything. Here's my ticket and everything I have about it: [paste the ticket, your notes, the refinement call, a Slack thread]. What's ambiguous? What would a developer still have to guess? Ask me one thing at a time."*

Shortcut: type **`/opsx:explore`**. Answer its questions. Let it sketch the change, surface edge cases, and challenge your assumptions. **Don't rush to the proposal** — the clarity you get here is the point.

> Got a Figma frame or a Claude prototype? **Screenshot it and drag it into the chat.** That's enough for now.

### Step 3 — Phases 2 & 3: Propose (the proposal + the spec)
When it feels solid, turn the thinking into a change:

> *"Now create an OpenSpec change for this — a clear **proposal** (what & why) and a **spec** of the behavior."*

Shortcut: type **`/opsx:propose`**. Claude generates the artifacts under `openspec/changes/<your-change>/`:

- **`proposal.md`** — *what* you're changing and *why* — **Phase 2**
- **`specs/.../spec.md`** — the **required behavior**, written as testable scenarios — **Phase 3**
- It also scaffolds a `design.md` and `tasks.md`. **Leave those alone** — that's the developer's starting point, not yours.

### Step 4 — Review the spec until it makes sense
This is the part that matters. Open the **proposal** and the **spec** and read them *cold* — as the developer who has to build it and the QA who has to verify it. **Where would they still have to guess?**

> *"`grill me` on this spec — one question at a time. Push on the scenarios I'm missing and anything a developer would still have to guess."*

Sharpen it until it reads true. The goal, in plain terms: **do the phases, review them so they make sense, and land it in a document you can edit and reason about.**

### Step 5 — Hand it off to the ticket
Put the artifacts where the team already looks:

> *"Post my proposal and spec onto Jira ticket [KEY] — as a comment or in the description. Show me the text first."* — read it, then say **"go."**

No Jira write yet? **Upload the artifacts to the ticket by hand for now** — that's fine until the repo workflow matures. From here the developer picks it up and redoes Explore → Proposal → Spec → **Design** in the real code repo — fast, because you already did the thinking.

### Step 6 — *(Stretch)* go deeper
Finished early? Explore a **second** ticket, or push this spec further: ask for the negative paths, the rollback behavior, and the non-obvious edge cases, and fold them into the spec.

---

## 🟩 QA room — full test cases from a story's AC

**You leave with:** test-case drafts that follow our **Test Case Standard** — Action / Data / Expected Result, definitive language, mapped to the AC — covering happy path, edges, and regression, saved into `qa-shared-tools` on your branch.

### Step 1 — Open your workspace
Clone QA's shared repo and open it in VS Code:
```
git clone "https://dev.azure.com/awdenver/Aspenware%20Commerce/_git/qa-shared-tools"
```
Make a branch so nothing touches `main`: `git checkout -b qa-training/<your-name>`. Start Claude here.

> Make sure the `grill-me` and `write-test-cases` skills are available — if they're not already under this repo's `.claude/skills/`, copy them in from the [training repo](https://github.com/tracedwax/ac-training-repo), and keep that repo open for the Test Case Standard and the `QUAL-4510` example.

### Step 2 — Pull the story and its AC
> *"Pull ticket [KEY] from Jira. Read its acceptance criteria and testing notes. Don't write anything yet — list what you'd need to verify it."*

(No Jira yet? Paste the ticket text instead.)

### Step 3 — Point Claude at our real format
> *"Follow our Test Case Standard — use the copy in this `qa-shared-tools` repo if it's here, otherwise `standards/test-case-standard.md` from the training repo. Match the format of a real test case like `QUAL-4510`, and see how AC maps to tests in `PUR-6243`."*

The standard is the bar: Summary as `{Feature} | {what's tested}`, a *"Validates that… so that…"* description, **Action / Data / Expected Result** steps, definitive language (never "should"/"could"), preconditions in the first step, a negative path inline, postconditions last.

> **Note:** `QUAL-4510` is a real, complete example — copy it. Other QUAL IDs in the tickets (QUAL-5013, QUAL-2591…) are placeholders we don't have bodies for.

### Step 4 — One-shot it, then read it cold
> *"Draft test cases for this story to our standard: happy path, edge cases, and a regression check. For each: Action / Data / Expected Result, definitive language, mapped to the AC it covers. Put the negative path before the happy path where it makes sense."*

Read it as the QA who has to run it — **and against the standard.** What's untestable? What precondition or data is missing? Which AC has no test? Does any expected result say "should"?

### Step 5 — Grill yourself
> *"`grill me` on the test coverage for this story. One question at a time — push on edge cases and regressions I haven't thought of."*

Write the result to `scratch/[TICKET]-test-cases.md`.

### Step 6 — Save it (then optionally share)
Save your test cases into `qa-shared-tools` on **your branch** and commit:
> *"Save these as `[TICKET]-test-cases.md` in a working folder and commit them to my branch. Show me the diff first."* — review, then **"go."**

Push the **branch** if you want to share it (open a PR later) — **never push to `main`** of the shared repo. **Stretch:** also add them to the Jira ticket: *"Post these as a comment on [KEY] — show me the text first."*

---

## ⭐ The capture finale (both rooms — stretch)

This is the part that pays off next week. After your **spec** (Product) or **test cases** (QA) are good:

**1. Find your preference**
> *"Looking back at everything I corrected you on while we built this — what are the one or two rules I clearly care about? State them as short preferences."*

**2. Write it into CLAUDE.md**
> *"Add those to a `CLAUDE.md` in this folder. Just those lines, no preamble."*

Now Claude loads that preference automatically next time.

**3. Save it as your own skill**
> *"Turn the way we just did this into a reusable skill — Product: `.claude/skills/write-openspec-change/SKILL.md`; QA: `.claude/skills/write-test-cases/SKILL.md`. A one-line description and the steps we followed. Ask me one question at a time if you need to."*

Next ticket, you just say *"write the OpenSpec change for this"* (or *"write test cases for this"*) and it works **your way**.

## Done when

- Your ticket is real work now: Product has a **reviewed OpenSpec change** (proposal + spec) uploaded to the ticket; QA has **test cases** to our standard, saved and reviewed.
- *(Stretch)* one preference is in a `CLAUDE.md`, and/or you saved a skill.

Bring one result and one honest opinion to [Section 3](section-3-qa.md).
