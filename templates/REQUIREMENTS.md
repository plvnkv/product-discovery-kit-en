# MVP and requirements

Baseline: <v0.1> · Owner: <name>

## Core journey

<Trigger → main action → visible value → completion/repeat>.

## Release boundaries

| Included in MVP | Why essential | Later / out-of-scope | Why deferred |
|---|---|---|---|
| <feature> | <value/constraint> | <feature> | <reason> |

Wave budget/time: <limit>. Scope-cutting order: <what to remove first>.
Must — essential for the core journey or a mandatory constraint. Should — only if capacity remains. Later — do not plan now. Release scope must be unambiguous; Should is not a hidden Must.

## REQ-001 — <behavior>

Objective: OBJ-001 · Priority: Must · Status: proposed · Source: <decision/research>.
Reason for Must: <what fails without this requirement>.
Actor/preconditions: <who and when>. Behavior: <observable action>.
Exceptions and boundaries: <empty/invalid input, repeat, offline>.

- AC-001: Given <state>, When <action>, Then <verifiable outcome>.
- AC-002: Given <error/boundary>, When <action>, Then <expected safe outcome>.

## NFR-001 — <quality requirement>

Objective: OBJ-001 · Priority: Must · Status: proposed.
Reason: <impact on the user>.
- AC-003: <metric, threshold, device, build, dataset, measurement method>.

Do not fill in every possible NFR. Choose what matters: performance, accessibility, persistence, security, size, battery, supported platforms.

## Traceability

| REQ/NFR | OBJ | AC | UX / ADR or N/A | TASK | TEST |
|---|---|---|---|---|---|
| REQ-001 | OBJ-001 | AC-001, AC-002 | <ID> | TASK-001 | TEST-001 |
| NFR-001 | OBJ-001 | AC-003 | <ID> | TASK-001 | TEST-002 |

Add relative links to other files; each ID has one definition. Keep test evidence in DELIVERY.
