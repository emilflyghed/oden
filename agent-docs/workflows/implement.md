# Implement Workflow

Implementation follows the accepted plan. It must stay scoped, verifiable, and reversible where possible.

## Before Editing

1. Read `AGENTS.md`.
2. Read `agent-docs/README.md`.
3. Read `agent-docs/rules/common-mistakes.md`.
4. Read the active plan or step file.
5. Inspect the current workspace and relevant files.
6. Confirm the current step scope in a short update.

## Procedure

1. Make only the changes described by the current step.
2. Keep edits small and aligned with existing structure.
3. Preserve user changes and unrelated work.
4. Do not combine future steps unless the user explicitly asks.
5. If the implementation reveals a plan problem, stop and record the issue instead of silently changing architecture.
6. Run the verification required by the step.
7. Report changed files, checks run, results, and residual risk.

## Deviations

A deviation is any meaningful change from the accepted plan, including:

- New files outside the step scope.
- New dependencies.
- Runtime behavior where the plan called for docs/config only.
- Provider-specific behavior in canonical docs.
- Weaker safety, browser, or credential rules.
- Different verification than the step required.

For deviations, stop and ask before proceeding unless the change is a narrow prerequisite needed to complete the current step.

## User Edits

If files contain changes the agent did not make:

- Treat them as user changes.
- Read and work with them.
- Do not revert them unless the user explicitly requests it.
- If they make the step impossible, ask the user how to proceed.

## Completion Summary

Use this format:

```markdown
Step N complete.

Changed:
- File path and short purpose.

Verification:
- Command or check: result.

Verification level:
- Exact level reached.

Open questions:
- Any remaining issue, or "None".
```

