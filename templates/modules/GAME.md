# Game module

Requirements: <REQ-IDs>; architecture decisions: <ADR-IDs>. Source of truth for mechanics; AC remain in REQUIREMENTS.

## Core loop

<Trigger → action → feedback → reward → next goal>.
Controls: <touch/gesture/buttons>; orientation: <mode>; session length: <hypothesis>.
States: menu → playing → won/lost; pause/resume/retry/exit: <allowed transitions>.

| Mechanic / REQ | Rule | Input → outcome | Edge cases |
|---|---|---|---|
| <ID> | <unambiguous rule> | <example> | <repeat, boundaries, simultaneous events> |

Win/loss: <conditions>; one-time reward issuance: <rule>.
Randomness: <none, or seed, range, replay>.
Physics/timer: <rules or N/A>; pause: <what is paused>.

## Progression and content

MVP: <number of levels/modes>; unlock order: <rule>.
Difficulty: <how it increases and how we check it>; tutorial: <first skill>.
Content creator: <owner>; format: <schema>; solvability/correctness check: <method>.
Economy: <currencies, sources/sinks, or N/A>; balance: <parameter table/link>.
Save: <timing, state contents, version, corruption>; reset: <rule>.
Graphics/audio: <list, sources, licenses, budget>.

## Experience validation

Enjoyment hypothesis: <description>. Test: <audience, task, observations>.
Threshold for revisiting: <result>; technical checks: <TEST-IDs>.
Multiplayer/UGC: <N/A or separate scope investigation>.
