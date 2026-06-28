---
name: goalstorm
description: Use when the user asks Codex to create or track a goal, split implementation work into independent pieces, spawn parallel agents or subagents, dispatch concurrent coding/research work, synthesize agent results, or explicitly says phrases like "write yourself a new goal", "spawn agents in parallel", "give each agent its own /goal", "parallelize this implementation", or "as many agents as needed".
---

# Goalstorm

## Delegation Rules

- Create or state one outcome goal before delegation. If a goal tool exists and no active goal conflicts, create the goal with that tool.
- Do not delegate atomic tasks.
- Do not delegate code edits with overlapping write scopes.
- Parent agent owns final integration unless integration itself is assigned as a separate non-overlapping task.
- If subagent tools are not exposed, search once for multi-agent or subagent tools; if unavailable, continue solo and say so.

## Procedure

1. Inspect the target files, issue, artifact, or repo inventory before assigning agent ownership.
2. Split work by ownership: modules, files, feature slices, tests, docs, UI, backend, data, migration, or verification.
3. Spawn all independent agents in the same round.
4. While agents run, work only on parent-owned or non-overlapping tasks.
5. Wait only when an agent result blocks the next parent step.
6. For each returned agent: inspect changed files or evidence, integrate accepted work, resolve conflicts, then close the agent.
7. Run verification for the combined result. Report any verification that could not run.

## Agent Prompt Template

```text
/goal: <agent-owned outcome>

Main objective: <overall user request>
Ownership: <files, modules, or responsibility>
Concurrency: Other agents may be editing different areas. Do not revert or overwrite unrelated changes.

Task:
<bounded task instructions>

Deliverable:
- Changed files, if any
- Tests or checks run
- Integration notes
- Remaining risks
```

## Agent Count

- 0 agents: atomic task or no subagent tool after one search.
- 1 agent: one background track can run while the parent handles another track.
- 2-4 agents: independent implementation, investigation, docs, tests, or verification tracks.
- 5+ agents: only when each agent has a disjoint ownership scope and the parent has capacity to integrate all results.

## Final Response

Include:

- Goal
- Agent split used, or why none was used
- Integrated outcome
- Verification run
