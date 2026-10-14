# Experience and technical decisions

Version: <v0.1> · Related requirements: <IDs>

## UX-001 — <core journey>

Preconditions: <state>. Flow: <screens and transitions>. Completion: <outcome>.

| Screen | Action / navigation | Empty / loading / error / offline | Accessibility |
|---|---|---|---|
| <name> | <actions, back, cancel> | <behavior or N/A with reason> | <focus, labels, text, contrast> |

Backgrounding/resume/restart: <what the user sees>.
Permissions and denial: <behavior or N/A>.
Visual direction: <mood, colors, typography, spacing>; references/mockups: <links>.
Sound/haptics/animation: <rules, disabling, or N/A>.

## Components and data

Diagram: <UI → application logic → storage; external systems only if needed>.

| Component | Responsibility | Input / output | Errors / dependencies |
|---|---|---|---|
| <component> | <one role> | <contract> | <behavior> |

| Entity | Fields, types, constraints | Storage location | Lifecycle / deletion |
|---|---|---|---|
| <entity> | <id, fields, nullability> | <location> | <retention, migration, recovery> |

Local save format / schema version: <description>.
Secrets / trust boundaries: <what must not be stored in the client, or N/A>.
Write errors, corrupted data, schema upgrades: <rules without silent data loss>.

## ADR-001 — <key choice>

Status: proposed · Date: <date> · Requirements: <IDs>.
Context: <constraints driving the choice>.
Options: <2–3 options, cost, complexity, maintenance>.
Decision: <choice and reason>; consequences: <trade-offs>.
Revisit if: <trigger>. Risk validation: <spike/evidence>.
Current external sources: <URL + verification date, or N/A>.

## Active modules

| Module | Active / N/A | Reason | Link |
|---|---|---|---|
| Game | <status> | <reason> | <path> |
| Backend | <status> | <reason> | <path> |
| Data/privacy | <status> | <reason> | <path> |
| Monetization | <status> | <reason> | <path> |
