# AI Training: Class 1: Skills

Welcome. This is the first live session of this engagement. By the end of the hour you'll have written your own agent skill and run it against real OpenSpec work.

> **Tooling:** We standardize on **Claude Code**. Cursor's fine too, and you don't have to give it up. For most people the best setup is Claude Code running alongside Cursor, so you get Cursor's editor and Claude's agent in one workflow. Examples here use Claude Code.

## What this class is

Four weeks, role-mixed (Dev, QA, Product), all hands-on with your own codebase and backlog. We are not here to watch slides. You bring real work; you leave each session with something that runs.

Class 1 covers the foundation: how to prompt and feed context well, how to make the agent remember your preferences with a CLAUDE.md, and how to build, vet, and run **skills** so the agent does your repetitive work the way you would.

> **Never used OpenSpec? Still fine.** OpenSpec is a workflow for writing a spec before the agent builds, so it doesn't drift. One-line version: a change has a proposal, spec deltas, and tasks the agent works through. Skim [spec-before-you-ship](https://spec-before-you-ship.vercel.app/) if it's new to you; Module 3 gives you a 30-second path either way.

## How each session runs

| | |
|---|---|
| **Core** | 60 minutes. Core session content (Modules 1 through 4). |
| **Office hours** | Optional 30 minutes after. Deeper questions, skill iteration, stuck-point help. Stay if you can; you won't miss anything required if you can't. |
| **Format** | Short framing, then you build. Module 3 runs in breakout rooms. |

## What we're asking of you across the four weeks

This part is about the engagement, not the live hour. Most of it happens between sessions.

- **Code AI-first.** Default to working with the agent; fall back to manual only when the agent can't finish the job.
- **Cameras on** during live sessions, so we're working with people not avatars.
- **Share wins and failures** in the channel. Fire-and-forget is fine; a failure is more useful to everyone than silence.
- **Complete the weekly survey.** It directly shapes what we cover next.

## The arc

Class 1 is Week 0. Here is where it sits and where we go next. **Schedule and topics are subject to change** as we learn what the team needs, expect adjustments week to week.

| Week | Topic | Required | Optional |
|------|-------|----------|----------|
| **0, Tue (this session)** | **Introduction: prompt & context engineering; Agents/CLAUDE.md; prompts; skills** | **Dev, QA, Product** | |
| 1a, Tue | Intent engineering; plan modes; spec-driven development | Dev, QA, Product | |
| 1b, Thu | Rapid prototyping; prototype-driven specification and development | Product | Dev, QA |
| 2a, Tue | Evals: testing and verified spec-driven development | Dev, QA | Product |
| 2b, Thu | Intent engineering for Product strategy; self-updating product artifacts, roadmaps, backlogs | Product | Dev, QA |
| 3, Tue | Subagents; long-running agents; metaharnesses; dark factories | Dev, QA | Product |
| 4, Tue | Retrospective | Dev, QA, Product | |

The direction is the **Dark Factory**: requirements go in, mergeable PRs come out. You do not have to reach a fully dark factory for the move toward it to change how you work.

## Where you are now: the six levels

Place yourself honestly on this ladder. It's Dan Shapiro's framing, popularized by Nate B. Jones ([source](https://simonwillison.net/2026/Jan/28/the-five-levels/)), and Shapiro modeled it on the [driving automation levels NHTSA uses](https://www.nhtsa.gov/vehicle-safety/automated-vehicles-safety). Same six rungs, different vehicle.

| Level | Self-driving (NHTSA) | AI coding agent (Shapiro) |
|:---:|---|---|
| 0 | Momentary Driver Assistance | **Spicy autocomplete**: you type, AI finishes the line. You approve every character. |
| 1 | Driver Assistance | **The coding intern**: discrete chores: a test, a docstring. |
| 2 | Additional Assistance | **The junior developer**: whole boring tasks handed off. Most "AI-native" devs are stuck here. |
| 3 | Conditional Automation | **The developer**: the agent does the work; you review and steer it like a teammate. |
| 4 | High Automation | **The engineering team**: you write and argue specs, then check back when the tests finish. |
| 5 | Full Automation | **The dark software factory**: no one reviews AI code line by line. Humans design the system that proves it. |

Most teams sit at level 2 and assume that's the ceiling. This engagement is about moving up deliberately. Today's work, CLAUDE.md and skills, is how you stop re-explaining yourself to the agent and start operating at level 3 and above.

## Before Class 1

Do the [Prerequisites](prerequisites.md). Only one item is required: Claude installed and telling you a joke. The rest help but won't block you.
