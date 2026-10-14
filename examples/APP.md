# Example: “Three Tasks” — a local app

A small educational example of Lite documents. All decisions below are illustrative; research, implementation, and tests have not been performed. IDs belong only to this example. Sections can be moved into the corresponding five files. UI copy is translated into English here for readability; the example's product language remains Ukrainian.

## PRODUCT

Idea: an adult user selects up to three tasks to keep a short list of priorities. The title is provisional. First platform: Android; language: Ukrainian. Data stays on the device; no accounts. Budget: up to two weeks of one person's work; this is a planning constraint, not a readiness estimate.

OBJ-001: the user independently creates and completes their first task. Hypothesis: at least 4 of 5 initial test participants do this within 60 seconds without help. Method: observation using a prototype; if unsuccessful, revisit labels and the main action. This is a small qualitative test, not market validation.

## REQUIREMENTS

Journey: open → add a task → see it in the list → mark it complete.
MVP: local list of at most three entries, adding, toggling completion, deletion, and persistence. Later: dates, reminders, sync, statistics. No automatic midnight reset. Completed entries occupy a slot until deleted.

REQ-001 — adding; Must, OBJ-001. Without adding, the core journey cannot work.
- AC-001: with two entries, entering “Buy bread” and pressing “Add” creates a third incomplete entry and clears the input after a successful write.
- AC-002: with three entries, a fourth cannot be added; “Maximum 3 tasks” is shown and the list stays unchanged. Text empty after trimming is not added; length is limited to 80 characters under the counting rule in the UI contract.

REQ-002 — completion and deletion; Must, OBJ-001. Needed to complete and repeat the journey.
- AC-003: pressing a checkbox toggles that entry's completion without changing others. Pressing it again restores the state.
- AC-004: confirmed deletion removes only the selected entry; cancellation leaves the list unchanged.

NFR-001 — local list reliability; Must, OBJ-001.
- AC-005: after a successful change, forced closure, and relaunch, the list, order, and completion flags are restored without a network.
- AC-006: on an injected write error, the UI shows a message, does not confirm success, and preserves the previous state; entered text remains available for retry.

## DESIGN

UX-001: one screen, input, add button, list. Empty: “Add your first task”; loading: brief storage loading with input disabled; error: explanation and retry; offline: normal operation. Checkboxes have text labels; state is not conveyed by color alone. Delete using a button and confirmation. Portrait orientation; larger system text is checked manually.

UI contract: trim outer whitespace; limit to 80 Unicode code points after trimming; an emoji sequence may occupy several positions. The UI counter uses the same rule.

Data: Task(id: unique string, title: string, completed: boolean, position: integer). Schema v1, up to three entries. Deletion is local with no undo; data remains until the user deletes it or clears app data. No export, external SDKs, or data transfers; the app requests no permissions. OS backup needs an explicit decision before release (Q-002).

ADR-001 — proposed: UI → list logic → repository. Compared with direct writes from UI, a separate repository makes error testing possible. Backend rejected because sync is outside scope. Select storage and write atomicity after Q-001; the technical stack is not yet approved. Do not start implementation from this example without that decision.

## DELIVERY

| Task | Scope | Dependencies | Status |
|---|---|---|---|
| TASK-001 | Adding slice: UI, validation, local repository; AC-001, AC-002, AC-005, AC-006 | Q-001 | blocked |
| TASK-002 | Toggle and delete; AC-003, AC-004, regression for AC-005 | TASK-001 | draft |

TASK-001: inputs — REQ-001, NFR-001, UX-001, ADR-001. Steps: model and input limits → repository with error handling → form and list → checks. Dates and sync excluded. Done: TEST-001 and TEST-003 passed, review and evidence. Rollback: revert the code change before publication; schema v1 remains unchanged.

TEST-001: AC-001, AC-002 — automated validation checks and a device scenario: add a third entry; try a fourth, empty text, and over 80 code points. Expectations follow the AC. Status: planned.
TEST-002: AC-003, AC-004 — toggle twice; cancel deletion; confirm deletion. Check that other entries remain independent. Status: planned.
TEST-003: AC-005, AC-006 — save different states and restart offline; separately inject write failure and check the UI and old data. Status: planned.

| Requirement | Objective | AC | Design | Task | Test |
|---|---|---|---|---|---|
| REQ-001 | OBJ-001 | AC-001, AC-002 | UX-001, ADR-001 | TASK-001 | TEST-001 |
| REQ-002 | OBJ-001 | AC-003, AC-004 | UX-001 | TASK-002 | TEST-002 |
| NFR-001 | OBJ-001 | AC-005, AC-006 | ADR-001 | TASK-001, TASK-002 | TEST-003 |

## STATE

Baseline demo-v0.1; G0–G4 pending, no human approval. Q-001: stack, storage, and target device; owner: product creator; deadline: before G2; blocks TASK-001. Q-002: OS backup and an accurate user explanation; owner: creator; deadline: before G2. Next question: what skills and Android devices are available? Game/Backend/Monetization modules: N/A; the minimal data inventory is already in DESIGN. No test evidence exists yet.
