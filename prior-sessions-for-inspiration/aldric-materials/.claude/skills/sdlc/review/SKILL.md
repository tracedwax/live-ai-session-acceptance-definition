---
name: sdlc:review
description: Interactive feature-by-feature human walkthrough of the active iteration's work. Asks narrow questions per feature, routes problems to the inbox, updates EXISTING_FEATURES with accepted work, and closes the iteration by writing review.md. Use at iteration's end to capture human feedback.
---

# /sdlc:review

Walk a human reviewer through the iteration's shipped work, one feature at a time. The reviewer's expertise is "does this feel right when I actually use it." Your job is to ask narrow, focused questions and capture answers honestly.

## How to run

### Step 1 — Locate the active iteration

Find the most recent `.sdlc/iterations/NNNN-<slug>/` without `review.md`. If none exists, tell the user there's nothing open to review.

Read:
- `plan.md` (the scope)
- `design.md` if present (what the UX was supposed to feel like)
- `qa.md` (what we said "works" means)
- `execute.md` (what was actually built, including the dispatch log)

### Step 2 — Frame the walkthrough

Tell the user: "We're going to walk through `<N>` features, one at a time. For each, I'll ask a few narrow questions — please answer for **that feature only**. We'll do a summary at the end."

Confirm they're ready.

### Step 3 — For each scope item

Walk through scope items in `plan.md` order. **One feature at a time.** Don't move on until the user has answered.

For each feature, ask these questions in sequence — **one per message**:

1. **Does it work?** "Try `<one specific action>`. Did it do what you expected?"
   - If yes → continue.
   - If no → ask: "What happened instead?" Capture verbatim.
2. **Does it feel right?** "Anything about the experience that's off — wording, placement, timing, visual?"
   - Capture any answer that isn't "no" or "fine."
3. **Did it break anything?** "Try `<one related existing feature>`. Still working?"
   - Capture failures verbatim.
4. **Anything else about this one?** Open-ended. Short.

**Critical:** never bundle these into a single question. Humans give shallow answers to compound questions.

If the user wants to skip a question (e.g., "no UI to look at" for question 2), accept and move on.

### Step 4 — Categorize each feature

After each feature's Q&A, classify it with the user:

- **Accepted** — works, feels right, no problems
- **Accepted with notes** — works, but has minor issues worth recording
- **Rejected** — doesn't work, broken UX, or breaks something else; needs more work

Don't infer — ask: "So we call this one accepted / accepted-with-notes / rejected?"

### Step 5 — Route problems to the inbox

For every problem captured (failures, UX complaints, regressions), append a line to `.sdlc/INBOX.md` under `## Items`:

```
- YYYY-MM-DD — [from iteration NNNN review] <verbatim problem>
```

Do this as you go, not at the end. Tell the user when you've added something.

### Step 6 — Write review.md

Once every feature has been reviewed, write `iterations/NNNN-<slug>/review.md`:

```markdown
# Review — Iteration NNNN

**Reviewed:** YYYY-MM-DD
**Reviewer:** <name or "user">

## Outcomes

### Accepted

- **<feature 1>** — <notes if any>
- ...

### Accepted with notes

- **<feature 2>** — <notes>
  - Captured to inbox: <problem 1>
  - ...

### Rejected

- **<feature 3>** — <reason>
  - Captured to inbox: <problem>

## Summary

- Features delivered: N
- Accepted: N
- Accepted with notes: N
- Rejected: N
- Items routed to inbox: N

## Reviewer's overall take

<one short paragraph from the user, captured verbatim if they offer one>
```

Ask the user for the overall take (one prompt: "Anything you want to say about the iteration as a whole?"). Capture verbatim.

### Step 7 — Update EXISTING_FEATURES.md

For every **accepted** and **accepted with notes** feature, append an entry to `.sdlc/EXISTING_FEATURES.md` under `## Shipped`:

```
- **<feature name>** — <one-line description> (iteration NNNN)
```

Do not add rejected features.

### Step 8 — Confirm closure

Reply with the summary numbers and a one-line confirmation that the iteration is closed (because `review.md` now exists). Suggest next steps based on what's in the inbox.

## Notes

- **Patience over speed.** This skill exists because compound questions destroy feedback quality. Ask narrowly. Wait for the answer.
- **Capture verbatim.** Don't paraphrase the user's words into the inbox or review.md. Their phrasing is signal.
- **Don't argue.** If the user rejects a feature you think works, that's data. Capture it and move on.
- **Stop if the user is fatigued.** Long reviews get sloppy. If you've gone through 5–6 features and the user is sighing, offer to pause and resume.
