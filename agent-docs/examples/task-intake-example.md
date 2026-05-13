# Task Intake Example

Use this example when the user gives a non-step request.

## User Prompt

```text
Add stronger guidance so weaker models recover better from failed checks.
```

## Agent Intake

```markdown
# Task Intake: Stronger Failure Guidance

## Goal

Add docs that help agents recover from failed checks without guessing.

## Non-Goals

- Do not add runtime code.
- Do not change provider-specific behavior as the source of truth.
- Do not claim behavior was tested.

## Known Inputs

- Existing verification workflow.
- Existing common mistakes file.
- User wants weaker models to improve.

## Likely Files Or Areas

- `agent-docs/workflows/`
- `agent-docs/rules/common-mistakes.md`
- `agent-docs/validation/`
- Provider bundle pointers if canonical docs change.

## Constraints

- Docs/config-first.
- Provider-neutral canonical behavior.
- No dependencies.

## Permission Gates

- Adding mandatory dependencies or runtime behavior requires permission.
- Weakening safety rules requires permission.

## Success Criteria

- Failure recovery has a clear active procedure.
- Common mistakes keeps only durable lessons.
- Validation commands confirm structure.

## Verification Target

`Structure checked` with file existence and targeted text searches.

## First Action

Read `agent-docs/workflows/validate.md`, `agent-docs/rules/verification.md`, and `agent-docs/rules/common-mistakes.md`.
```

## Expected Agent Behavior

The agent should use this intake to choose the planning or implementation workflow, then keep the work scoped to the listed files and constraints.
