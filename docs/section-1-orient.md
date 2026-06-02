# Section 1: Orient

> **Time: ~20 min. All together.** Ends with everyone having seen a finished OpenSpec example, and knowing the journey their own room runs.

## Rules of engagement (read these first)

This is a hands-on working session, not a webinar. Three things we're asking of everyone:

1. **Follow along live.** Do the work on your own machine as we go. You learn this by typing it, not by watching someone else.
2. **Share your screen while you work.** We all keep our screens shared in the breakout so facilitators can spot where you're stuck and help fast. Rough and messy is expected; nobody's being graded.
3. **Speak up the moment a question lands.** Mid-build questions are the useful ones, ask them out loud or in chat right away.

Two safety habits we'll repeat all session: **nothing is created in Jira until you read the plan and say go**, and **messy input is the point** (half-formed notes feed the agent better than a polished paragraph).

The only goal of this first part is that when we split into rooms, nobody is staring at a blank screen wondering what to type. They've seen it.

## Welcome & level-set (5 min)

Quick and warm. Round-robin, each person answers two things:

> *"What did you do with AI this past week? And which ticket did you bring today?"*

This gets voices in early and surfaces where the room is starting from. "I haven't really" is a fine answer to the first.

**Confirm everyone brought a ticket, and have them pull it up in Jira right now.** That's what they'll work in the breakout. Anyone without one, flag it to a facilitator.

Then name the win out loud:

> "By the end of the session you'll have taken something you own and, with Claude, made it real, one piece at a time. **Product:** your feature split into **value-bearing Jira tickets in your own project**, an Epic, a Story per behavior, sub-tasks, each backed by a proposal and a spec. **QA:** test cases to your team's standard saved to your shared repo, plus a **shared skill** so the team drafts to the same bar next time. Same habit, your half of it."

## The gentle frame (3 min)

*Adapted from Aldric's facilitator script, keep it this light. Two words, no jargon.*

Open Claude in VS Code and ask it something tiny about a ticket, out loud, narrating:

> *"Read this and tell me, in one sentence, what a developer would still have to guess."*

Let it answer. Then:

- "What you just saw me do is send a **prompt**: a message to a colleague."
- "That colleague is an **agent**. It reads instantly and forgets nothing. That's the whole mental model for today: **agent, prompt.**"
- "It gets more complicated later. Not today."

> **Talking point that lands:** *"You just watched me onboard a teammate who's read the entire ticket before I finished asking."*

## Connect Jira & see a finished OpenSpec example (10 min)

> **First, make sure Jira answers in this folder.** If you set the Jira MCP up in another repo, it may be configured there and not here. Ask Claude to **move the MCP config to your global setup** so it works in every folder. Not sure where yours lives, or starting fresh? Just ask Claude to walk you through MCP setup.

This is the opening look, not a live build: **Trace shares a finished OpenSpec example** so the room sees the shape they're aiming for, the same arc the Product room runs in [Section 2, Steps 1-5](section-2-breakout.md). Put a completed change on screen, the proposal, a spec or two, and the Jira ticket tree it produced, and walk the shape out loud. The real building, one artifact at a time, happens in the breakout; here we just study a good finished one.

**The reveal, Claude reads Jira for you:**

> *"Pull my ticket from Jira and summarize what it's asking for."*

When it comes back, name it (gently):

- "Notice I didn't paste the ticket. Claude **read it from Jira** for me. That connection is called an **MCP**: it just means Claude can reach the tools you already use."

**Then walk the example, naming each piece (these are the room's Steps 1-5):**

1. **Explore + grill (Step 1).** Show how the messy feature got mapped to every behavior it touches, and point out where the `grill-me` answers ended up written into the spec. Name it: *"I didn't have to know the right questions; grill-me found the holes, and every answer became a decision in the ticket."*
2. **Split by behavior (Step 2).** Show the 2-4 behaviors, each named like a behavior with a one-line "Why". Say it: *"Not a frontend ticket and a backend ticket, those have no value alone. We split by what a user can see work."*
3. **Proposal (Step 3).** Open `proposal.md`, read the what and why; that became the **Epic**.
4. **Specs (Step 4).** Open one `spec.md`, show the WHEN/THEN scenarios; each spec became a **Story**.
5. **Tickets (Step 5).** Show the **Epic**, a **Story per behavior**, **sub-tasks** underneath.

Name the habit: *"This got built one artifact at a time, each one reviewed, not one-shot. That's what you'll do next, on your own ticket, as a practice clone."*

Then close:

> "That's the target: one fuzzy feature, explored, split, and turned into tickets that each deliver something. You'll build your own in a minute, one piece at a time. Let's split into rooms."

> **QA, your parallel arc (the [QA room](section-2-breakout.md), same habit).** You won't split a feature into tickets; you'll hold a story to the bar. Pull your own ticket, run `grill-me` to surface what it takes to test it, draft to your team's [Test Case Standard](https://aspenware.atlassian.net/wiki/spaces/QA/pages/4137582614/Test+Case+Standard) (or level up cases that already exist), then critique and improve before you save. The payoff is a shared `write-test-cases` skill committed back so the whole team drafts the same way. (Facilitator B can speak to this in 30 seconds so QA folks have their template too.)

> **Autosave aside (10 seconds):** mention that in the breakout, Claude autosaves with a tiny git commit after each step. *"You never touch git; it's just an undo trail."*

## Done when

- Two people have said how they've used Claude
- The room has seen a **finished OpenSpec example** (the proposal, a spec, and the ticket tree) and the **5-step shape** they'll follow
- QA has heard their **parallel arc** (pull the ticket, grill what's needed, draft to the standard, critique, save)
- Everyone knows which room they're in and what they're producing

Send them to [Section 2](section-2-breakout.md).
