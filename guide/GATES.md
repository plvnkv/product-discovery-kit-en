# Stages and decision gates

A gate checks whether there is enough information for the next step. One owner can approve everything. Chat confirmation is acceptable: record the date, author, version, and link or precise substance in STATE. AI may recommend a decision, but cannot invent approval.

| Stage / gate | Input | Passing criteria and evidence | Enables |
|---|---|---|---|
| Idea / G0 Value | Initial idea, constraints | Audience, value, riskiest hypothesis, and validation method defined; PRODUCT | Detail the MVP; conduct research |
| Boundaries / G1 MVP | PRODUCT, core journey | Must items have reasons and verifiable AC; exclusions, budget, and scope-cutting order exist; REQUIREMENTS | Design the bounded MVP |
| Decisions / G2 Feasibility | MVP, UX, modules | States, data, contracts, and critical NFR defined; architecture selected; critical risks tested or scope revised; DESIGN and spike evidence | Plan implementation |
| Handoff / G3 Ready | Consistent documents | No blocking Qs for the current wave; tasks have dependencies, AC, and checks; agent rules and traceability review ready | Execute only approved ready tasks |
| Release / G4 Release | Implementation and evidence | All Must items for the current release pass checks on target devices; no critical defects; release, support, and rollback defined | Hand off the build for release; external publication requires appropriate authorization |

Gate statuses: `pending`, `pass`, `conditional`, `fail`, `stale`.

- `conditional`: explicitly list nonblocking risks, owner, deadline, and permitted work. Unknown access control, data loss, or a core-journey criterion cannot be waved through conditionally.
- `fail`: fix a specific gap, test a hypothesis, reduce scope, or stop pursuing the idea. Repeat only the relevant gate.
- `stale`: a change invalidated a previous approval. Reassess dependent decisions.

For Lite, G0–G2 may be approved in one message after reviewing the relevant sections. Do not create three separate approval documents. G3 may cover the first wave: unprepared later tasks remain blocked. G4 evaluates Must items for the entire release.

## Minimal record

`G3 | pass | baseline v0.2 | owner: Name | date: YYYY-MM-DD | scope: TASK-001…003 | evidence: DELIVERY + review | conditions: none`

## Revisit after changes

Audience or value change → G0 and dependent gates. Added feature or platform → G1. Storage, sync, or payment change → G2. AC or task dependency change → G3. Code changes after release checks → relevant G4 rechecks. Unaffected work may continue.
