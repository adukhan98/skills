---
name: shape
description: Turn a fuzzy product, feature, system, or workflow idea into a decision-complete brief. Use when the user wants to stress-test an idea, clarify what to build before a spec, resolve design branches, or be interviewed one decision at a time.
---

# Shape

Produce a brief that later stages can trust. Separate discoverable facts from user-owned decisions.

## Procedure

1. Inspect repository instructions, existing briefs/specs, domain documents, relevant code, and current behavior before asking questions. Resolve local facts directly.
2. Create or update the project's existing discovery artifact. If no convention exists, use `docs/briefs/<slug>.md` with these sections:
   - Outcome
   - Users and problem
   - Success signals
   - Constraints
   - Decisions
   - Assumptions
   - Risks
   - Open questions
   - Out of scope
   - Evidence
3. Build a prerequisite-ordered decision tree. Ask exactly one material decision per turn. Give a recommended answer first, then its main trade-off and concise alternatives.
4. Treat explicit delegation such as "use your judgment" as authority to choose routine, reversible details. Record the assumption instead of asking.
5. Update the brief after each resolved branch. Mark entries as confirmed, assumed, deferred, or rejected.
6. Route factual uncertainty to `$research` and experiential UI, interaction, state, or logic uncertainty to `$prototype`. Use `$map` when the unresolved tree is too large for one focused task.
7. Sharpen overloaded domain terms. Update an existing glossary when one exists; create one only after multiple durable terms have been resolved.
8. Record an ADR only when the choice is hard to reverse, surprising without context, and the result of a real trade-off.

## Exit gate

Finish shaping when the outcome, users, success signals, scope, core behavior, constraints, major risks, and material assumptions are explicit and no open question blocks a spec or prototype.

When the user is actively deciding, show the compact brief and ask for one final confirmation. When the user explicitly delegated the decisions or requested end-to-end execution, proceed and label delegated assumptions clearly.
