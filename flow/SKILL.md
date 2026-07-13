---
name: flow
description: Drive an end-to-end build from a fuzzy idea to a verified implementation. Use when the user wants Codex to take work through ideation, research, prototyping, specification, decomposition, and implementation, or wants to know which build skill should run next.
---

# Flow

Start from the latest trustworthy artifact or working state. Do not restart discovery when a usable brief, map, spec, ticket set, handoff, or implementation already exists.

## Route the work

Inspect the conversation, repository instructions, relevant documents, current plan, and git state. Select the first unmet gate:

- **Unclear outcome or unresolved product decisions** -> use `$shape`.
- **A destination exists but the route contains more uncertainty than one focused task can resolve** -> use `$map`.
- **A decision depends on external or version-sensitive facts** -> use `$research`, then feed the findings back into the active brief, map, or spec.
- **A decision needs something runnable or visible** -> use `$prototype`, then record its verdict in the active brief, map, or spec.
- **The behavior is settled but not captured canonically** -> use `$spec`.
- **The spec needs multiple bounded delivery slices** -> use `$tickets`. Send a small, coherent change directly to `$build`.
- **A slice is defined** -> use `$build`; apply `$tdd` inside it when an automated behavioral loop is valuable.
- **The task must pause, fork, or move to a fresh context** -> use `$handoff`.

## Operating rules

1. Run only the stages the work needs. A clear bug fix or one-slice feature may enter at `$build`, which can apply `$tdd` internally.
2. Distinguish decision work from delivery work. `$map` clears uncertainty; `$tickets` decomposes settled implementation.
3. Treat research and prototypes as loops, not milestones: question -> evidence -> decision update.
4. If implementation exposes an unresolved product or architecture decision, stop at a safe boundary, update the governing artifact, repair affected tickets, then resume.
5. Continue through safe, reversible stages when the user asked for an end-to-end result. Pause only for a material user-owned choice, a genuine blocker, or authority for an external state change.
6. Use parallel agents for independent lanes with disjoint ownership. Keep synthesis, integration, and final verification in the parent task.
7. Update an existing canonical artifact instead of creating a competing copy. Reference evidence by path or URL.

## Completion

Finish with one of these outcomes:

- a verified implementation with the checks and review evidence reported;
- a decision-complete artifact and the exact next gate;
- a handoff that names the pause or transfer reason, the blocker or `none`, and the first action for continuation.
