# Oden

Oden is a docs/config-first scaffold for agent-assisted software work.

It gives LLM agents a shared operating system made from markdown instructions: where to look, how to work, when to stop for permission, how to verify work, how to preserve state, and how to hand off unfinished tasks.

Oden is designed to be consumed directly by agents such as Codex, Claude Code, Cursor, ChatGPT, Hermes Agent, and local/open models through LM Studio. It does not require a runtime, model SDK, graph engine, package install, or hosted service.

## What It Does

Oden provides:

- A root agent entrypoint in `AGENTS.md`.
- Canonical agent rules under `agent-docs/rules/`.
- Workflow protocols for task intake, research, planning, implementation, validation, failure recovery, review, checkpoints, handoffs, claim/evidence tracking, and `Start step X` work.
- Provider-neutral skills for codebase location, code analysis, web research, browser research, and provider bundle maintenance.
- Durable memory files for decisions, open questions, and session notes.
- Exportable provider bundles for Codex, Claude Code, Cursor, Hermes/LM Studio, and ChatGPT.
- Guarded browser research/testing guidance with explicit permission gates.
- Validation checklists for scaffold structure, provider bundles, browser safety, and release readiness.
- Copyable examples for step execution, provider installation, and browser research.

## Strengths

- **Portable by default**: Oden is markdown and config. Agents can use it without installing dependencies.
- **Provider-neutral core**: canonical behavior lives in `agent-docs/`; provider bundles are adapters, not separate sources of truth.
- **Works across sessions**: checkpoints, handoffs, memory, and common mistakes make long-running work resumable.
- **Built for step-based execution**: large implementation plans can be split so a user can say `Start step 4` and the agent knows what to read, change, verify, and report.
- **Safety is explicit**: destructive operations, credentials, auth walls, publishing, payments, account changes, browser side effects, and mandatory dependency changes require user permission.
- **Browser use is constrained**: browser guidance is for public research, inspection, screenshots, and safe testing, not autonomous signup, publishing, purchasing, credential entry, or account management.
- **Verification is named honestly**: agents must report what was actually checked, distinguishing inspection, structure checks, provider checks, and behavior checks.
- **Common errors have a home**: avoidable mistakes are tracked in `agent-docs/rules/common-mistakes.md` so future agents know what to cross-check.

## Quick Start

For an agent working inside this repository:

```text
Read AGENTS.md and agent-docs/README.md before starting.
```

For a numbered implementation plan:

```text
Start step 3.
```

The agent should then read the plan index, the step protocol, the matching step file, relevant Oden docs, make only the scoped changes, run the listed verification, and report the actual verification level.

For provider setup, start with:

```text
agent-docs/provider-bundles/
```

Each provider bundle contains copyable instructions for that provider. Keep `AGENTS.md` and `agent-docs/` available as the canonical source.

## Project Structure

```text
.
  AGENTS.md
  README.md
  agent-docs/
    README.md
    rules/
    workflows/
    skills/
    memory/
    handoffs/
    provider-bundles/
    validation/
    browser/
    examples/
  implementation-plan/
  references/
```

Important paths:

- `AGENTS.md`: universal agent entrypoint.
- `agent-docs/README.md`: canonical scaffold map.
- `agent-docs/rules/`: stable behavior, safety, verification, code quality, browser safety, and common mistakes.
- `agent-docs/workflows/`: task intake, research, plan, implement, validate, failure recovery, review, checkpoint, handoff, claim/evidence, and `Start step X` protocols.
- `agent-docs/skills/`: provider-neutral skills.
- `agent-docs/provider-bundles/`: adapters for specific agent providers.
- `agent-docs/browser/`: guarded browser research/testing docs.
- `agent-docs/validation/`: static validation checklists.
- `agent-docs/examples/`: copyable usage examples.
- `implementation-plan/`: the Phase 1/Phase 2 build plan used to create this scaffold.
- `references/`: source reference material used during design.

## Provider Bundles

Oden currently includes provider adapters for:

- Codex
- Claude Code
- Cursor
- Hermes/LM Studio
- ChatGPT

Provider bundles are intentionally thin. They should point agents back to canonical Oden docs instead of duplicating behavior permanently.

Re-check current provider documentation before changing provider-specific file names, config locations, or feature claims.

## Browser Research

Browser guidance lives in `agent-docs/browser/` and `agent-docs/rules/browser-safety.md`.

Allowed by default when in scope:

- Public research.
- Reading public pages.
- Inspecting dynamic public pages.
- Capturing screenshots or page-state evidence.
- Trying Oden behavior when no irreversible or externally visible action occurs.

Requires explicit permission:

- Publishing, submitting, posting, or sending information.
- Signing up.
- Entering credentials or crossing auth walls.
- Making payments or purchases.
- Changing account settings.
- Deleting data.
- Accepting terms.
- Uploading files or downloading sensitive private data.
- Reusing browser profiles, cookies, or authenticated sessions.
- Any irreversible or externally visible action.

## Validation

Validation checklists live in `agent-docs/validation/`.

Use them to check:

- Scaffold structure and canonical links.
- Provider bundle coverage and permission preservation.
- Browser safety and evidence rules.
- Release readiness, including secrets, provenance, open questions, and handoff state.

Oden does not claim behavior was tested unless an executable helper, browser flow, provider install, or concrete example was actually run.

## Current Status

The local docs/config scaffold is ready to use.

Known limits:

- No provider installation has been tested inside the actual provider UIs.
- No executable browser harness is included.
- No runtime package, CLI, model SDK, or dependency file is included.
- No license file has been added yet.

See `agent-docs/handoffs/final-phase2-handoff.md` for the completed Phase 2 handoff and verification summary.
