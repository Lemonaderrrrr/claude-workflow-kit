---
name: build
description: Turn an idea into a working product or project (side projects, repos, technical designs). Default Engineer mode (define needs -> design -> MVP -> iterate); Philosopher mode for thinking through "should this exist, what is it really, what's the differentiation" before building. Saves to outputs/build/. Use when the user says "I want to build X", "design this project", or invokes the skill.
---

# Build Workflow

Turn an idea into something **that runs and ships**.

## Start

1. **Route-confirm** (see `CONVENTIONS.md`): one line stating this is the build workflow and the suggested mode; wait for the go-ahead.
2. **Confirm mode**: default ⚙️ **Engineer**; the user may switch to 🧠 Philosopher.
3. *(Optional)* Align with the user's broader product/strategy goals if they have one.

## ⚙️ Engineer mode (default)

Goal: **make it and get it running** — validate in small steps, not all at once.

1. **Define needs** — What problem? For whom? **Measurable success criterion**? Cut nice-to-haves first.
2. **Design** — Break into modules / pick architecture / make tech choices; write down the key **trade-offs** (why A not B).
3. **MVP** — Build the smallest version that validates the core assumption; get the main path working before optimizing.
4. **Iterate** — Compare results to the success criterion → find the bottleneck → change one thing at a time.
5. **Capture** — Save to `outputs/build/build_<english-slug>.md` (needs + design + trade-offs + current progress + next step).

## 🧠 Philosopher mode

For **thinking before building** (should it exist, what is it): avoid building a pretty solution to a fake problem.

1. **Dig for the real need** — The genuine pain point? Real need or vanity feature?
2. **Interrogate from first principles** — Why this solution? Where's the real differentiation?
3. **Set direction** — Once it's clear, switch to Engineer mode and build.
4. **Capture** — Same location.

## Wrap-up conventions

- Keep design docs separate from code (docs in `outputs/build/`).
- Maintain a "current progress + next step" line per project so work resumes cleanly across sessions.
- **Promote**: if it's directional/reusable, offer to save it to long-term memory; one-off outputs stay put.
- Filenames use **English slugs**.
