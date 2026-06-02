# Section 1 — Orient

> **Time: ~20 min. All together.** Ends with everyone having watched the whole loop once: a real feature, split into Jira tickets.

The only goal here is that when we split into rooms, nobody is staring at a blank screen wondering what to type. They've seen it.

## Welcome & level-set (5 min)

Quick and warm. Then one question in chat — **two people answer aloud:**

> *"In one line: how have you used Claude so far — even once? What did you ask it?"*

This tells you the room's real starting point and gets voices in early. No wrong answers; "I haven't really" is a fine answer.

Then name the win out loud:

> "By the end of the session you'll have taken one of your own **features** and, with Claude, broken it into **Jira tickets that each deliver real value** — an Epic, a story per behavior, sub-tasks underneath. Product splits the feature; QA writes the test cases. Same move, your half of it."

## The gentle frame (3 min)

*Adapted from Aldric's facilitator script — keep it this light. Two words, no jargon.*

Open Claude in VS Code and ask it something tiny about a ticket — out loud, narrating:

> *"Read this and tell me, in one sentence, what a developer would still have to guess."*

Let it answer. Then:

- "What you just saw me do is send a **prompt** — a message to a colleague."
- "That colleague is an **agent**. It reads instantly and forgets nothing. That's the whole mental model for today: **agent, prompt.**"
- "It gets more complicated later. Not today."

> **Talking point that lands:** *"You just watched me onboard a teammate who's read the entire ticket before I finished asking."*

## Connect Jira & watch the loop (10 min)

This is the demo. **Drive on a real feature; narrate as you go.** (If a connection isn't ready, drive on your own Jira.) Run the *entire* loop once so the rooms have a template: **feature → explore → grill out the gaps → split → tickets.**

**The reveal — Claude reads Jira for you:**

> *"Pull [CHK-3334] from Jira and summarize what it's asking for."*

When it comes back, name it (gently):

- "Notice I didn't paste the ticket. Claude **read it from Jira** for me. That connection is called an **MCP** — it just means Claude can reach the tools you already use."

**Then the loop, narrated:**

1. **Dump everything, explore the whole feature.** *"Here's the feature, plus my rough notes and what we said in refinement. Explore it with me before we write or split anything — what are all the distinct behaviors here? Don't write yet."* (Or just `/opsx:explore`.)
2. **Let `grill me` find what's missing — this is the moment to land.** *"`grill me` on this feature — one question at a time. What's ambiguous, what's unspecced, what would a developer still have to guess?"* Answer 2–3 questions live. Then name it:
   > **The point:** *"I didn't have to know the right questions. `grill me` found the holes for me — and every answer is a decision that belongs in the ticket. That's how the ticket gets complete before anyone writes code."*
3. **Split by behavior.** *"Now split this into independently shippable behaviors — one bucket each, named like a behavior, with a one-line 'Why' (the business value)."* Say out loud: *"Not a frontend ticket and a backend ticket — those have no value on their own. We split by what a user can see work."*
4. **Propose.** `/opsx:propose` — Claude writes the proposal + a spec per behavior. Point at the files appearing under `openspec/changes/`.
5. **Create the tickets, confirm-first.** *"In my Jira project, create an Epic from the proposal and a Story per behavior with its 'Why', plus sub-tasks. Show me the tree first."* — read it, then say **"go."** (Demoing on a real backlog? Use a sandbox/Playground project, or print the tree as markdown.)

Then close the demo with the honest line:

> "I turned one fuzzy feature into a clean set of tickets that each deliver something — and `grill me` did the work of finding what I'd have missed. The thinking was still mine; it just stopped me from shipping vague. That's the whole session. Now you do it on yours."

> **Autosave aside (10 seconds):** point out that Claude's been making tiny git commits after each step. *"That's autosave — you never touch git. It's just an undo trail."*

## Done when

- Two people have said how they've used Claude
- The room has seen Claude **read a feature from Jira**, get **grilled into completeness**, **split by behavior**, and **create a ticket tree on confirm**
- Everyone knows which room they're in and what they're producing

Send them to [Section 2](section-2-breakout.md).
