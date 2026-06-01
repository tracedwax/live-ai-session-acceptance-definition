---
name: sdlc:plan
description: Compose an iteration plan from inbox items, roadmap, and product vision. Use when the user is ready to define scope for a unit of work. Creates iterations/NNNN-<slug>/plan.md. Detects open iterations and warns before starting a new one.
---

# /sdlc:plan

Help the user compose the next iteration. Output is `iterations/NNNN-<slug>/plan.md`.

## How to run

### Step 1 — Check for an open iteration

Run:
```bash
ls -1 .sdlc/iterations/ 2>/dev/null | sort | tail -1
```

If a directory exists and contains no `review.md`, that iteration is **open**. Surface this to the user and offer three choices:
1. Close the open iteration first (suggest running `/sdlc:review`)
2. Force-start a new one anyway (the open one will sit unclosed)
3. Cancel

Wait for the user's choice before proceeding.

### Step 2 — Establish seed material

- If the user passed `$ARGUMENTS`, treat that as the iteration's intent/theme.
- Otherwise, ask the user one short question: "What's the focus of this iteration?"
- Read `.sdlc/PRODUCT_VISION.md` and surface relevant constraints if the iteration touches the product surface.
- Read `.sdlc/ROADMAP.md` and identify "Next" items that match the focus.
- Read `.sdlc/INBOX.md` and identify items that match the focus (including any with `[design: <slug>]` markers).

### Step 3 — Propose the slate

Show the user the candidate items as a numbered list, grouped by source (roadmap / inbox). Include any `[design: <slug>]` markers verbatim. Ask which to include — invite them to add new items not on either list.

### Step 4 — Name the iteration

Once the slate is locked, propose 2–3 short slugs (kebab-case, ≤4 words) that capture the iteration's character. Let the user pick or override.

### Step 5 — Compute the iteration number

```bash
ls -1 .sdlc/iterations/ 2>/dev/null | grep -E '^[0-9]{4}-' | sort | tail -1
```
The next number is that one + 1, zero-padded to 4 digits. If none exist, start at `0001`.

### Step 6 — Create the iteration directory and plan

Create `.sdlc/iterations/NNNN-<slug>/` and write `plan.md` with this structure:

```markdown
# Iteration NNNN — <human title>

**Started:** YYYY-MM-DD
**Focus:** <one-sentence intent>

## Scope

- [ ] <feature/work item 1> [optional design marker]
- [ ] <feature/work item 2>
- ...

## Out of scope

- <explicitly excluded thing, with brief reason>

## Notes

<any context worth carrying — links to inbox source, related roadmap items, constraints from product vision>
```

### Step 7 — Pull in any referenced designs

For each `[design: <slug>]` marker on a scope item:
- If `.sdlc/designs/<slug>.md` exists, copy its contents into `iterations/NNNN-<slug>/design.md` under a heading for that work item. Prepend a one-line provenance note at the top of `design.md`: `_Copied from designs/<slug>.md on YYYY-MM-DD. Edits here are local to this iteration._`
- The original in `designs/` stays.

### Step 8 — Drain promoted items from the inbox

For each inbox item that landed in the plan, **remove** it from `INBOX.md`. Items left behind stay for future iterations.

### Step 9 — Confirm

Reply with a short summary: iteration number, slug, count of scope items, path to `plan.md`. Suggest the next step is `/sdlc:design` (if any UX work isn't already designed), `/sdlc:qa`, or both.

## Notes

- Don't gate the user. If they want to skip steps, let them.
- Keep the plan terse. The plan is a list of intentions; details belong in design/qa/execute.
- If `PRODUCT_VISION.md` is empty or missing, just note that and move on — don't block.
