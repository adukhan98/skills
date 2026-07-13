---
name: map
description: Chart a large, foggy effort as a dependency-aware decision map and advance its frontier. Use when the destination is known but the route spans multiple tasks, important questions cannot all be stated yet, or the user needs a durable map of research, prototype, and decision work before specification.
---

# Map

Map uncertainty, not implementation. A map is unnecessary when the route is already clear enough for a spec or one build task.

## Artifact

Use the project's existing planning convention. Otherwise create `docs/maps/<slug>.md` with:

- **Destination** - the observable end state this map must make reachable.
- **Scope boundaries** - in scope and out of scope.
- **Decisions** - resolved questions with one-line answers and evidence links.
- **Frontier** - precise, open questions whose blockers are resolved.
- **Blocked** - precise questions waiting on named decisions.
- **Fog** - in-scope areas that cannot yet be phrased as precise questions.
- **Artifacts** - linked research, prototypes, briefs, and handoffs.
- **Next gate** - the condition for moving to `$spec` or `$build`.

Give each question a type (`decision`, `research`, `prototype`, or `task`), status (`open`, `in-progress`, `awaiting-review`, `resolved`, or `out-of-scope`), blockers, evidence target, and resolution condition. Never put secrets in the map.

## Chart mode

1. Define the destination and scope. Use `$shape` first if either is unclear.
2. Explore breadth-first. Put a question on the frontier only when it can be stated precisely now; leave coarse uncertainty in Fog.
3. Add true dependency edges. The frontier is every open question whose blockers are resolved.
4. Stop charting when the current frontier and fog are faithfully represented. Do not invent distant tickets to make the map look complete.

## Advance mode

1. Select the highest-leverage frontier question, or the question the user named, and mark it `in-progress`.
2. Resolve it with `$shape`, `$research`, `$prototype`, or a bounded prerequisite task.
3. Mark it `awaiting-review` when an artifact exists but still needs the user or parent task to judge it. After the evidence is accepted, record the answer once, mark it `resolved`, remove it from the frontier, and update affected blockers, scope, and fog.
4. Promote newly precise fog to the frontier. Move mis-scoped work to Out of scope.
5. Run independent frontier investigations in parallel only when ownership and evidence are disjoint. Integrate every result into the map before it influences downstream work.

## Exit gate

Move to `$spec` when no unresolved decision blocks a complete statement of behavior. Publish or mutate external tracker issues only when the user explicitly requests it; the local map remains the default source of truth.
