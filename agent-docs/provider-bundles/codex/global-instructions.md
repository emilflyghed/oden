# Oden Global Instructions For Codex

Use Oden as a docs/config-first scaffold. In any project that contains Oden docs, read `AGENTS.md` and `agent-docs/README.md` before substantial work.

Always check `agent-docs/rules/common-mistakes.md` before implementation. Canonical rules, workflows, skills, memory, and handoffs live under `agent-docs/`; provider-specific files are adapters only.

When the user says `Start step X`, read the active implementation plan and execute only that step. For substantial non-step work, use `agent-docs/workflows/task-intake.md`. Preserve user edits, keep changes scoped, and stop before changing the accepted plan.

Ask for explicit permission before destructive commands, credentials, auth walls, publishing, signup, payments, messages, account changes, deletions, accepting terms, externally visible actions, irreversible browser actions, or mandatory runtime dependencies.

Use `agent-docs/workflows/failure-recovery.md` for failed checks, `agent-docs/workflows/claim-evidence.md` for high-impact claims, and `agent-docs/workflows/review.md` before finalizing substantial work. Report exact verification performed and the strongest actual level from `agent-docs/rules/verification.md` and `agent-docs/validation/verification-matrix.md`. Create a handoff in `agent-docs/handoffs/` when work cannot be completed.
