# Requirements, sources of truth, and checks

## IDs and links

Use stable IDs: `OBJ-001` objective, `REQ-001` behavior, `NFR-001` quality requirement, `AC-001` acceptance criterion, `UX-001` journey/screen, `ADR-001` decision, `TASK-001` task, `TEST-001` check, `Q-001` question, `RISK-001` risk, `CHG-001` change.

Define each ID once, in a heading such as `## REQ-001 — Title` or the appropriate table. Later mentions are references, not new definitions. Do not renumber or reuse deleted IDs: mark them `retired` with a reason.

Required chain: `OBJ → REQ/NFR → AC → TASK → TEST → evidence`. Add UX and ADR only where relevant. A test may cover multiple AC, and a task may cover multiple requirements, but the links must be explicit. A spike without a product requirement references a Q or RISK and has an exit criterion.

## Sources of truth

| Information | Edit here |
|---|---|
| Audience, objectives, hypotheses | PRODUCT |
| Scope, priority, behavior, AC, NFR | REQUIREMENTS |
| UX, data, contracts, ADR | DESIGN or a linked active module |
| Tasks, test cases, results, release | DELIVERY |
| Gates, questions, baseline, change log | STATE |

The traceability table in REQUIREMENTS contains IDs and links, not copied prose. AGENTS describes the process, not duplicate product requirements. If code and approved requirements disagree, record a defect or CHG rather than rewriting the requirement to justify the code.

## Checks before G3 and G4

1. Every Must REQ/NFR has an OBJ, a reason, and AC with observable outcomes. Words such as “fast” or “easy” without a measure are gaps.
2. Every AC has a TASK and TEST. A planned TEST is enough for G3; G4 requires a result, environment, and evidence.
3. No tasks implement out-of-scope features or lack a requirement/Q/RISK. Dependencies exist and have no cycles; ready tasks do not depend on unresolved blockers.
4. UX and rules agree: for example, a deletion screen follows the retention policy. Document empty/error/offline states and permission denial where applicable.
5. NFR align with platforms, devices, storage, and budget limits. Offline behavior does not contradict a mandatory server action.
6. Games: victory, rewards, retry, and saves do not contradict one another; content has an owner and a solvability check.
7. Active modules are complete within the MVP scope. Inactive modules have an N/A reason. No unresolved placeholders remain in the scope being approved.
8. IDs are unique within the project, links resolve, and changes have undergone impact review. Exclude templates and examples from the working project's ID checks.
9. Statuses are honest: `planned` is not `passed`, a mockup is not an implementation, and AI self-assessment is not a user-test result.

Finding format: `severity: blocker/warning | ID | files | contradiction | recommended fix | owner`. A blocker prevents the relevant gate; a warning needs a recorded decision. This is a semantic review by a person/AI; the starter kit does not include an automated validator.

## Change management without bureaucracy

Record CHG in STATE: reason → affected IDs → impact on scope/time/data/tests → owner's decision. Update the source of truth, then links and dependent tasks; mark affected gates stale. Cosmetic edits with no behavior change need only a short Git history entry. Move requirements removed from the MVP to Later, retaining their IDs and reasons.
