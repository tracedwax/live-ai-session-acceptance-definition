---
name: sdlc:qa
description: For each feature in the current iteration's plan, define how we will verify it works and how we know it plays nice with other features. Prefers automated verification (scripts, tests) over manual checks. Writes qa.md in the active iteration directory.
---

# /sdlc:qa

QA's expertise is two questions:
1. **How do we know this works?** (the happy path verifies)
2. **How do we know it doesn't break anything else?** (the interaction verifies)

Build a verification script — automated where possible, manual where unavoidable — for each feature in the iteration plan.

## How to run

### Step 1 — Locate the active iteration

Find the most recent `.sdlc/iterations/NNNN-<slug>/` directory without a `review.md`. If none exists, tell the user: "No open iteration. Run `/sdlc:plan` first." and stop.

Read its `plan.md`. If `design.md` exists, read it too — design constraints often define acceptance.

### Step 2 — Read the tech vision

Read `.sdlc/TECH_VISION.md`. Pay attention to:
- Any testing principles ("integration-first", "no mocked DB", etc.)
- Stack details that affect what "automated" means here

### Step 3 — For each scope item, define verification

Walk the user through the scope items **one at a time**. For each, ask:

> "For `<scope item>`, how do we know it works?"

Help the user articulate:
- **Happy path** — the canonical user/system flow that proves the feature exists
- **Edge cases** — boundary conditions, empty states, errors
- **Interaction risk** — what existing feature could this break? (Read `EXISTING_FEATURES.md` for the list.)

For each verification, decide together: **automated or manual**? Default to automated. Use manual only when:
- The feature has no programmatic surface (e.g., a visual change that no test could meaningfully assert)
- Automation cost vastly exceeds the value for this iteration

When automated, specify the **level**: unit / integration / acceptance. When manual, specify the **script**: numbered steps + expected outcome.

### Step 4 — Write qa.md

Write `iterations/NNNN-<slug>/qa.md` in this shape:

```markdown
# QA — Iteration NNNN

**Captured:** YYYY-MM-DD

## Verification per feature

### <scope item 1>

**Works when:**
- <happy path assertion>
- <edge: ...>

**Doesn't break:**
- <interaction with existing feature X>

**Verification:**
- [automated, integration] <one-line description of what the test does>
- [automated, unit] <...>
- [manual] Steps:
  1. ...
  2. ...
  Expected: ...

### <scope item 2>

...
```

### Step 5 — Cross-feature regression checks

After per-feature verifications, ask: "Anything we should re-check globally for this iteration?" Common answers: smoke-test the whole app, run the existing test suite, hit the prod-shaped staging environment.

Append a final section:

```markdown
## Cross-cutting checks

- [automated] Full test suite passes
- [manual] Smoke check of <area>
- ...
```

### Step 6 — Confirm

Reply with: count of scope items covered, count of automated vs. manual checks, path to `qa.md`. Suggest `/sdlc:execute` next.

## Notes

- One question per item, one item at a time. Don't batch.
- If the user says "I don't know how to test this" — help. Suggest a test shape. Don't move on without a verification (even if it's manual).
- The qa.md is a contract that `/sdlc:execute` will read to build its TDD plan. Be precise about what the tests assert.
