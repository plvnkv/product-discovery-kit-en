# Example: “Light Turn” — a puzzle without a server

An educational example, not a launch-ready specification. All tests are planned and all gates pending. IDs are local to this example. UI copy is translated into English here for readability; the example's product language remains Ukrainian.

## PRODUCT

A short, calm puzzle for adults: rotate tiles to guide a beam to its target. First platform: Android; portrait only; Ukrainian language. Hypothesis OBJ-001: 4 of 5 new players complete the tutorial level without verbal help and independently start the second. Validate with a prototype; the result is currently unknown. If unsuccessful, revise the hint/controls before producing content.

## REQUIREMENTS

MVP: 3 authored levels, rotation, visible beam path, victory, restart, and local level unlocking. No timer, loss state, move limit, currency, ads, procedural generation, or accounts. If time runs short, reduce decoration; retain solvability checks.

REQ-001 — rotation and beam; Must, OBJ-001.
- AC-001: tapping a movable tile rotates it 90° clockwise and recalculates the path; tapping an immovable tile leaves the state unchanged.
- AC-002: the path ends at the boundary, an opaque tile, or a repeated (coordinates, incoming direction) pair; an infinite loop is impossible.

REQ-002 — victory and retry; Must, OBJ-001.
- AC-003: reaching the target transitions playing to won only once and unlocks the next level if one exists. On the last level, show “All levels completed” without navigating beyond the list.
- AC-004: retry restores initial orientations and playing state, and resets the current attempt's victory flag; already unlocked levels stay unlocked.

NFR-001 — progress persistence; Must, OBJ-001.
- AC-005: after successfully saving a victory and restarting, unlocked levels are available offline; an unfinished attempt starts over.
- AC-006: a write error does not cancel victory in the current session; show “Progress not saved” with a write retry option and do not claim a successful save.

## DESIGN and GAME

UX-001: level menu → board → victory → next/menu. Pause covers the board and ignores taps; resume restores the same in-process state. After process termination, an unfinished level resets. Content loading error: message and return to menu; an empty catalog disables starting. Sound is optional and unnecessary for solving. Tiles differ by shape, not only color.

Core loop: select level → rotate → see beam → light target → next puzzle. Board: 4×4; coordinates x,y = 0…3; directions N/E/S/W. One source, one target; no beam splitting. Types: empty (passes through), block (stops), mirror `/` or `\` (reflects), source, target. Mirrors have 4 orientations, with 0/180 and 90/270 equivalent. No randomness.

For `/`: E→N, N→E, W→S, S→W. For `\`: E→S, S→E, W→N, N→W. Direction means the beam's travel direction. The target absorbs the beam from any side. The path contains (coordinates, direction) states; at most 64 unique board states. This is an algorithmic bound, not a performance measurement.

Level format: id, schemaVersion=1, grid[4][4], sourceDirection, initialRotations, movableCells, knownSolution. First tutorial fixture: source at (0,1) facing E, movable `\` mirror at (1,1), target at (1,0), all other cells empty. One rotation changes the mirror to `/` and reaches the target. The other two levels still need to be created and validated (Q-001).

ADR-001 — proposed: pure beam logic separate from rendering; provide the UI with a segment list and won flag. Alternative: engine physics collisions, but these complicate reproducibility for a discrete grid. Select the stack after checking the creator's experience (Q-002). No backend: only the maximum unlocked level index, version=1; writing the same progress again is idempotent. No personal data/SDKs/payments.

## DELIVERY

| Task | Requirements / outcome | Dependencies | Status |
|---|---|---|---|
| TASK-001 | REQ-001: playable slice of one fixture with UI, algorithm, and pause | Q-002 | blocked |
| TASK-002 | REQ-002, NFR-001: victory, retry, menu, local persistence | TASK-001 | draft |
| TASK-003 | REQ-001, REQ-002: create and validate all 3 levels | TASK-002, Q-001 | blocked |

TASK-001: AC-001, AC-002. Steps: direction model → path calculation → board UI and taps → pause → fixture and loop checks. Boundaries: no animation, sound, or metaprogression. Done: TEST-001 passed, UX-001 manually checked, and review. Rollback before release: revert the slice code; there is no user data yet.

TEST-001: AC-001, AC-002 — check all reflections, immovable tile, boundary, block, and a closed loop with a specified fixture; complete the tutorial fixture on a device. Planned.
TEST-002: AC-003, AC-004 — deliver the victory event twice, retry, and finish the last level. Expect only one won transition per attempt and no nonexistent level. Planned.
TEST-003: AC-005, AC-006 — successful save/restart offline; separately test write failure with retry. Planned.
TEST-004: AC-001, AC-003 — each of the three levels has a valid schema, legal moves from initialRotations to knownSolution, and a reachable target; replay the solution using the game's algorithm. Planned.

| Requirement | Objective | AC | Design | Task | Test |
|---|---|---|---|---|---|
| REQ-001 | OBJ-001 | AC-001, AC-002 | UX-001, ADR-001 | TASK-001, TASK-003 | TEST-001, TEST-004 |
| REQ-002 | OBJ-001 | AC-003, AC-004 | UX-001 | TASK-002, TASK-003 | TEST-002, TEST-004 |
| NFR-001 | OBJ-001 | AC-005, AC-006 | ADR-001 | TASK-002 | TEST-003 |

## STATE

Baseline demo-v0.1. G0–G4 pending. Q-001: content for levels 2–3; owner: game creator; deadline: before TASK-003 is ready. Q-002: stack and target test device; owner: creator; deadline: before G2. Next step: choose prototype tools and test OBJ-001. Game active; other modules N/A for the reasons above. The absence of external analytics does not prevent manual observation.
