---
name: spec
description: Synthesize settled product and technical decisions into an implementation-ready specification. Use when a brief, conversation, decision map, research note, or prototype verdict is mature enough to become the canonical description of what to build.
---

# Spec

Synthesize existing decisions. Do not restart discovery or inflate the document with imagined requirements.

## Procedure

1. Read the governing brief, map, research, prototype verdicts, domain documents, relevant ADRs, repository instructions, and current implementation. Record the source revision when drift would matter.
2. Resolve contradictions among sources. If a missing decision materially changes scope, behavior, data, security, or architecture, route it to `$shape`, `$research`, or `$prototype` instead of inventing an answer.
3. Use the project's spec convention. Otherwise write `docs/specs/YYYY-MM-DD-<slug>.md` with:
   - Status and source artifacts
   - Outcome and success signals
   - Problem and users
   - Scenarios and user flow
   - Numbered behavioral requirements
   - Technical design and stable interfaces
   - Data, API, migration, and rollout decisions when applicable
   - Verification seams and acceptance evidence
   - Security, privacy, accessibility, performance, and observability constraints when applicable
   - Risks and edge cases
   - Dependencies
   - Out of scope
   - Open decisions
4. Make every requirement observable and verifiable. Prefer concise scenarios and acceptance conditions over repetitive user-story prose.
5. Name stable modules, interfaces, and contracts when they guide implementation. Avoid brittle line-number recipes or speculative code snippets. Include a prototype-derived snippet only when it encodes a decision more precisely than prose.
6. Cross-check the spec against every confirmed decision and success signal. Mark assumptions explicitly and link evidence rather than duplicating it.
7. Set status to `ready` only when implementation can proceed without inventing product behavior. Otherwise keep it `draft` and identify the exact routing step for each blocker.

Use the lifecycle `draft` -> `ready` -> `partially-implemented` -> `implemented`. Set `partially-implemented` only when some in-scope requirements have verified delivery evidence, and `implemented` only when every in-scope requirement is verified. Link that evidence instead of rewriting the implementation into the spec.

Keep the spec local by default. Publish or label an external tracker item only when the user explicitly requests it.

## Next gate

Use `$build` for one coherent slice. Use `$tickets` when the spec requires multiple bounded slices or dependency-aware execution.
