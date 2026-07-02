---
name: loop
description: A closed-loop delivery engine that wraps any output-oriented task — define spec, get your approval, then autonomously produce + adversarially self-check and iterate (max 3 rounds), show you only when aligned, and re-loop on your feedback until you're satisfied. Orchestrates the other SOPs (build/write/research/plan/analyze) and the two thinking modes. Default Engineer mode. Offer it proactively when a task is a substantial, multi-step deliverable; the user may also invoke it directly. Saves to outputs/loop/.
---

# Loop — Closed-Loop Delivery Engine

A top-level orchestration over **any output-oriented task**: turn "define goal → produce →
self-check → show you → iterate" into a closed loop. The inner self-check iterations are on me;
two gates are yours.

## Trigger

When a task is a **substantial, multi-step deliverable**, ask: "Want to run this through `/loop`?"
(Don't offer for one-line answers or small edits.) The user may also invoke `/loop` directly.

---

## 🚪 Gate 1 · Define the spec (keep asking → your approval)

By questioning the user, lock down three things and present a **spec** for approval:

1. **Product goal** — what to build, for whom, why.
2. **Operating + acceptance criteria** — constraints (scope / style / tech) + a checkable
   **definition of done** (the *same ruler* used by both self-check and your review).
3. **Mode + SOP** — 🧠 Philosopher / ⚙️ Engineer (default Engineer) + which existing workflow
   to drive (`build` / `write` / `research` / `plan` / `analyze`).

> **No work starts before approval.** Keep asking for missing key inputs — don't assume.

---

## 🔁 Self-check loop · autonomous (user not involved)

After approval:

1. **Produce** — make a version via the chosen SOP + mode.
2. **Adversarial self-check** — play the critic; itemize every place it fails the acceptance
   criteria. If you can find faults, it's not aligned.
3. **Decide**:
   - Faults found → iterate, back to step 1 (**max 3 rounds**).
   - No faults (aligned) → show the user.
   - Still not aligned after **3 rounds** → **show the user anyway + state what's stuck and
     what's missing**. Never fake completion.
4. **Log** — each round: what changed / what the self-check caught / aligned or not.

---

## 🚪 Gate 2 · Your review

- **Satisfied** → done, archive.
- **Not satisfied** → **judge the feedback intelligently**:
  - "The output is off" → back to the self-check loop with the feedback.
  - "The goal/criteria were wrong" → back to Gate 1 to redefine the spec.
  - Repeat until satisfied.

---

## Wrap-up

- Maintain `outputs/loop/loop_<english-slug>.md` throughout: **spec + acceptance checklist +
  iteration log + current status** (so work resumes across sessions).
- Live-search principle applies: verify external facts online.
- **Promote**: if it's directional/reusable, offer to save it to long-term memory; one-off outputs stay put.
- Follow the host repo's `CLAUDE.md` style.
