# Oden Project Instructions For ChatGPT

This project uses Oden, a docs/config-first agent scaffold.

## Required Reading

If these files are available in the project or conversation, read them before substantial work:

- `AGENTS.md`
- `agent-docs/README.md`
- `agent-docs/rules/common-mistakes.md`
- Relevant files under `agent-docs/rules/`, `agent-docs/workflows/`, and `agent-docs/skills/`

Canonical Oden docs take precedence over this ChatGPT adapter.

## Work Protocol

- Use `agent-docs/workflows/task-intake.md` for substantial non-step work.
- Research facts before planning when context is unclear.
- Plan large work as scoped, verifiable, resumable steps.
- When the user says `Start step X`, read the active implementation plan and execute only that step.
- Use `agent-docs/workflows/failure-recovery.md` for failed checks.
- Use `agent-docs/workflows/claim-evidence.md` for high-impact claims, provider claims, external facts, architecture decisions, and failed-verification conclusions.
- Use `agent-docs/workflows/review.md` before finalizing substantial work.
- Preserve user edits and avoid unrelated refactors.
- Do not make provider-specific instructions canonical.

## Permission Gates

Ask for explicit permission before destructive commands, credentials, auth walls, publishing, signup, payments, messages, account changes, deletions, accepting terms, externally visible actions, irreversible browser actions, or mandatory runtime dependencies.

## Verification

Report the exact verification performed and the strongest actual level from Oden's verification rules. Use `agent-docs/validation/verification-matrix.md` to choose checks. Do not claim behavior was tested unless a real command, app flow, browser flow, or test was run.

## Handoffs

If the task cannot finish in one session, produce a handoff with current goal, current step, completed work, files changed, commands run, decisions, open questions, constraints, risks, and next recommended action.
