---
name: spec
description: Turn a confirmed brief and settled product decisions into the canonical implementation-ready specification. Use after brainstorming is complete and before creating implementation tickets.
---

# Spec

Synthesize existing decisions. Do not restart discovery or inflate the document with imagined requirements.

## Procedure

1. Read the governing brief, map, research, prototype verdicts, domain documents, relevant ADRs, repository instructions, and current implementation. Record the source revision when drift would matter.
2. Resolve contradictions among sources. If a missing decision materially changes scope, behavior, data, security, or architecture, return to `$shape`; use `$research` or `$prototype` there only when evidence is needed.
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
4. Make every requirement observable and verifiable. Give each behavioral requirement a confirmed source decision or an explicitly labeled delegated assumption; remove unsupported behavior instead of silently choosing it. Prefer concise scenarios and acceptance conditions over repetitive user-story prose.
5. Name stable modules, interfaces, and contracts when they guide implementation. Avoid brittle line-number recipes or speculative code snippets. Include a prototype-derived snippet only when it encodes a decision more precisely than prose.
6. Cross-check the spec against every confirmed decision and success signal. Mark assumptions explicitly, link evidence rather than duplicating it, and verify that no requirement or edge-case rule was invented during synthesis.
7. Set status to `ready` only when implementation can proceed without inventing product behavior. Otherwise keep it `draft` and identify the exact routing step for each blocker.

Use the lifecycle `draft` -> `ready` -> `partially-implemented` -> `implemented`. Set `partially-implemented` only when some in-scope requirements have verified delivery evidence, and `implemented` only when every in-scope requirement is verified. Link that evidence instead of rewriting the implementation into the spec.

Keep the spec local by default. Publish or label an external tracker item only when the user explicitly requests it.

## Next gate

Use `$tickets` next. A small spec may become one ticket; larger specs become a dependency-aware set.
