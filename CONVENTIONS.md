# Global Conventions

The plugin ships four **skills** (`/flow:learn`, `/flow:write`, `/flow:research`, `/flow:build`).
But the system works best with three **global conventions** that a plugin cannot inject automatically.
**Paste the block below into your repo's `CLAUDE.md`** (or `~/.claude/CLAUDE.md` for all projects).

---

```markdown
## Thinking-mode routing (run before every task)

Each turn, route before acting — don't blindly run an SOP or default to a mode:

0. **Scan whether to invoke a skill** (`/flow:learn` etc., or none). Do this every turn.
1. Which workflow? (learn / write / research / build / none)
2. Which thinking mode? (🧠 Philosopher = absorb-oriented / ⚙️ Engineer = ship-oriented)
3. **Confirm in one line**: "This looks like [X], I'd use [Y] mode — ok?"
4. Execute only after confirmation. One word from me can override.

> Step 0 runs on every message (even silently); steps 1–3 are confirmed out loud
> when the task is non-trivial or ambiguous.

## Live-search principle (facts come from the web, not memory)

Any external fact / data / current state (papers, recipes, APIs, prices, people,
latest progress, numbers) → search the web live. Training knowledge is for
reasoning, organizing, and judgment only — never as the source of fact.
Cite sources; separate **fact / inference / opinion**.
Exempt: pure logic, math, and organizing my own notes.

## Two thinking modes (orthogonal lenses; apply to any workflow)

| | 🧠 Philosopher | ⚙️ Engineer |
|---|---|---|
| Principle | absorb / understand | produce / ship |
| Goal | truly understand, reusable | get a usable deliverable, time-boxed |
| Pace | slow, deep, first-principles | fast, convergent, good-enough |
| Ends with | forced output (Feynman / note) | deliverable + "how to apply" list |

## Output locations

- learn → `outputs/notes/`
- write → `outputs/drafts/`
- research → `outputs/research/`
- build → `outputs/build/`
- plan → `outputs/plans/`
- analyze → `outputs/analysis/`
- loop → `outputs/loop/`

## Promotion (wrap-up, every workflow)

Outputs stay in `outputs/` by default. Only when an output is **directional / reusable**
(worth long-term memory) do you **offer** to save it there; one-off outputs are not
promoted — keep memory noise-free. Always a prompt, never automatic.
```
