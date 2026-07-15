---
name: flow
description: Run or resume the standard five-phase workflow from a vague idea to reviewed, verified code. Use when the user wants Codex to own the whole process, continue from an existing brief, spec, ticket set, or implementation, or decide which core phase comes next.
---

# Flow

Use one simple sequence:

1. **Brainstorm** - `$shape` interviews the user and produces a confirmed brief.
2. **Spec** - `$spec` turns the brief into the canonical build contract.
3. **Tickets** - `$tickets` converts the spec into ready implementation issues.
4. **Build** - `$build` implements the tickets and uses `$tdd` when useful.
5. **Review** - `$build` performs spec and code review, fixes findings, and verifies the result.

`$flow` is the wrapper around these phases, not another phase.

## Procedure

1. Inspect the conversation, repository instructions, existing artifacts, current implementation, plan, and git state.
2. Resume from the first incomplete core phase. Never restart a phase whose trustworthy artifact already exists.
3. In the full workflow, route every ready spec through `$tickets`. A small change may produce a single ticket.
4. Work ready tickets with `$build`. Use `$tdd` inside the build when a stable automated behavior seam exists.
5. After implementation, require the review pass in `$build`. A green test run alone is not completion.
6. If review finds an implementation defect, return to Build. If it finds a missing or changed requirement, return to Shape or Spec, update affected tickets, then resume.
7. Continue through safe, reversible work when the user asked for an end-to-end result. Pause only for a material user-owned decision, a real blocker, or authority for an external mutation.

## Optional helpers

Use these only when the active phase needs them:

- `$research` for current external facts.
- `$prototype` for a decision that must be seen or run.
- `$map` for unusually large uncertainty that cannot fit one shaping pass.
- `$tdd` for a test-first loop inside the build phase.
- `$handoff` when work must pause or move to another task.

Helpers return their evidence to the active core phase. They do not add mandatory phases.

## Direct entry

A request that already includes a trustworthy spec, ticket, or implementation may enter at the corresponding phase. Preserve the same downstream rule: implementation is followed by review and verification.

## Completion

Finish only with a reviewed, verified implementation, or stop explicitly as blocked with the exact unresolved decision, dependency, or authority required. Report which phases were reused, completed, or revisited.
