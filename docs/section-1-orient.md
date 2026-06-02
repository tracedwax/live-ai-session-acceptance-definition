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

This is the demo. **Drive on a real feature; narrate as you go.** (If a connection isn't ready, drive on your own Jira.) Run the loop once so the rooms have a template: **feature → explore → grill out the gaps → split → one artifact at a time → tickets.** Model the habit out loud: **you are not one-shotting this**, you make one thing, read it, then make the next.

**The reveal, Claude reads Jira for you:**

> *"Pull my ticket from Jira and summarize what it's asking for."*

When it comes back, name it (gently):

- "Notice I didn't paste the ticket. Claude **read it from Jira** for me. That connection is called an **MCP**: it just means Claude can reach the tools you already use."

**Then the loop, narrated:**

1. **Dump everything, explore the whole feature.** *"Here's the feature, plus my rough notes and what we said in refinement. Explore it with me before we write or split anything, what are all the distinct behaviors here? Don't write yet."* (Or just `/opsx:explore`.)
2. **Let the `grill-me` skill find what's missing.** Run it on the feature and answer 2-3 questions live. Then name it:
   > **The point:** *"I didn't have to know the right questions. `grill me` found the holes for me, and every answer is a decision that belongs in the ticket. That's how the ticket gets complete before anyone writes code."*
3. **Split by behavior.** *"Now split this into independently shippable behaviors, one bucket each, named like a behavior, with a one-line 'Why' (the business value)."* Say out loud: *"Not a frontend ticket and a backend ticket, those have no value on their own. We split by what a user can see work."*
4. **Propose.** `/opsx:propose`, Claude writes the proposal + a spec per behavior. Point at the files appearing under `openspec/changes/`.
5. **Create the tickets, confirm-first.** *"In my Jira project, create an Epic from the proposal and a Story per behavior with its 'Why', plus sub-tasks. Show me the tree first."*, read it, then say **"go."** (Demoing on a real backlog? Use the **Mocking Project** (`MP`) sandbox, or print the tree as markdown.)

Then close the demo with the honest line:

> "I turned one fuzzy feature into a clean set of tickets that each deliver something, and `grill me` did the work of finding what I'd have missed. The thinking was still mine; it just stopped me from shipping vague. Now you do it on yours."

> **Autosave aside (10 seconds):** point out that Claude's been making tiny git commits after each step. *"That's autosave, you never touch git. It's just an undo trail."*

## Done when

- Two people have said how they've used Claude
- The room has seen Claude **read a feature from Jira**, get **grilled into completeness**, **split by behavior**, and **create a ticket tree on confirm**
- Everyone knows which room they're in and what they're producing

Send them to [Section 2](section-2-breakout.md).
