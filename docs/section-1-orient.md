# Section 1 — Orient

> **Time: ~17 min. All together.** Ends with everyone having watched the whole loop once, on a real ticket.

The only goal here is that when we split into rooms, nobody is staring at a blank screen wondering what to type. They've seen it.

## Welcome & level-set (5 min)

Quick and warm. Then one question in chat — **two people answer aloud:**

> *"In one line: how have you used Claude so far — even once? What did you ask it?"*

This tells you the room's real starting point and gets voices in early. No wrong answers; "I haven't really" is a fine answer.

Then name the win out loud:

> "By the end of the hour you'll have taken one of your own tickets and gotten its acceptance criteria from rough to ready — with Claude — and pushed it to Jira. Product writes the story. QA writes the test cases. Same move, your half of it."

## The gentle frame (3 min)

*Adapted from Aldric's facilitator script — keep it this light. Two words, no jargon.*

Open Claude in VS Code and ask it something tiny about a ticket — out loud, narrating:

> *"Read this and tell me, in one sentence, what a developer would still have to guess."*

Let it answer. Then:

- "What you just saw me do is send a **prompt** — a message to a colleague."
- "That colleague is an **agent**. It reads instantly and forgets nothing. That's the whole mental model for today: **agent, prompt.**"
- "It gets more complicated later. Not today."

> **Talking point that lands:** *"You just watched me onboard a teammate who's read the entire ticket before I finished asking."*

## Connect Jira & watch the loop (9 min)

This is the demo. **Erin drives on a real ticket; you narrate.** (If a connection isn't ready, you drive on your own Jira.) Run the *entire* loop once so the rooms have a template.

**The reveal — Claude reads Jira for you:**

> *"Pull ticket [CHK-3334] from Jira and summarize what it's asking for."*

When it comes back, name it (gently):

- "Notice I didn't paste the ticket. Claude **read it from Jira** for me. That connection is called an **MCP** — it just means Claude can reach the tools you already use."

**Then the loop, narrated:**

1. **Dump everything.** *"Here's the ticket, plus my rough notes and what we said in the refinement call. Don't write anything yet."*
2. **Show a good example.** *"Here's a ticket whose AC I like — [PUR-6243]. Match that shape: Given / When / Then, testable, edge cases named."*
3. **One-shot it.** *"Now draft acceptance criteria for my ticket."* — read it aloud; let the room see it's *okay, not great.*
4. **Grill.** *"`grill me` on these acceptance criteria — one question at a time."* — answer 2–3 questions live so they see it sharpen.
5. **Review the draft**, then **confirm-to-push.** *"Update the ticket's acceptance criteria in Jira. Show me the change first."* — read it, then say **"go."**

Then close the demo with the honest line:

> "I pushed the **story and the AC** the agent helped me sharpen. The thinking was still mine — it just stopped me from shipping something vague. That's the whole hour. Now you do it on yours."

## Done when

- Two people have said how they've used Claude
- The room has seen Claude **read a ticket from Jira**, get **grilled**, and **push a reviewed change**
- Everyone knows which room they're in and what they're producing

Send them to [Section 2](section-2-breakout.md).
