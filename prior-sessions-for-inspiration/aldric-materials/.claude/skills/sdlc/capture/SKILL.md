---
name: sdlc:capture
description: Append an idea, bug, or thought to .sdlc/INBOX.md as a one-liner. Use when the user wants to quickly record something without breaking flow. No dialogue, no follow-up questions.
---

# /sdlc:capture

Append one item to `.sdlc/INBOX.md`. Fast. No questions.

## How to run

1. Take the user's `$ARGUMENTS` as the item text. If the user invoked the skill with no arguments, ask: "What do you want to capture?" — one line, accept the next user message verbatim.
2. If `.sdlc/INBOX.md` does not exist, scaffold it:
   ```
   # Inbox

   ## Items

   ```
3. Append a single bullet under `## Items` in this exact format:
   ```
   - YYYY-MM-DD — <item text>
   ```
   Use today's date. Do **not** quote the item, edit its wording, or add commentary.
4. Reply with one line: `Captured: <item text>`. Nothing else.

## Notes

- This skill should never open a discussion. If the user wants to think out loud, that's a different skill.
- Multiple captures in a row are fine — each one independent.
- The inbox is intentionally a flat bullet list. Structure happens later (in `/sdlc:plan` or by hand-editing `ROADMAP.md`).
