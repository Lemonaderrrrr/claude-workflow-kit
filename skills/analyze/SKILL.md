---
name: analyze
description: Turn data, a situation, or a set of options into a structured analysis with a confidence-rated conclusion. Default Engineer mode. Two branches — 🧮 Decision analysis (which path to choose) and 📈 Data analysis (find insight in data). Hands off to the research skill when external data is missing. Saves to outputs/analysis/. Use when the user says "analyze this", "run the numbers", "which of these should I pick", "what does this data say", or invokes the skill.
---

# Analyze Workflow

Turn data / a situation / options into a **structured analysis + a confidence-rated conclusion**.

## Start

1. **Route-confirm** (see `CONVENTIONS.md`): one line stating this is the analyze workflow and the suggested mode; wait for the go-ahead.
2. **Confirm mode**: default ⚙️ **Engineer**; the user may switch to 🧠 Philosopher.
3. **Confirm branch**: 🧮 **Decision analysis** or 📈 **Data analysis**.

---

## 🧮 Decision-analysis branch (which path / whether to do it)

1. **Define the decision** — choosing between what? Supporting what action?
2. **Pick a framework** — decision matrix / cost-benefit / weighted scoring.
3. **List options + criteria + weights** — lay out candidates and judging dimensions.
4. **Score + run the numbers** — show the work, don't hand-wave.
5. **Conclusion + confidence + sensitivity** — what to pick, how sure, **what would flip it**.
6. **Capture** — `outputs/analysis/analysis_<english-slug>.md`.

## 📈 Data-analysis branch (find insight in data)

1. **Define the question** — what are we answering?
2. **Inspect the data** — structure / quality / missing values.
3. **Explore** — descriptive stats / distributions / correlations.
4. **Findings** — patterns / anomalies / relationships.
5. **Conclusion + limits** — don't claim what the data doesn't support.
6. **Capture** — same location.

---

## Wrap-up conventions

- **Separate fact / inference / opinion**; give the conclusion a **confidence** level.
- When external data is missing, **hand off to the `research` skill** — don't invent numbers from memory.
- For any quantitative claim, **show the calculation**, not just the result.
- **Promote**: if it's directional/reusable, offer to save it to long-term memory; one-off outputs stay put.
- Filenames use **English slugs**.
