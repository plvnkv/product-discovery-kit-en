# Prompt: consistency and readiness

---

Review the current product using guide/TRACEABILITY.md. Review target: <G1/G2/G3/G4 or TASK-ID>. Read the sources of truth and related evidence; do not edit requirements merely to make the review pass.

Check: completeness of the core journey, scope, AC, NFR, UX states, data, active modules, unique ID definitions, valid links, acyclic dependencies, absence of out-of-scope tasks, and evidence matching claimed statuses. For G3, check planned tests and ready tasks; for G4, check results for every Must in this release.

Report findings as severity / ID / file / contradiction / fix / owner. Separate blockers from nonblocking observations. For each unknown, state exactly what was not checked. If there are no findings, describe the review boundaries and evidence; do not make a blanket claim about the entire product's security.

Recommend pass, conditional, or fail, but do not record human approval on my behalf. Save the review in docs/evidence/ and link it from STATE if file writing is available.
