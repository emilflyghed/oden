# Oden Agent Docs

This directory is the canonical Oden scaffold. Agents should read this file first, then follow the relevant rule, workflow, skill, memory, provider, validation, or browser docs.

Canonical docs in `agent-docs/` take precedence over provider bundles. Provider bundles are adapters for specific tools and must point back here.

## Directory Map

- `rules/`: stable behavior, safety, verification, code quality, browser safety, and common mistakes.
- `workflows/`: task intake, research, planning, implementation, validation, failure recovery, review, checkpoint, handoff, claim/evidence, and `Start step X` workflows.
- `skills/`: provider-neutral task skills and skill authoring guidance.
- `memory/`: long-lived decisions, open questions, and session notes.
- `handoffs/`: resumable task summaries for future sessions.
- `provider-bundles/`: exportable instructions for specific agent providers.
- `validation/`: scaffold, provider, browser, release, and verification matrix checklists.
- `browser/`: guarded browser research/testing guidance.
- `examples/`: copyable examples for step execution, provider installation, and browser research.

## Current Build State

Steps 1 through 8 created the full Phase 2 scaffold: foundation, canonical rules, initial memory, workflows, provider-neutral skills, provider export bundles, guarded browser research/testing guidance, validation checklists, examples, and the final Phase 2 handoff. A later refinement pass added task intake, failure recovery, review, claim/evidence, and verification matrix guidance for weaker-model execution.
