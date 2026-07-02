---
name: plan
description: Turn a goal into an executable plan with milestones, dependencies, schedule, and checkpoints. Default Engineer mode. Uses whatever context the user provides as a baseline, fine-tunes from current info, and asks for missing key inputs instead of assuming. Saves to outputs/plans/. Use when the user says "help me plan X", "make a timeline", "schedule this", or invokes the skill.
---

# Plan Workflow

Turn a goal into a **milestone-based, dependency-aware, scheduled, trackable** plan.

## Start

1. **Route-confirm** (see `CONVENTIONS.md`): one line stating this is the plan workflow and the suggested mode; wait for the go-ahead.
2. **Confirm mode**: default ⚙️ **Engineer**; the user may switch to 🧠 Philosopher.
3. **Establish the baseline**: use any context the user has provided (notes, prior plans, constraints) as the starting point; fine-tune from current info. **When a key input is missing, ask the user before scheduling — don't assume.**

## ⚙️ Engineer mode (default)

Goal: **a plan you can execute against**.

1. **Define the goal** — goal + measurable success criterion + deadline.
2. **Take stock** — assemble the starting point from context + known constraints/resources; **state your assumptions out loud ("I'm assuming X — correct?")** and ask for any missing key facts.
3. **Decompose** — milestones → tasks → mark dependencies.
4. **Schedule** — timeline, critical path, buffers.
5. **Risks + Plan B** — what's most likely to slip, and the fallback.
6. **Checkpoints** — how to track progress and when to review.
7. **Capture** — Save to `outputs/plans/plan_<english-slug>.md`.

## 🧠 Philosopher mode

For **thinking before scheduling**: should this goal be pursued, what's the real objective? Then switch to Engineer mode to schedule.

## Wrap-up conventions

- In the plan, **separate**: known facts / your assumptions / awaiting-confirmation.
- **Live-search principle**: verify external facts (deadlines, policies, requirements) online — don't rely on training memory.
- Keep a "current progress + next step" line so work resumes across sessions.
- **Promote**: if it's directional/reusable, offer to save it to long-term memory; one-off outputs stay put.
- Filenames use **English slugs**.
