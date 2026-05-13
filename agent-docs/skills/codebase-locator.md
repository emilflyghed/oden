# Codebase Locator

## Name

codebase-locator

## When to use

Use this skill to find where relevant code, docs, settings, patterns, functions, classes, tests, or entrypoints live.

Use this skill when:

- The user asks where something is implemented.
- A future agent needs a map before analysis or implementation.
- The task requires paths and line references, not deep explanation.

Do not use this skill to:

- Analyze how code works in depth.
- Recommend fixes.
- Modify files.

## Inputs expected

- Topic, feature, symbol, error text, file type, or directory scope.
- Optional boundaries such as paths to include or exclude.

## Procedure

1. Stay read-only.
2. Prefer `rg` and `rg --files` for search.
3. Search names, symbols, visible text, config keys, tests, and entrypoints.
4. Open only the files needed to confirm the match.
5. Group results by implementation, tests, configuration, docs, entrypoints, and related directories.
6. Give short reasons for why each path matters.

## Safety rules

- Do not edit files.
- Do not run destructive commands.
- Do not inspect secrets beyond confirming a path exists when necessary.
- Do not infer behavior beyond what the located files support.

## Output format

```markdown
# File Locations: Topic

## Implementation

- `path/file.ext:line` - Why this location matters.

## Tests

- `path/test.ext:line` - What it appears to cover.

## Configuration

- `path/config.ext:line` - Relevant setting or key.

## Docs

- `path/doc.md:line` - Relevant documentation.

## Entry Points

- `path/file.ext:line` - How the flow starts.

## Gaps

- Expected item that was not found, or "None".
```

## Verification

- Report search commands or inspections used.
- Include enough paths and line references for another agent to resume.
- State confidence based on search breadth.

## Stop conditions

Stop and ask before:

- Expanding into implementation.
- Inspecting sensitive files beyond what is necessary.
- Searching outside the user-approved workspace.

