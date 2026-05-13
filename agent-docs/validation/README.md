# Validation

This directory holds validation checklists for the Oden scaffold.

Use these files before handing off, exporting provider bundles, or calling a step complete. Validation must state what was actually checked and must not claim tests or behavior checks that were not run.

## Checklists

- `scaffold-checklist.md`: canonical tree, links, rules, workflows, skills, memory, and handoffs.
- `provider-checklist.md`: provider adapters, copy instructions, canonical links, permission gates, and current-docs status.
- `browser-checklist.md`: browser permission policy, auth walls, evidence, and site skills.
- `release-checklist.md`: final readiness checks for secrets, generated clutter, license/provenance, open questions, and handoff state.
- `verification-matrix.md`: map task types to minimum practical verification and reporting expectations.

## Verification Levels

- `Inspected`: files were read manually.
- `Structure checked`: required files, links, headings, and terms were checked.
- `Provider checked`: provider bundle details were checked against current provider docs or local references.
- `Behavior checked`: an executable helper, browser workflow, or example was actually run.

Do not report `Behavior checked` for this docs/config scaffold unless an executable helper, browser flow, or concrete example was actually run.
