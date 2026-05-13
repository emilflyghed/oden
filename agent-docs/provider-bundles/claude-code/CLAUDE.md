# Oden For Claude Code

@AGENTS.md

## Claude Code Adapter

Read `agent-docs/README.md` before substantial work. Canonical Oden docs under `agent-docs/` take precedence over this adapter.

Always check `agent-docs/rules/common-mistakes.md` before implementation.

Use these Oden workflows when appropriate:

- Task intake: `agent-docs/workflows/task-intake.md`
- `/research`: map facts without implementing.
- `/plan`: create scoped, verifiable, resumable steps.
- `/implement`: execute the accepted plan.
- `/validate`: report exact checks and residual risk.
- Failure recovery: `agent-docs/workflows/failure-recovery.md`
- Review: `agent-docs/workflows/review.md`
- Claim/evidence: `agent-docs/workflows/claim-evidence.md`
- `/handoff`: prepare a resumable handoff.

Do not use provider-specific commands, skills, or subagents to bypass Oden's permission gates, browser safety rules, verification requirements, or canonical memory locations.

If this file is used outside a project that has `AGENTS.md`, remove the `@AGENTS.md` import and copy the root Oden entrypoint content into this file.
