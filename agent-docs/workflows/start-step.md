# Start Step Workflow

This workflow defines how agents respond when the user says `Start step X`.

## While Building Oden

In this repository, while following the Phase 2 implementation plan:

1. Read `implementation-plan/README.md`.
2. Read `implementation-plan/04-step-protocol.md`.
3. Read `implementation-plan/steps/XX-*.md`.
4. Read `AGENTS.md`, `agent-docs/README.md`, and relevant rules.
5. Inspect the current workspace before editing.
6. Confirm the step scope in a short progress update.
7. Execute only that step.
8. Run the step's verification.
9. Stop with changed files, verification results, verification level, and open questions.

Do not combine steps unless the user explicitly asks.

## After Oden Is Installed In Another Project

When an Oden-adopting project has its own implementation plan:

1. Read the project's `AGENTS.md`.
2. Read `agent-docs/README.md`.
3. Read `agent-docs/rules/common-mistakes.md`.
4. Read the relevant implementation plan index.
5. Read the requested step file.
6. Follow that step's scope, stop points, and verification.
7. Create a handoff if the step cannot be completed.

If no implementation plan exists, ask the user whether to research, plan, or implement directly.

## Required Stop Points

Stop and ask before:

- Changing the step sequence.
- Skipping required verification.
- Adding dependencies or runtime behavior not called for by the step.
- Moving canonical Oden files.
- Making provider-specific instructions canonical.
- Crossing permission gates from `agent-docs/rules/safety-permissions.md` or `agent-docs/rules/browser-safety.md`.

## Final Response Shape

```markdown
Step X complete.

Changed:
- Path and short purpose.

Verification:
- Command or check: result.

Verification level:
- Exact level reached.

Open questions:
- Any remaining issue, or "None".
```

