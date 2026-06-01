# Pre-Work — Non-Technical Track

**Drafted:** 2026-05-21
**Status:** outline only — pending alignment on contents before drafting in full (with screenshots)
**Audience:** Product, design, QA, and any program attendee who lives in GUIs and doesn't open terminals
**Companion to:** `2026-05-20-sdlc-training-design.md`

## Why this guide exists

The program's canonical tooling is **VS Code with the Claude Code extension**. Engineers can get there in 10 minutes. Non-technical attendees can't — not because they're unable, but because the standard install paths assume terminal familiarity that they reasonably don't have. This guide gives them a GUI-only path to the same ready state.

The cohort is **dedicated**: they will do the pre-work if we give them clear pre-work to do. The risk isn't motivation; it's clarity.

## What "ready" means at S1

You arrive at S1 able to:

- Open **VS Code** on your machine
- See the **Claude panel** inside VS Code
- Type a message to Claude and get a reply
- Have **one small piece of your own day-to-day work** ready to share with Claude (see step 6 below — it's role-specific, not ticket-specific)

That's it for S1. Everything else builds from there. You will not need to clone a repo, run a terminal command, or read documentation before S1.

## Step-by-step (sketch — screenshots TBD)

1. **Install VS Code.** *[link to platform-specific download; screenshot of installer; what to click]*
2. **Install the Claude Code extension.** *[where to find it in VS Code's marketplace UI; screenshot]*
3. **Authenticate.** *[browser-based flow; what window pops up; what to click]*
4. **Open the Claude panel.** *[where the panel lives in the VS Code sidebar; screenshot]*
5. **Say hello.** Type one short message ("hi, can you read this?"). Confirm you get a reply.
6. **Pick something small from your daily work to bring.** Not a ticket specifically — *something native to your role*. Examples:
   - *Product:* a Jira ticket whose description or AC could be sharper
   - *Design:* a user-flow note, screen description, or design rationale you're polishing
   - *QA:* a vague acceptance criterion you'd like to sharpen into testable assertions, or a flaky test you're triaging
   - *Engineering:* a piece of code you'd like to understand, refactor, or document better

   Whatever you bring, make sure it's **small** (you wouldn't mind spending 10 minutes on it with help) and **not urgent** (if Claude says something weird, no one is depending on a fast answer).

Estimated time: **30–60 minutes**, including download/install. If a step takes more than 10 minutes, stop and bring it to the pre-S1 coaching hour.

## What you do NOT need to do before S1

- Clone a repository (an engineer pairs with you in S4 — week 4 — when you need it)
- Install any command-line tools beyond what VS Code installs automatically
- Configure Jira from a terminal (your facilitator handles MCP setup)
- Read documentation about *agents*, *skills*, *MCPs*, or *hooks* — that's what the program is for

## If you get stuck

The **pre-S1 coaching hour** is dedicated to this. Bring whatever step you got stuck on. No question is too small — these steps look obvious to engineers and entirely opaque to anyone else, and that's not a you-problem.

If you get stuck and can't make the coaching hour, post in the shared channel and someone will pair with you async.

## What's coming after S1

So you can mentally prepare:

- **Sessions 2–3:** more prompts, no new tools. Things get more interesting; the tooling stays the same.
- **Session 4:** you'll touch a repository for the first time, **paired with an engineer**. The git side is GUI through VS Code — no terminal.
- **Sessions 5–6:** refining and reviewing the team's workflow. By this point you're driving.

## Open questions for alignment

Before drafting this in full (with real screenshots and tested steps):

1. **Format.** Single doc with screenshots? Video walkthrough? Both? (My recommendation: both — screenshots in the doc for reference, a 5–7 min video for the install path.)
2. **Pre-S1 coaching hour cadence.** One pre-S1 coaching hour, or multiple if the cohort needs it? Mandatory for non-tech attendees, or optional?
3. **QA segmentation.** QA folks in some teams *do* touch terminals occasionally. Should QA have a hybrid track, or just default to non-technical and let the engineers among them skim?
4. **Distribution.** Where does this live — a Notion page, a Confluence page, a PDF, the GitHub repo? Where will non-technical attendees actually find it and open it without friction?
5. **Authentication account.** Which Claude account/login do non-technical attendees use — a personal one, a team one, an org-managed SSO? Lock this before the install steps are written, because the screenshots depend on it.
6. **Jira MCP setup for non-technical attendees.** Is this configured *for them* (by IT or a facilitator), or do they configure it themselves through a GUI? Affects whether step 6 above stays as "open a Jira ticket in a browser" or expands to include MCP config.
