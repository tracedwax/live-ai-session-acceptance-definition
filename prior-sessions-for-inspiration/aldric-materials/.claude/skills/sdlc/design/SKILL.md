---
name: sdlc:design
description: Attach UX/visual-design information to a piece of work — either an inbox item (creates designs/<slug>.md) or an active iteration's scope item (writes into the iteration's design.md). Adds a [design: <ref>] marker on the linked item so the link is visible at a glance. UX/UI/flow only — not technical architecture.
---

# /sdlc:design

Capture UX/UI/flow information for a work item and link it to that item. This is **visual and experiential design**, not technical architecture.

## How to run

### Step 1 — Ask what to design for

If `$ARGUMENTS` references something specific (a slug, an inbox phrase, "iteration 0001's dark mode"), use it as the target. Otherwise show the user a numbered list of candidates and ask which:

- Items currently in `.sdlc/INBOX.md`
- Scope items in the currently-open iteration's `plan.md` (the most recent `iterations/NNNN-<slug>/` without a `review.md`)

If neither has items, tell the user and stop.

### Step 2 — Gather the design info

Ask the user for the design material. Be flexible — they may provide:
- A written flow (numbered steps the user walks through)
- A description of screens / states
- Visual notes (colors, layout, placement)
- Links to external mockups (Figma, image files, sketches)
- A combination

One question at a time. Don't overwhelm. Start with: "Walk me through what the user does, step by step."

Then follow with shorter focused questions as needed (e.g., "What's on the screen when they land?" → "Where does the toggle live?" → "What happens on error?").

### Step 3 — Decide the destination

**If the target is an inbox item:**
- Generate a kebab-case slug (≤4 words) from the item text. Confirm with the user.
- Write to `.sdlc/designs/<slug>.md`.
- Append `[design: <slug>]` to the inbox item line in `INBOX.md`.

**If the target is a scope item in an open iteration:**
- Open or create `iterations/NNNN-<iter-slug>/design.md`.
- Append a section under a `## <item title>` heading.
- Mark the scope item line in `plan.md` with `[design ✓]` at the end.

### Step 4 — Write the design file

Use this structure (omit empty sections):

```markdown
# Design — <item title>

**Captured:** YYYY-MM-DD
**For:** <inbox item text> | <iteration NNNN-<slug>, scope item N>

## User flow

1. ...
2. ...

## Screens / states

- **<state name>** — what's visible, what's interactive

## Visual notes

<colors, typography, placement, motion>

## External references

- <link or path>

## Open UX questions

- <anything unresolved>
```

### Step 5 — Confirm

Reply with the destination path and the marker added to the linked item. One short sentence.

## Notes

- This is **not** technical design. If the user starts describing data models, APIs, or implementation details, gently redirect: "Sounds like that belongs in the plan or in tech notes — `/sdlc:design` is for what the user sees and does."
- Multiple designs can attach to one iteration; each gets its own `## <item title>` section in `design.md`.
- It's fine for a design to be a few bullets. Don't pad.
