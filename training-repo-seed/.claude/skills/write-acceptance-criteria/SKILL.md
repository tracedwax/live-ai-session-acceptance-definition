---
name: write-acceptance-criteria
description: Draft testable acceptance criteria for a user story from rough notes and a good example, interviewing the user before writing. Use when writing or sharpening acceptance criteria for a Jira story.
---

# Write Acceptance Criteria

> **This is a starter.** It works as-is, but the point of the session is to make it *yours* — edit the steps and rules below to match how you decided you like acceptance criteria written.

## When to use this
The user wants acceptance criteria for a story — writing from scratch or sharpening vague ones.

## How to do it

1. **Take in everything first.** Read the ticket, the user's notes, and any transcript they paste. Do **not** write criteria yet.
2. **Find the good example.** If the user names one (e.g. `examples/PUR-6243.md`), match its shape.
3. **Name the gaps.** List what a developer would still have to guess and which edge cases aren't covered. Ask the user about each, **one question at a time**, with a recommended answer.
4. **Draft.** Write the acceptance criteria as **Given / When / Then**, one scenario per criterion, each independently testable. Name edge cases and the regression check as their own criteria.
5. **Save the draft** to `scratch/[TICKET].md` so the user can read it before anything is pushed.
6. **Confirm before pushing.** If asked to update Jira, show the exact change first and wait for explicit approval.

## Rules
- Every criterion must be testable by someone who can't ask the author a question.
- No UI wording or implementation detail in the criteria — outcomes only.
- If the user keeps correcting you the same way, that's a preference — offer to add it to `CLAUDE.md`.
