---
name: tickets
description: Decompose a ready specification or settled plan into dependency-aware vertical delivery slices. Use when implementation spans multiple bounded tasks, needs a parallelizable frontier, requires tracker-ready issues, or must be split into fresh-context work without losing acceptance coverage.
---

# Tickets

Create delivery tickets only after material product decisions are settled. Use `$map` for uncertainty and send a single coherent change directly to `$build`.

## Procedure

1. Read the authoritative spec or plan, its evidence, repository instructions, current architecture, and relevant ADRs.
2. Give each numbered requirement at least one delivery owner. Separate requirements already delivered or explicitly out of scope.
3. Slice the work into tracer bullets: each ticket delivers a narrow, complete, demonstrable behavior across every required layer and fits one bounded agent task.
4. Add a preparatory refactor only when evidence shows it unblocks delivery. For a wide mechanical migration that cannot land as a vertical slice, use expand -> migrate in safe batches -> contract.
5. Add only true blocking edges. Keep independent work unblocked; parallelize frontier tickets only when file ownership, state changes, and integration risk are disjoint.
6. Validate that the dependency graph is acyclic and topologically ordered.

## Local artifact

Follow the project's issue convention. Otherwise create `docs/tickets/<feature>/` containing:

- `INDEX.md` - source spec, requirement coverage, dependency graph, current frontier, and integration notes.
- One file per ticket, numbered in dependency order: `<NN>-<slug>.md`.

Use these statuses: `draft` -> `ready` -> `in-progress` -> `done`. Use `blocked` when a newly discovered dependency or decision prevents work. Record completion evidence before setting `done`. After every status or dependency change, recompute the frontier in `INDEX.md`; the frontier contains only `ready` tickets whose blockers are `done`.

Use this ticket contract:

```markdown
# <NN> - <Title>

**Status:** ready
**Source:** <spec path and requirement IDs>
**Outcome:** <observable behavior this slice delivers>
**Blocked by:** <ticket titles or None>

## Scope
<what is included and excluded>

## Acceptance criteria
- [ ] <observable criterion>

## Verification
<commands, browser checks, migration checks, or other evidence>

## Current-revision hints
<stable modules, symbols, or paths to re-verify before editing>
```

## Quality gate

Before finishing, verify:

- every in-scope requirement maps to at least one ticket;
- no acceptance behavior is duplicated or orphaned;
- every ticket is independently verifiable;
- blockers are necessary and cycle-free;
- at least one frontier ticket can start without inventing product behavior;
- integration, migration, rollout, and cleanup work is owned where required.

Create local tickets without an approval round when the user asked for decomposition. Publish to GitHub, Linear, or another external tracker only with explicit authorization; create blockers first so later relationships use real identifiers.

Use `$build` on one frontier ticket per agent task. Integrate and verify independent tickets before expanding the frontier. Update the ticket status and `INDEX.md` frontier after every completed or blocked build.
