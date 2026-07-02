---
name: learn
description: Absorb a topic, paper, or lesson into reusable knowledge. Default Philosopher mode (first-principles decomposition + optional Feynman check + a distilled note); Engineer mode for time-boxed extraction of usable takeaways. Saves notes to outputs/notes/. Use when the user says "I want to learn X", "help me understand this paper", or invokes the skill.
---

# Learn Workflow

Turn a topic / paper / lesson into **reusable, durable knowledge**.

## Start

1. **Route-confirm** (see `CONVENTIONS.md`): in one line, say this is the learn workflow and which mode you suggest; wait for the go-ahead.
2. **Confirm mode**: default 🧠 **Philosopher**; the user may switch to ⚙️ Engineer.
3. *(Optional)* Anchor the material to the user's own focus area so new knowledge connects to what they care about.

## 🧠 Philosopher mode (default)

Goal: **truly understand, reusable for life**. Slow is fine; half-baked is not.

1. **Frame** — What is this? What field? Why does it matter?
2. **Decompose to first principles** — Break down to irreducible concepts; at each layer ask "why this way, why not otherwise?"
3. **Feynman check (optional)** — Have the user explain it back in plain words. Where they stumble = not yet understood → go back and fill the gap. Skippable on request.
4. **Connect** — Link to what they already know (prior topics, notes).
5. **Capture** — Write `outputs/notes/note_<english-slug>.md`: one-sentence essence + 3 key insights + open questions.

## ⚙️ Engineer mode

Goal: **get usable conclusions, time-boxed**. For exams / reproducing a result / looking up one thing.

1. **Anchor the goal** — What will you do with this? (exam / reproduce / ship)
2. **Extract** — Go straight to takeaways + key formulas / APIs; skip derivations.
3. **Action list** — Turn it into executable steps or a code skeleton.
4. **Capture** — Write `outputs/notes/cheat_<english-slug>.md`: a quick-reference card.

## Wrap-up conventions

- **Live-search principle**: look up external facts (papers, recipes, APIs, data) online; don't rely on training memory. Pure reasoning / math is exempt.
- **Promote**: if it's directional/reusable, offer to save it to long-term memory; one-off outputs stay put.
- Filenames use **English slugs** (e.g. `note_transformers.md`).
- Follow the host repo's `CLAUDE.md` style if present.
