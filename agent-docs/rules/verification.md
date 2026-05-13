# Verification

Verification must be reported honestly. Code or document inspection is useful, but it is not the same as testing behavior.

## Verification Levels

Use the strongest level actually reached:

- `Not run`: no verification command or inspection was performed.
- `Inspected`: files were read and checked manually.
- `Structure checked`: expected files, links, headings, or required text were checked.
- `Provider checked`: provider bundle behavior or format was checked against current provider docs or local provider references.
- `Behavior checked`: an executable helper, browser workflow, example, test, build, or relevant command was actually run.

Do not report a higher level than the work supports.

## Required Reporting

Every completion summary must include:

- Exact command or check performed.
- Pass or fail result.
- Relevant output or observed behavior.
- Known limits of the verification.

Acceptable:

```text
Ran `rg -n "permission" agent-docs/rules`; required permission language is present in safety and browser rules.
Verification level: Structure checked.
```

Unacceptable:

```text
Looks good.
Should work.
The docs seem correct.
```

## Failed Verification

If verification fails:

- Do not hide or downplay the failure.
- Fix it if it is inside the current step scope.
- If fixing it changes scope or architecture, stop and ask.
- Report the exact failure and what remains unresolved.

## Documentation-Only Work

For docs/config scaffold work, structure checks and targeted text searches are often the right verification. Do not claim behavior was tested unless a real behavior, command, or workflow was executed.

