---
name: write
description: Turn ideas into deliverable writing, split into two tracks — 📚 Academic (adds a mandatory evidence-gathering step; every claim gets a traceable source) and ✍️ Regular (emails, posts, docs, narrative). Each track runs in 🧠 Philosopher (default) or ⚙️ Engineer mode. Saves drafts to outputs/drafts/. Use when the user says "help me write/draft X", "write a paper", "write an email", or invokes the skill.
---

# Write Workflow

Turn ideas into **deliverable writing**.

## Start

1. **Route-confirm** (see `CONVENTIONS.md`): one line stating this is the write workflow and the suggested mode; wait for the go-ahead.
2. **Confirm mode**: default 🧠 **Philosopher**; the user may switch to ⚙️ Engineer.
3. **Confirm track**: 📚 **Academic** or ✍️ **Regular** (decides which branch below).

---

## ✍️ Regular writing

Emails, posts, docs, narrative parts of applications — writing **not centered on citations**.

**🧠 Philosopher mode (default)**: ① Dig for the *one* core idea → ② Interrogate the angle (why this, does it match the real story) → ③ Write only once the core is set → ④ Capture.

**⚙️ Engineer mode**: ① Define the goal (who reads it, what action) → ② Outline (get the skeleton confirmed) → ③ Draft (match tone) → ④ Trim + proof (names, emails, dates, numbers) → ⑤ Capture.

---

## 📚 Academic writing

Course papers, research reports, literature-backed essays — anything where **claims need evidence**.
This track adds a **mandatory evidence-gathering step**, and every fact/claim must have a traceable source.

1. **Thesis** — What is the claim/question? What does it answer? Bound the scope.
2. **🔍 Gather evidence (mandatory — the core of this track)** — Search the literature/data online; **attach a traceable source to every claim** (paper title, authoritative source, link). For broad needs, call the `research` or `deep-research` skill. **Separate fact / inference**, flag what's uncertain, never fabricate.
3. **Compose** — Follow an academic structure (intro → claims → evidence → conclusion); **attach citations as you write**, evidence next to each claim.
4. **Verify citations** — Check each one: it really exists, it actually supports the claim, format is consistent.
5. **Capture** — Save to `outputs/drafts/draft_<english-slug>.md` (body + **reference list**).

> Mode still applies: 🧠 Philosopher = think the argument/position through before gathering and writing; ⚙️ Engineer = produce to the structure, time-boxed.

---

## Wrap-up conventions

- **Never send on the user's behalf** — produce the draft, let them review.
- **Live-search / verify facts** — verify external facts online; academic citations **must be traceable, never fabricated**.
- **Promote**: if it's directional/reusable, offer to save it to long-term memory; one-off outputs stay put.
- Filenames use **English slugs**.
