---
name: research
description: Turn a question or topic into an evidence-backed, cited research output (literature review, technical report, option comparison, project scoping). Default Engineer mode (define question -> multi-source search -> cross-verify -> structured output); Philosopher mode for truly mapping a field's threads and debates. Can call the deep-research skill for heavy fan-out. Saves to outputs/research/. Use when the user says "research X", "do a survey of", or invokes the skill.
---

# Research Workflow

Turn a question / topic into an **evidence-backed, cited, deliverable** output.

## Start

1. **Route-confirm** (see `CONVENTIONS.md`): one line stating this is the research workflow and the suggested mode; wait for the go-ahead.
2. **Confirm mode**: default ⚙️ **Engineer**; the user may switch to 🧠 Philosopher.
3. **Decide on heavy search**: for broad questions needing multi-source fan-out + fact-checking, call the `deep-research` skill; for small ones, use plain web search/fetch.

## ⚙️ Engineer mode (default)

Goal: **a report you can act on or decide from, time-boxed**.

1. **Define the question** — The *specific* question. For whom, what decision? Bound the scope.
2. **Multi-source search** — Papers / authoritative sites; **cite every claim**. Go deep-research if broad.
3. **Distill + cross-verify** — Cross-check key conclusions across ≥2 sources; **flag what's uncertain**; never pass guesses as fact.
4. **Structured output** — Review / comparison table / report, conclusions first, with citations.
5. **Capture** — Save to `outputs/research/research_<english-slug>.md` (conclusion + evidence + citations + next steps).

## 🧠 Philosopher mode

For **truly understanding a field** (not just shipping a report): map the threads, schools, and core disagreements, then form your own judgment.

1. **Map the field** — Main schools / methods / timeline; who disagrees with whom and why.
2. **Trace to first principles** — Each school's core assumptions; when do they hold or fail?
3. **Form a judgment** — Where you stand and why.
4. **Capture** — Same location.

## Wrap-up conventions

- **Live-search principle (mandatory)** — all material searched live; **citations must be traceable**; don't fabricate sources.
- Separate **fact / inference / opinion** — don't blur them.
- **Promote**: if it's directional/reusable, offer to save it to long-term memory; one-off outputs stay put.
- Filenames use **English slugs**.
