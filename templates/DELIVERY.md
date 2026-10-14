# Implementation plan and checks

Baseline: <version> · Current wave: <name>.

## Sequence

1. Spike only for a critical unknown: question, timebox, success criterion, result, and decision to proceed/change/abandon. Research code does not automatically become production code.
2. First vertical slice: the smallest complete user journey.
3. Remaining Must items, then reliability and release checks. Add Should items only after an explicit scope decision.

| Task | Outcome | REQ/NFR or Q/RISK | Depends on | Status |
|---|---|---|---|---|
| TASK-001 | <outcome> | <IDs> | none | draft |

Statuses: draft → ready → in_progress → review → done; blocked with a reason; dropped with a decision. Dependencies form a DAG: no cycles. Size a task around one independently verifiable behavior; S/M/L estimates are relative, not promises of AI execution time.

## TASK-001 — <title>

Goal: <user outcome>. Requirements: <IDs>. Criteria: <AC-IDs>.
Dependencies: none. Change boundaries: <modules/contracts>. Excluded: <list>.
Input: <documents, mockups, data>. Steps: <3–6 concrete steps>.
Verification: <TEST-ID and command or manual scenario>.
Done when: AC met, checks passed, changes reviewed, evidence added, documents consistent.
Risk/rollback: <description>. Owner: <name>. Estimate: <S/M/L>.
Agent result: <changed files, summary, evidence, remaining issues>.

## TEST-001 — <check>

Covers: <AC-IDs>. Type: <unit/integration/device/manual/usability>.
Preconditions: <data, device, build>. Actions: <steps>. Expected: <outcome>.
Command: <verified command or N/A — manual check>.
Result: planned. Evidence: <path/link after execution>.
Date, executor, commit/build: <after execution>.

## TEST-002 — <NFR check>

Covers: <AC-IDs>. Method and environment: <description>. Threshold: <value>.
Result: planned. Evidence and date: <after measurement>.

Results: planned / passed / failed / blocked. Do not mark passed without running the check.

## Release and support

- Target build, platforms, and devices: <description>.
- Must items covered by evidence: <review link>.
- Known defects and accepted nonblocking risks: <IDs or none>.
- Assets and usage rights: <register>; store/SDK requirements: <official sources and date, if applicable>.
- OBJ metric: <how collected, who reviews it, when>; a manual test is possible without an analytics SDK.
- Distribution: <channel, signing, owner>; recovery/rollback: <actions and migration limits>.
- After launch: <feedback channel, triage, owner>.
