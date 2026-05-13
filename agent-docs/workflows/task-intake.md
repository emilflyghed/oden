# Task Intake Workflow

Use task intake before substantial work when the user has not selected a numbered implementation step.

If the user says `Start step X`, use `agent-docs/workflows/start-step.md` instead.

## Purpose

Task intake converts a loose request into a small working contract. It helps weaker models avoid guessing, skipping constraints, or starting implementation before the goal is clear.

## Intake Fields

```markdown
# Task Intake: Short Topic

## Goal

What the user wants done.

## Non-Goals

What should not be changed or decided.

## Known Inputs

- User-provided paths, files, requirements, errors, or examples.

## Likely Files Or Areas

- Files, directories, docs, provider bundles, or external sources likely involved.

## Constraints

- Scope limits, style requirements, provider limits, docs/config-first boundary, or compatibility requirements.

## Permission Gates

- Destructive actions, credentials, auth walls, publishing, payments, browser side effects, dependency changes, or other stop points.

## Success Criteria

- Observable conditions that mean the task is done.

## Verification Target

- Expected verification level and likely commands or inspections.

## First Action

The next non-destructive action, usually reading or searching files.
```

## Procedure

1. Read `AGENTS.md`, `agent-docs/README.md`, and `agent-docs/rules/common-mistakes.md`.
2. Fill the intake fields from the user request and local files.
3. Explore before asking when the missing detail is discoverable.
4. Ask only for product intent, permission, or high-impact ambiguity that cannot be resolved from local context.
5. Choose the matching workflow: research, plan, implement, validate, review, browser research, or handoff.
6. Keep the intake short. It is a working contract, not a diary.

## Stop Conditions

Stop and ask before:

- Treating an unclear request as permission for broad implementation.
- Changing the docs/config-first architecture.
- Adding dependencies, runtime behavior, provider credentials, or browser tooling.
- Crossing any gate in `agent-docs/rules/safety-permissions.md` or `agent-docs/rules/browser-safety.md`.
