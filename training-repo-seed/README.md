# AC Training Repo

This is the workspace for the **Writing Acceptance Criteria with Claude** session. Download the zip, unzip it, open the folder in VS Code, and start Claude here. You can write to everything in here (unlike the read-only product repos).

## What's in here

| Path | What it's for |
|------|---------------|
| `openspec-process.md` | **The process Claude follows** to turn a feature into specs and Jira tickets. Tell Claude to read it; don't edit it. |
| `examples/` | Four real Jira tickets as markdown. Paste from these as "good examples." See which is which below. |
| `scratch/` | Where your drafts go. Save your AC / test cases here as `[TICKET].md`. |
| `.claude/skills/grill-me/` | The `grill-me` skill, already installed for you. Just say *"grill me on this."* |
| `.claude/skills/write-acceptance-criteria/` | A **starter** skill (Product). Read it, then make it yours in the capture finale. |
| `.claude/skills/write-test-cases/` | A **starter** skill (QA) that writes to our Test Case Standard. |
| `standards/` | Our **Test Case Standard**: the bar every QA test case must meet. |
| `CLAUDE.md` | Empty on purpose. You'll add your one preference here. |

## The examples

- **`examples/PUR-6243.md`**: ✅ copy this shape (clean Given/When/Then + test mapping)
- **`examples/PPA-4978.md`**: ✅ good QA example (AC + test scenarios)
- **`examples/QUAL-4510.md`**: ✅ a real test case in our exact format (QA: copy this)
- **`examples/CHK-3334.md`**: ✏️ a Product story to sharpen
- **`examples/PUR-6336.md`**: ✏️ "is this even AC?" practice

## The loop

> Dump everything + a good example → ask for a first pass → read it cold → `grill me` → review the draft → push to your ticket → capture the way you like it.

Full prompts are in the session's **Section 2** page.
