# Team Handbook — the contract every role obeys

> This is the shared "company handbook" for `/flow:team`. Planner, Engineers, and
> Reviewer all operate under these rules. When a role's own config conflicts with
> this handbook, **the handbook wins**. When the handbook is silent, escalate to
> the human (see §7).

## 1. Org chart & separation of duties

| Role | Company analog | Owns | May NOT |
|---|---|---|---|
| **Planner** | Eng Manager / Tech Lead | the spec, the **board**, decomposition, assignment, arbitration, final ship | write feature/implementation code |
| **Engineer-FE** | Frontend IC | code inside **frontend-owned dirs**, tests for own code | touch backend dirs, shared contracts (without approval), or the board |
| **Engineer-BE** | Backend IC | code inside **backend-owned dirs**, tests for own code | touch frontend dirs, shared contracts (without approval), or the board |
| **Reviewer** | QA / Gatekeeper | the quality gate: verdict PASS / REWORK | modify any implementation code, or move a ticket itself |

**One writer per surface.** Board → only Planner. Code → only the owning Engineer.
Verdicts → only Reviewer (returned to Planner, who acts on them). This is what keeps
parallel work from corrupting each other.

## 2. Directory ownership (the boundary that lets FE/BE run in parallel)

No git worktrees — isolation comes from **who may write which directories**.

- **Frontend owns**: `frontend/`, `app/`, `components/`, `src/ui/`, `src/pages/`,
  `public/`, `styles/`, plus FE config (`vite.*`, `tailwind.*`, `next.config.*`).
- **Backend owns**: `backend/`, `server/`, `src/api/`, `src/services/`, `db/`,
  `migrations/`, plus BE config (`Dockerfile`, `alembic.*`, ORM config).
- **Shared / contract** (types, API schema, OpenAPI, protobuf, shared enums,
  `src/shared/`, `packages/types/`): **frozen**. Changing one is an *Interface
  Change* and needs Planner approval (§4). Everyone may **read** shared files.

Planner records the exact owned-globs per project in the board header (§3), because
real repos vary. The lists above are the default when the project matches.

**Boundary proof (git baseline).** The Planner keeps the repo under git with a baseline
commit and commits after each ticket reaches Done. Because parallel tickets share one
working tree, ownership is proven **per ticket, path-scoped**: a reviewer diffs only the
ticket's `touches`/owned globs against the baseline (`git status --porcelain -- <paths>`),
ignoring build artifacts and other in-flight tickets' files. Only a file *this ticket
changed* that lies outside its lane is a violation.

## 3. The board (single source of truth)

One file, `BOARD.md` at repo root (template ships with this skill). Kanban columns:

`Backlog → Todo → Doing → Review → Done`  (+ `Blocked`, and the `Rework` marker).

**Ticket schema** (one block per ticket):

```
### T-007 · [BE] Create /orders endpoint
- status: Doing
- owner: engineer-backend
- layer: backend
- touches: src/api/orders.py, tests/api/test_orders.py
- depends_on: T-003
- acceptance:
  - POST /orders validates body, returns 201 + id
  - rejects missing fields with 422
  - unit tests cover both paths
- review: (empty until Reviewer verdict)
- rework_count: 0
```

Rules:
- **Only Planner edits `BOARD.md`.** Engineers/Reviewer read it; they never write it.
- A ticket names its `touches` up front — Planner rejects a plan where two tickets
  in flight touch the same file (serialize them via `depends_on` instead).
- `layer` ∈ {frontend, backend, shared}. `shared` tickets are handled specially (§4).

## 4. Interface changes (shared contracts)

When an Engineer discovers it needs a shared-contract change to finish its ticket,
it **stops and reports the request to Planner** (does not edit the shared file).
Planner then either:
1. opens a `shared` ticket, assigns it, and **blocks** dependents until it lands, or
2. rejects/reshapes the request to protect the other layer.

Both engineers are notified (via the board) when a shared contract changes, so
neither builds on a stale interface. **Contract-first**: the shared ticket lands and
is reviewed before the FE/BE tickets that depend on it start.

## 5. Definition of Done (DoD)

A ticket is Done only when **all** hold:
1. Every `acceptance` bullet is satisfied.
2. Tests for the new behavior exist **and pass** (the Engineer writes them; Reviewer
   verifies they actually exercise the acceptance criteria).
3. Only the ticket's owned dirs were touched — no boundary violations.
4. No unapproved interface change.
5. Project build / typecheck / lint (whatever the repo has) is green.

## 6. The hard gate & rework loop

```
Doing ──engineer finishes──▶ Review ──Reviewer verdict──▶ PASS  ▶ Done
                                          │
                                          └▶ REWORK ▶ back to Doing (with findings)
```

- **Nothing reaches Done without a Reviewer PASS.** No self-certification.
- On REWORK, Reviewer returns a numbered, specific findings list tied to DoD/AC.
  Planner increments `rework_count` and sends the ticket + findings back to its owner.
- **Rework cap = 3.** On the 4th failure, Planner marks the ticket `Blocked` and
  **escalates to the human** (§7) — do not loop forever.

## 7. Escalation (when to involve the human)

Planner escalates — pausing and asking the user — when:
- a ticket exceeds the rework cap,
- two tickets have an unresolvable scope/boundary conflict,
- an interface change would break the other layer and no clean option exists,
- the spec is ambiguous in a way that changes the build materially,
- tests can't run (missing deps/secrets/services) and the Engineer can't self-serve.

Never guess past a blocker that changes scope. Surface it with the specific decision
needed and 1–2 options.

## 8. Communication protocol

- Engineers and Reviewer are **stateless workers**: each is spawned with a task
  packet (the ticket + relevant context) and returns a **structured result**; they
  don't talk to each other directly. Planner is the switchboard.
- Every worker returns a machine-checkable result (see role configs for the exact
  shape) so Planner can act without re-reading the whole repo.
- Keep the board human-readable at all times — it's the audit log and the resume point.

## 9. Parallelism rules

- Planner dispatches **independent** Todo tickets to FE and BE **concurrently**
  (spawn in one batch).
- A ticket with unmet `depends_on` stays in Todo.
- Two in-flight tickets must never share a `touches` file (enforced at planning time).
- Reviewer runs can also parallelize across independent finished tickets.
