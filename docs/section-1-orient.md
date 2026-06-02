# Section 1: Orient

> **Time: ~20 min. All together.** Ends with everyone having watched the whole loop once: a real feature, split into Jira tickets.

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

> "By the end of the session you'll have taken one of your own **features** and, with Claude, broken it into **Jira tickets that each deliver real value**: an Epic, a story per behavior, sub-tasks underneath. Product splits the feature; QA writes the test cases. Same move, your half of it."

## The gentle frame (3 min)

*Adapted from Aldric's facilitator script, keep it this light. Two words, no jargon.*

Open Claude in VS Code and ask it something tiny about a ticket, out loud, narrating:

> *"Read this and tell me, in one sentence, what a developer would still have to guess."*

Let it answer. Then:

- "What you just saw me do is send a **prompt**: a message to a colleague."
- "That colleague is an **agent**. It reads instantly and forgets nothing. That's the whole mental model for today: **agent, prompt.**"
- "It gets more complicated later. Not today."

> **Talking point that lands:** *"You just watched me onboard a teammate who's read the entire ticket before I finished asking."*

## Connect Jira & watch the loop (10 min)

> **First, make sure Jira answers in this folder.** If you set the Jira MCP up in another repo, it may be configured there and not here. Ask Claude to **move the MCP config to your global setup** so it works in every folder. Not sure where yours lives, or starting fresh? Just ask Claude to walk you through MCP setup.

This is the demo, and it is the whole point of the opening: **Erin runs OpenSpec on one real feature, soup to nuts, the exact arc the Product room will do in [Section 2, Steps 1-5](section-2-breakout.md).** Drive on a real feature, narrate as you go, and go **one artifact at a time** (don't one-shot it). Move briskly: do the proposal and one spec for real, summarize the rest. (No Jira connection? Drive on your own.)

**The reveal, Claude reads Jira for you:**

> *"Pull my ticket from Jira and summarize what it's asking for."*

When it comes back, name it (gently):

- "Notice I didn't paste the ticket. Claude **read it from Jira** for me. That connection is called an **MCP**: it just means Claude can reach the tools you already use."

**Then walk the arc, narrating each step (these are the room's Steps 1-5):**

1. **Explore the whole feature (Step 1).** Dump the ticket plus your rough notes and what was said in refinement, and ask Claude to map **every behavior the feature touches**, without writing a spec yet. (`/opsx:explore` does the same.)
2. **Grill out the gaps (still Step 1).** Run the `grill-me` skill and answer 2-3 questions live. Name it:
   > **The point:** *"I didn't have to know the right questions. grill-me found the holes, and every answer is a decision that belongs in the ticket. That's how it gets complete before anyone writes code."*
3. **Split by behavior (Step 2).** Ask Claude to break the feature into independently shippable behaviors, each with a one-line "Why". Say out loud: *"Not a frontend ticket and a backend ticket, those have no value on their own. We split by what a user can see work."*
4. **Write the proposal, then review it (Step 3).** *"Draft just the proposal, the what and why. Don't write specs yet."* Open `proposal.md` on screen, read it aloud, point at one thing you'd fix. Name the habit: *"I'm not letting it one-shot the whole change. One artifact, then I read it. You'll do the same."*
5. **Write one spec, then review it (Step 4).** *"Now the spec for just this one behavior, as WHEN/THEN."* Open the spec, read it, grill one unhappy path. Mention the rest get the same treatment, one at a time.
6. **Create the tickets, confirm-first (Step 5).** *"Create the Epic from the proposal, then a Story for this behavior with its 'Why', plus sub-tasks. Show me the tree first."* Read it, then say **"go."** (Real backlog? Use the **Mocking Project** (`MP`) sandbox, or have Claude print the tree as markdown.)

Then close the demo with the honest line:

> "That's the whole move, and it's exactly what you'll do next: one fuzzy feature, explored, split, and turned into tickets that each deliver something, one artifact at a time. grill-me found what I'd have missed; the thinking was still mine. Now you do it on yours."

> **Autosave aside (10 seconds):** point out that Claude's been making tiny git commits after each step. *"That's autosave, you never touch git. It's just an undo trail."*

## Done when

- Two people have said how they've used Claude
- The room has watched the full arc once: a feature **read from Jira**, **grilled into completeness**, **split by behavior**, a **proposal and one spec written and reviewed one at a time**, and a **ticket tree created on confirm**
- Everyone knows which room they're in and what they're producing

Send them to [Section 2](section-2-breakout.md).
