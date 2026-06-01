# Section 2 — Breakout: do it on your own ticket

> **Time: ~30 min. Two rooms.** This is the build. You watched the loop; now you run it on a ticket you actually own.

Same loop in both rooms. Product writes the **story + acceptance criteria**. QA writes the **test cases**. Pick your room; copy the prompts; change the bracketed bits.

## The loop (both rooms)

1. **Dump everything** you have into Claude — the ticket, the requirements, your notes, a transcript. Messy is good.
2. **Show a good example** so it copies the shape you want.
3. **Ask for a first pass.** Read it *cold*, as the person who'd receive it.
4. **If it's not good — `grill me`.** Let Claude interview you one question at a time and build it step by step.
5. **Review the local draft, then confirm-to-push** to your ticket. Nothing goes to Jira until you say go.
6. *(Stretch)* **Capture the way you like it** — into a `CLAUDE.md`, then a saved skill.

---

## 🟦 Product room — a story with testable AC

**You leave with:** acceptance criteria a developer could build from and QA could verify, pushed to your ticket.

### Step 1 — Open your workspace
Open the **training repo's `scratch/` folder** in VS Code and start Claude there.

### Step 2 — Dump everything
> *"I need to write/sharpen a user story. Here's the ticket and everything I have about it — the requirements I was given, my own notes, and [paste any transcript or Slack]. Read it all. Don't write anything yet — just tell me what's still ambiguous."*

### Step 3 — Show a good example
Open [example-tickets.md](example-tickets.md) and paste the AC from **PUR-6243**:
> *"Here's a ticket whose acceptance criteria I like — match this shape: Given / When / Then, each one testable, edge cases named separately."*

### Step 4 — One-shot it, then read it cold
> *"Now draft acceptance criteria for my story."*

Read it as the developer who has to build it. **Where would they still have to guess?** What edge case is missing?

### Step 5 — Grill yourself
> *"`grill me` on these acceptance criteria. One question at a time. For each, suggest your recommended answer."*

Answer honestly. Watch it go from generic to *yours*. Tell it to write the result to `scratch/[TICKET].md` so you can see the draft.

### Step 6 — Confirm-to-push
> *"Update the acceptance criteria on ticket [KEY] in Jira. Show me exactly what you'll change first."*

Read the change. If it's right, say **"go."** If not, keep grilling. *You* own the push.

### Step 7 — *(Stretch)* go deeper
No AC to sharpen, or finished early? Build the **rest of the story** — problem statement, scope, out-of-scope — the same way: dump, example, draft, grill.

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

This is the part that pays off next week. After your AC or test cases are good:

**1. Find your preference**
> *"Looking back at everything I corrected you on while we built this — what are the one or two rules I clearly care about? State them as short preferences."*

**2. Write it into CLAUDE.md**
> *"Add those to a `CLAUDE.md` in this folder. Just those lines, no preamble."*

Now Claude loads that preference automatically next time.

**3. Save it as your own skill**
> *"Turn the way we just did this into a reusable skill. Create `.claude/skills/write-acceptance-criteria/SKILL.md` (or `write-test-cases`) — a one-line description and the steps we followed. Ask me one question at a time if you need to."*

Next ticket, you just say *"write acceptance criteria for this"* and it works **your way**.

## Done when

- Your ticket's AC (Product) or test cases (QA) are sharper than they started, and you've **reviewed and pushed/saved** them
- *(Stretch)* one preference is in a `CLAUDE.md`, and/or you saved a skill

Bring one result and one honest opinion to [Section 3](section-3-qa.md).
