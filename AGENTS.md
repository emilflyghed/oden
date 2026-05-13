# Oden Agent Entrypoint

Oden is a docs/config-first scaffold for agent work. Its core behavior lives in markdown and configuration that agents can consume directly; it does not require a runtime, model SDK, or graph engine.

Before starting work, read `agent-docs/README.md`.

## Canonical Docs

The canonical Oden docs live under `agent-docs/`. Provider-specific files and exported bundles are adapters only; they must point back to the canonical docs instead of becoming separate sources of truth.

Common mistakes are tracked at `agent-docs/rules/common-mistakes.md`. This path is reserved and stable.

## Working From Plans

When an implementation plan exists and the user says `Start step X`, follow the matching step file. For this repository, the current implementation plan lives in `implementation-plan/`.

Do not combine steps unless the user explicitly asks. If a step requires confirmation, stop and ask before proceeding.

For substantial non-step work, use `agent-docs/workflows/task-intake.md` before choosing research, planning, implementation, validation, review, or handoff.

Use `agent-docs/workflows/failure-recovery.md` when checks fail. Use `agent-docs/workflows/claim-evidence.md` for high-impact claims, provider claims, external facts, architecture decisions, and failed-verification conclusions. Use `agent-docs/workflows/review.md` before finalizing substantial work.

## Permission Gates

Ask for explicit user permission before:

- Running destructive git or filesystem operations.
- Publishing, submitting, sending, deleting, or committing externally visible information.
- Signing up for accounts.
- Entering credentials or crossing auth walls.
- Making purchases or payments.
- Changing account settings.
- Performing browser actions with irreversible effects.
- Adding mandatory runtime dependencies or changing Oden from docs/config-first to runtime-first.

Browser use is allowed for guarded research and testing only when it does not cross one of these gates.

## Handoffs

If work cannot be completed in the current session, create a handoff in `agent-docs/handoffs/` once that directory exists. Include the current goal, files changed, commands run, decisions made, open questions, risks, and next recommended action.
