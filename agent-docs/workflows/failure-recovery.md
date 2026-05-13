# Failure Recovery Workflow

Use this workflow when a command, check, test, provider verification, browser observation, or expected file inspection fails.

This is the active recovery procedure. `agent-docs/rules/common-mistakes.md` is the durable lesson store for avoidable mistakes that future agents should not repeat.

## Recovery Sequence

1. Record the exact failed command, check, or observation.
2. Capture the relevant output, error text, missing file, or mismatch.
3. Classify the failure.
4. Decide whether fixing it is inside the current scope.
5. Retry only when the cause is understood and the retry is meaningfully different.
6. Stop and ask when recovery would change scope, architecture, dependencies, permissions, provider behavior, or runtime assumptions.
7. Update `common-mistakes.md` only when the failure reveals a durable avoidable lesson.

## Failure Classes

- `Command typo`: the command was malformed or used the wrong path.
- `Missing prerequisite`: required file, tool, dependency, permission, provider context, or service is unavailable.
- `Bad assumption`: the agent expected a structure, API, behavior, or file that is not present.
- `Implementation defect`: the current edits or existing behavior do not satisfy the requirement.
- `Environment limitation`: the local environment cannot run the check as intended.
- `Scope mismatch`: the required fix is outside the accepted task or step.
- `Permission gate`: the next action requires explicit user approval.

## Retry Rules

- Do not repeat the same command unchanged unless the environment changed.
- Do not try random fixes.
- Do not hide failed output.
- Do not downgrade the verification level to avoid a failure.
- Do not add dependencies, generated files, credentials, browser setup, or provider configuration to force a pass unless the user approved that scope.

## Recovery Note Template

```markdown
## Failure Recovery

- Failed check:
- Relevant output:
- Class:
- In scope: yes/no
- Recovery action:
- Retry command:
- Result:
- Residual risk:
- Common mistake update needed: yes/no
```

## When To Handoff

Create or update a handoff when:

- The failure remains unresolved.
- The next action is blocked on user input or permission.
- The context needed to resume is larger than a short final response.
- The failure changes the recommended next step.
