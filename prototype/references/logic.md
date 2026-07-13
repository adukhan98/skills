# Logic prototype

Use a small interactive harness when the uncertainty concerns state transitions, rules, data shape, or an interface.

1. Put the decision-bearing logic behind the smallest natural interface: a reducer, explicit state machine, pure function set, or state-owning module.
2. Keep I/O in a thin disposable shell. Dispatch an action through the logic interface, replace the current state, and render again.
3. Show the complete relevant state and available actions after every step. Keep the frame small enough to understand at a glance.
4. Include the edge cases most likely to disprove the proposed model. Avoid speculative capabilities.
5. Use the host project's language and runner. If none exists, choose the lowest-dependency local option and document the command.
6. Preserve only validated interfaces, state shapes, invariants, and examples as decisions. Treat the harness and unverified implementation as disposable.
