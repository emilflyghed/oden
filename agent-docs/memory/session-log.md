# Session Log

This file records short notes that help future agents continue work.

Add entries only when they preserve useful context for later sessions. Prefer handoffs for incomplete tasks.

## Entry Guidance

Use a session-log entry for:

- A durable discovery that does not belong in decisions or open questions.
- A short note explaining why a local convention exists.
- A completed setup step whose result helps future agents orient quickly.

Use a handoff instead when:

- Work is incomplete.
- A future agent needs exact next actions.
- There are known failures, partial edits, or verification gaps.

## Entries

### 2026-05-12: Step 2 Core Rules And Memory

- Created canonical provider-neutral rules under `agent-docs/rules/`.
- Seeded memory with locked product decisions and the provider-format verification open item.
- Kept the scaffold docs/config-first with no runtime dependencies.

### 2026-05-12: Step 5 Provider Export Bundles

- Created provider adapters for Codex, Claude Code, Cursor, Hermes/LM Studio, and ChatGPT.
- Checked current provider documentation before writing provider-specific file names and installation guidance.
- Kept canonical Oden behavior under `agent-docs/`; provider bundles are adapters only.

### 2026-05-12: Step 6 Browser Research Harness

- Added guarded browser research/testing docs under `agent-docs/browser/`.
- Kept browser capability docs/config-only; no executable browser harness code, browser launch, cloud setup, or dependency was added.
- Reinforced explicit permission gates for publishing, signup, credentials, payments, messages, account changes, deletion, uploads, accepting terms, and irreversible or externally visible actions.

### 2026-05-12: Step 7 Validation Suite

- Added validation checklists for scaffold structure, provider bundles, browser safety, and release readiness under `agent-docs/validation/`.
- Kept validation docs/config-only; no optional validation script or dependency was added.
- Documented that agents must distinguish structure checks from provider checks and behavior checks.

### 2026-05-12: Step 8 Examples And Handoff

- Added copyable examples for `Start step X`, provider installation, and safe browser research under `agent-docs/examples/`.
- Added the final Phase 2 handoff at `agent-docs/handoffs/final-phase2-handoff.md`.
- Completed the planned Phase 2 docs/config scaffold without adding a root public README, runtime dependency, provider credential flow, or executable browser harness.

### 2026-05-12: Reasoning And Execution Refinement Pack

- Added task intake, failure recovery, review, and claim/evidence workflows for weaker-model execution.
- Added a verification matrix and examples for task intake, failure recovery, and review.
- Added `M-003: Retrying Without Diagnosis` to common mistakes.
- Kept the refinement docs/config-only with no runtime, dependency, browser harness, or provider credential flow.
