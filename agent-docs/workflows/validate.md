# Validate Workflow

Validation checks whether the work actually satisfies the task. It must report what was checked, not what the agent hopes is true.

## Verification Levels

Use the levels defined in `agent-docs/rules/verification.md`:

- `Not run`
- `Inspected`
- `Structure checked`
- `Provider checked`
- `Behavior checked`

Report only the strongest level actually reached.

## Procedure

1. Read the success criteria in the active plan or task.
2. Identify the strongest practical verification for this kind of change.
3. Run the required commands or perform the required inspections.
4. Capture exact command names, pass/fail status, and relevant output.
5. Check that no scope boundaries were crossed.
6. Record residual risk and unverified assumptions.
7. If validation fails, fix in scope or stop and ask.

## Documentation Checks

For docs/config work, validation usually means:

- Required files exist.
- Required headings or sections exist.
- Canonical links point to the right locations.
- Provider-specific content does not replace canonical docs.
- Permission gates are present.
- No runtime or dependency files were added when the plan forbids them.

## Behavior Checks

Claim `Behavior checked` only when a real command, script, app flow, browser flow, example, or test was executed and its observed result supports the claim.

## Residual Risk

Every validation summary should mention remaining limits, such as:

- Provider docs were not checked.
- Browser flow was not run.
- Only structure was checked.
- No executable code exists yet.
- Current environment prevented a command from running.

## Failure Handling

If validation fails:

- Report the failure exactly.
- Do not hide failed output.
- Fix failures that are inside scope.
- Ask before fixing failures that require a scope, dependency, provider, runtime, or permission change.

