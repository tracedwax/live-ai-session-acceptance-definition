---
name: write-test-cases
description: Draft QA test cases for a story from its acceptance criteria, following the team Test Case Standard, interviewing the user before writing. Use when writing or sharpening test cases for a Jira story.
---

# Write Test Cases

> **This is a starter.** It works as-is, but the point of the session is to make it *yours* — edit it to match how you decided you like test cases written.

## When to use this
The user wants test cases for a story — from its acceptance criteria, testing notes, or a bug's repro steps.

## How to do it

1. **Read the standard first.** Read `standards/test-case-standard.md`. That is the bar — every test case must meet it before it leaves In Progress.
2. **Take in the story.** Read the ticket, its acceptance criteria, and any testing notes. If a good example is named (e.g. `examples/QUAL-4510.md`), match its format.
3. **Find the gaps.** List what needs verifying: happy path, edge cases, and what could break elsewhere (regression). Ask the user about gaps **one question at a time**, with a recommended answer.
4. **Draft to the standard.** For each test case produce:
   - **Summary**: `{Main Feature} | {what is being tested}`
   - **Description**: *"Validates that [behavior] so that [reason / ticket]."*
   - **Preconditions**: state needed before the test; a quick config change goes in the first step.
   - **Steps** as **Action / Data / Expected Result**. First step sets context (precondition, login state, specific user). Multiple actions → a bulleted list. Use "click" + exact button labels. Include end URLs for specific product pages.
   - **Expected results** in definitive language — **never "should" or "could."** Exact prices where they matter.
   - A **negative path inline** where it makes sense (test the failure before the happy path).
   - **Postconditions** as the last step.
   - Map each test case to the **AC** it covers.
5. **Save the draft** to `scratch/[TICKET]-test-cases.md` so the user can read it before anything is pushed.
6. **Confirm before pushing.** If asked to post to Jira, show the exact text first and wait for explicit approval.

## Rules
- Anyone in the company must be able to run it without asking the author a question.
- No "should"/"could" in expected results — definitive only.
- Flag any required reporting field you can't fill (Priority, Test Kind, Components, Product(s), Tax Setting…) so the user sets it.
- If the user keeps correcting you the same way, that's a preference — offer to add it to `CLAUDE.md`.
