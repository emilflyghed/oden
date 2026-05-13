# Codebase Analyzer

## Name

codebase-analyzer

## When to use

Use this skill to explain how selected code, docs, configuration, or workflows function.

Use this skill when:

- The relevant files have already been located.
- The user asks how something works.
- A plan needs factual understanding of data flow, contracts, dependencies, or constraints.

Do not use this skill to:

- Modify files.
- Propose fixes as the main output.
- Replace implementation planning.

## Inputs expected

- Specific files, directories, functions, classes, docs, or a clearly bounded topic.
- The question the analysis should answer.
- Known constraints or files to avoid.

## Procedure

1. Stay read-only.
2. Read the selected files and nearby imports, callers, or referenced docs as needed.
3. Trace entrypoints, data flow, state changes, outputs, and error paths.
4. Identify contracts, dependencies, configuration, and side effects.
5. Separate observed behavior from inference.
6. Document risks as factual uncertainty, coupling, edge cases, or verification gaps; do not turn them into unsolicited implementation advice.

## Safety rules

- Do not edit files.
- Do not run mutation commands.
- Do not expose secrets.
- Do not claim runtime behavior was tested unless it was actually executed.

## Output format

```markdown
# Analysis: Component Or Topic

## Overview

Short factual summary.

## Files Read

- `path/file.ext:line` - Why it was read.

## Data Flow

1. Entry: `path/file.ext:line` receives or starts with...
2. Processing: `path/file.ext:line` transforms or routes...
3. Output: `path/file.ext:line` returns, writes, renders, or triggers...

## Key Contracts

- Input, output, state, schema, or API contract.

## Dependencies

- Internal and external dependencies.

## Risks Or Unknowns

- Factual risk, unclear behavior, or missing verification.

## Confidence

High, medium, or low, with a reason.
```

## Verification

- List files inspected and commands run.
- State whether the analysis is static inspection or behavior checked.
- Identify assumptions that would need tests or runtime execution.

## Stop conditions

Stop and ask before:

- Editing files.
- Expanding into broad architecture critique.
- Recommending a migration or redesign not requested by the user.
- Crossing permission gates.

