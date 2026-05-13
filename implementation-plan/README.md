# Oden Phase 1 Implementation Plan

This directory is the Phase 1 output. It is a plan for building Oden in Phase 2, not the scaffold implementation itself.

Oden will be a docs/config scaffold consumed directly by agents. Its core must work without a runtime dependency. The design borrows state, checkpoint, interrupt, tool-routing, and verification ideas from LangGraph, but it does not depend on LangGraph in the core scaffold.

## How Future Agents Use This Plan

When the user says `Start step X`, the agent must:

1. Read this `README.md`.
2. Read `04-step-protocol.md`.
3. Read the matching file in `steps/`.
4. Execute only that step unless the step explicitly says another step is included.
5. Stop and ask the user when the step says confirmation is required.
6. Report exactly what changed and how it was verified.

Do not implement Phase 2 from memory. The step files are the source of truth.

## Phase 2 Step Index

| Step | File | Goal |
| --- | --- | --- |
| 1 | `steps/01-repo-foundation.md` | Create the scaffold file tree, source policy, and root entrypoints. |
| 2 | `steps/02-core-rules-memory.md` | Create canonical agent rules, memory, common mistakes, and verification docs. |
| 3 | `steps/03-workflow-protocol.md` | Create research, plan, implement, validate, checkpoint, and handoff workflows. |
| 4 | `steps/04-skill-system.md` | Create provider-neutral skills, templates, and skill-authoring rules. |
| 5 | `steps/05-provider-export-bundles.md` | Create exportable bundles for Codex, Claude Code, Cursor, Hermes/LM Studio, and ChatGPT. |
| 6 | `steps/06-browser-research-harness.md` | Integrate the guarded browser research/testing harness. |
| 7 | `steps/07-validation-suite.md` | Add validation checklists and structure checks for the docs/config scaffold. |
| 8 | `steps/08-examples-handoff.md` | Add examples, install guidance, and final handoff docs. |

## Required Reading Before Any Step

- `00-phase-boundaries.md`
- `01-reference-synthesis.md`
- `02-product-decisions.md`
- `03-target-architecture.md`
- `04-step-protocol.md`

## Non-Goals For Phase 2 Core

- Do not build a general agent runtime.
- Do not require LangGraph, LangChain, or any model provider SDK for the core scaffold.
- Do not assume a specific hosted LLM.
- Do not create a browser agent that can publish, sign up, enter credentials, make payments, or perform irreversible actions without explicit user permission.
- Do not hide state in provider-specific files only. Canonical rules and memory must live in Oden-owned docs.

