---
name: tdd
description: Implement behavior test-first with a red-green-refactor loop at a stable observable seam. Use when the user requests TDD, test-first development, a regression test before a fix, or a build task selects an automated behavioral feedback loop.
---

# TDD

Work one coherent behavior slice at a time.

## Loop

1. Read repository instructions, the governing acceptance criterion, relevant design records, existing tests, and the project's real test commands.
2. Select the smallest behavior and a stable observable seam. Infer an existing seam when it is clear; ask only when creating or choosing the seam materially changes the public contract or architecture.
3. Run the nearest existing test command to establish the local baseline. Record unrelated pre-existing failures.
4. **Red:** add the smallest behavior-focused test and run it. Confirm it fails for the intended missing behavior, not syntax, fixture, environment, or unrelated failure. If it passes, prove the gap with a different test or establish that the behavior already exists before changing production code.
5. **Green:** make the smallest coherent production change that passes the new test. Run the exact test and nearest related suite.
6. **Refactor:** improve names, duplication, and local design while the tests stay green. Do not add new behavior during refactoring.
7. Repeat for the next acceptance slice. Run broader repository-prescribed verification at integration points and completion.

## Test rules

- Test observable behavior through stable interfaces, not private call order.
- Use expected values independent from the implementation.
- Mock system boundaries such as external APIs, time, randomness, or costly infrastructure. Prefer real in-process collaborators and a test database when practical.
- Keep mocks domain-shaped; avoid generic conditional fetch mocks.
- A test may contain multiple assertions when they describe one observable outcome.
- For a bug, turn the real minimized reproduction into the regression test when a valuable seam exists.
- When automation would be low-value or impossible, state why and use explicit alternative evidence such as browser verification, a migration dry run, generated-output comparison, or a deterministic smoke harness.

## Completion

Report the red failure, green pass, refactoring checks, broader verification, skipped checks, and any pre-existing failures. Do not claim TDD when the test was written after the production change.

When TDD is part of delivery, return the diff and evidence to `$build` for user-surface verification, independent review, artifact updates, and final completion. A green TDD loop alone is not a completed build.
