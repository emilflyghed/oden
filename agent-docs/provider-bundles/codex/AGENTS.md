# Oden For Codex

Oden is a docs/config-first scaffold for agent work. Before starting work, read `agent-docs/README.md`.

## Canonical Docs

Canonical Oden behavior lives in `agent-docs/`.

Always check:

- `agent-docs/rules/common-mistakes.md`
- `agent-docs/rules/`
- `agent-docs/workflows/`
- `agent-docs/skills/`
- `agent-docs/memory/`

Provider-specific files are adapters and must not become the source of truth.

## Step Work

When the user says `Start step X`, read the active implementation plan index and matching step file. Execute only that step unless the user explicitly asks to combine steps.

For substantial non-step work, use `agent-docs/workflows/task-intake.md`. Use `agent-docs/workflows/failure-recovery.md` for failed checks, `agent-docs/workflows/claim-evidence.md` for high-impact claims, and `agent-docs/workflows/review.md` before finalizing substantial work.

## Permission Gates

Ask for explicit permission before destructive filesystem or git operations, credentials, auth-wall handling, publishing, submissions, messages, signup, payments, account changes, deletions, accepting terms, externally visible actions, irreversible browser actions, or adding mandatory runtime dependencies.

## Verification

Report the strongest actual verification level from `agent-docs/rules/verification.md` and use `agent-docs/validation/verification-matrix.md` to choose checks. Do not claim behavior was tested unless a command, browser flow, app flow, or test actually ran.

## Handoffs

If work cannot finish in the current session, create a handoff in `agent-docs/handoffs/` with goal, files changed, commands run, decisions, open questions, risks, and next action.
