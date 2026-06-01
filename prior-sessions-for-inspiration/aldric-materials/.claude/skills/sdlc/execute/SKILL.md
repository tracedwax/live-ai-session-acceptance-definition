---
name: sdlc:execute
description: From the active iteration's plan and qa, build an ordered TDD execution plan with file/line-precise test and code specifications, then dispatch a subagent to implement it. Reads plan.md, qa.md, TECH_VISION.md, and the codebase. Writes execute.md.
---

# /sdlc:execute

Turn the iteration's plan + qa into a concrete TDD execution plan, then hand it off to a subagent.

## How to run

### Step 1 — Locate the active iteration and read context

Find the most recent `.sdlc/iterations/NNNN-<slug>/` without `review.md`. Read:
- `plan.md` (the scope)
- `qa.md` (the verifications — your test list comes from here)
- `design.md` if present (UX constraints that affect assertions)
- `.sdlc/TECH_VISION.md` (stack, principles, testing conventions)

If any of `plan.md`, `qa.md`, or the iteration directory itself is missing, tell the user and stop.

### Step 2 — Survey the codebase

Read the project's `CLAUDE.md` if present. Identify:
- Where tests live, and their conventions (file naming, runner, fixtures)
- Where the code that needs changing lives
- Any existing tests adjacent to the change area (to match style)

Use focused tools (`Grep`, `Read`) rather than dumping the whole repo. If the codebase is unfamiliar enough that this survey would take more than a few queries, dispatch the **Explore** subagent to do it.

### Step 3 — Build the ordered test list

From `qa.md`, produce a single ordered list. Order by:
1. **Unit tests** (smallest, fastest, fewest dependencies)
2. **Integration tests** (real boundaries: DB, file system, service-to-service)
3. **Acceptance tests** (end-to-end / user-flow)

Each entry is a row with: level, target feature, what it asserts, the test file path, and (where it sharpens the intent) the rough position in the file (`new file` / `append to <existing>` / `after line N`).

### Step 4 — Specify the test code

For each test, write the test body **as code** — not pseudo-code. Match the project's testing idioms (Jest, pytest, RSpec, Go's `testing`, whatever the codebase uses). Include:
- Imports / setup
- Arrange / Act / Assert structure
- Expected values written literally

If a piece genuinely depends on a choice the implementing agent will make, mark it `// FILL: <what to decide>` rather than guessing.

### Step 5 — Specify the implementation changes

For each test (in TDD order), specify the code change that should make it pass:
- File path
- Insertion point (`new file`, `after line N`, `inside function X`, `replace function Y`)
- The code itself, as code

Again, no pseudo-code unless a real ambiguity demands it — and if there is one, surface it to the user **before** dispatching the subagent.

### Step 6 — Write execute.md

Write `iterations/NNNN-<slug>/execute.md`:

```markdown
# Execute — Iteration NNNN

**Built:** YYYY-MM-DD
**Status:** ready to dispatch | in progress | complete

## Codebase notes

<short: where tests live, conventions in use, anything the subagent needs to match>

## TDD order

### 1. [unit] <what it asserts> — <feature>

**Test file:** `path/to/test_file.ext` (new file | append)

```<lang>
<actual test code>
```

**Implementation:** `path/to/source_file.ext` (insertion point)

```<lang>
<actual implementation code>
```

### 2. [unit] ...

...

### N. [acceptance] ...

...

## Dispatch log

<filled in by the subagent below>
```

### Step 7 — Sanity-check with the user

Before dispatching, show the user the test list (just the row summary — not the full code) and confirm. If they want changes, iterate. Don't dispatch a plan the user hasn't OK'd.

### Step 8 — Dispatch the subagent

Use the `Agent` tool with `subagent_type: general-purpose` (or a project-specific implementation agent if the consumer repo defines one). The prompt should:

- Pass the absolute path to `execute.md`
- Instruct: "Implement this in TDD order. For each step: write the test, run it, watch it fail, write the code, run it, watch it pass, commit. After each step, append a `### Step N completed` entry to the `## Dispatch log` section of `execute.md` with: what file changed, test result summary, commit hash. If a step diverges from the plan, append a `### Step N diverged` entry explaining why, then continue."
- Specify the working directory
- Specify any pre-flight commands (install, build) if `TECH_VISION.md` mentions them

Run the subagent in the **foreground** so the dispatching session waits for completion. (Background is OK only if the user explicitly asks for it.)

### Step 9 — Report

When the subagent returns, summarize what was completed, surface any divergences, and suggest `/sdlc:review` next.

## Notes

- The TDD discipline (red → green → commit per step) is the load-bearing convention. Don't soften it.
- File/line precision in the plan is the point. Vague execution plans produce vague code.
- If a test or implementation is genuinely too uncertain to specify, raise it to the user **before** dispatching — the planning step is where ambiguity goes to die.
- The subagent is a worker, not a planner. Don't ask it to "figure out the approach"; ask it to execute the approach you've specified.
