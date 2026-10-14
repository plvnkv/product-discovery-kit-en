# Product Discovery Kit · English

Turn an idea for a mobile app or a small game into verifiable tasks for an AI coding agent. Version 1.0.

This kit contains instructions and Markdown templates. It does not generate code automatically or require a specific model, framework, or paid service. The product owner may also be the researcher, designer, and developer. Gates are short decision records, not separate meetings.

## Get started in 15 minutes

1. Create a separate product repository. Copy `templates/PRODUCT.md`, `REQUIREMENTS.md`, `DESIGN.md`, `DELIVERY.md`, and `STATE.md` into its `docs/` directory. These are all the required working documents.
2. Copy `templates/AGENTS.md` to the root. If AGENTS.md already exists, reconcile the rules manually rather than overwriting it. README and other templates must not overwrite existing files either.
3. Give the AI the [discovery prompt](prompts/01-discovery.md), [interview](guide/INTERVIEW.md), [stages](guide/GATES.md), and the five documents. Add 2–5 sentences about your idea.
4. Answer in small batches. The AI records answers in files, surfaces unknowns, and asks you to confirm material decisions. “I don't know” is a valid answer.
5. At G1, limit the MVP; at G2, check risks and design; at G3, approve tasks that are ready to execute. Give the agent the [implementation prompt](prompts/02-implementation.md).
6. After each task, run a [review](prompts/03-review.md), add evidence, and update STATE. Complete G4 before publishing.

Fifteen minutes is enough to start, not to complete discovery. Unclear mechanics may require a prototype or research first.

## Choose the right scope

| Mode | When to use it | What to maintain |
|---|---|---|
| Lite — default | One core journey, local data, a small team | Five documents, ADRs inside DESIGN, tasks inside DELIVERY |
| Extended | Sync, payments, roles, sensitive data, or complex content | The same documents plus only the activated modules |
| Reassess scale | Real-time multiplayer, moderated UGC, a complex economy | Investigate the risky subsystem separately; do not treat it as a simple game |

Include the game module for every game, but describe only the mechanics that exist. Modules can start as sections in DESIGN. When they grow, move them to `docs/modules/` and leave links instead of duplicate content.

## Kit map

- [Adaptive interview](guide/INTERVIEW.md) — questions, branches, pause and resume.
- [Stages and gates](guide/GATES.md) — what each decision enables.
- [Traceability and consistency](guide/TRACEABILITY.md) — IDs, sources of truth, changes.
- [Repository structure](guide/REPOSITORY.md).
- [PRODUCT](templates/PRODUCT.md), [REQUIREMENTS](templates/REQUIREMENTS.md), [DESIGN](templates/DESIGN.md), [DELIVERY](templates/DELIVERY.md), [STATE](templates/STATE.md).
- Modules: [game](templates/modules/GAME.md), [backend and sync](templates/modules/BACKEND.md), [data and privacy](templates/modules/DATA.md), [payments](templates/modules/MONETIZATION.md).
- Additional templates: [ADR](templates/ADR.md), [standalone task](templates/TASK.md), [product README](templates/PROJECT-README.md), [AGENTS](templates/AGENTS.md).
- End-to-end examples: [local app](examples/APP.md), [puzzle game](examples/GAME.md). These are fictional format examples, not test results.

## Conventions

`<fill in>` marks a template field. Before a gate, replace it with an answer, `N/A — reason`, or a `Q-###` question with an owner and deadline. Do not turn guesses into facts. Do not populate inactive modules just for completeness.

A documented MVP is the smallest complete path to value, not a list of every desirable feature. You can start without a backend, accounts, analytics SDK, or ads if the journey does not require them.

This kit defines a process. Verify SDK versions, pricing, platform support, and store requirements against current official sources when selecting an implementation. Do not treat a template as legal advice or a ready-to-use privacy policy.
