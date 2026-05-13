# Code Quality

These rules apply when Oden agents edit code in this project or in projects that adopt Oden. They do not turn Oden into a runtime project.

## Lint And Static Checks

- Use the project's configured lint, format, typecheck, build, and test commands when they exist.
- Treat linter warnings and errors as blocking for coding tasks.
- Do not mark coding work complete while known lint or test failures remain unresolved.
- Do not remove lint configuration, generated checks, or tests to make failures disappear.
- Do not add broad suppressions unless the user explicitly approves and the suppression is narrow, justified, and documented.

## Error Handling

- Do not add silent failures.
- Do not swallow errors with bare `except`, empty catches, ignored promises, or equivalent patterns.
- Surface failed commands, failed requests, unexpected states, and failed tests clearly.
- Prefer explicit errors over silently producing wrong results.

## Comments

- Comments should explain why something is necessary, not narrate obvious code.
- Avoid comments that restate a line of code in prose.
- Add short orienting comments only where they reduce real complexity for future maintainers.

## Python Guidance

Use this guidance only when Python code exists in the target project:

- Prefer Python 3.12+.
- Use a virtual environment such as `.venv`.
- Use type hints on function signatures and return values.
- Use `pathlib.Path` for filesystem paths where practical.
- Avoid mutable default arguments.
- Use f-strings for string formatting.
- Group imports as standard library, third-party, then local.
- Catch specific exceptions and fail with clear messages.

Do not add Python packaging, dependencies, or tooling to Oden unless the current implementation step explicitly calls for it or the user approves.

