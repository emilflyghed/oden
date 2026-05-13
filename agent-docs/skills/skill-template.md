# Skill Template

Use this template when adding a provider-neutral Oden skill.

## Name

Short kebab-case or plain-language name.

## When to use

Describe the trigger clearly enough that any agent can decide whether the skill applies.

Use this skill when:

- Condition one.
- Condition two.

Do not use this skill when:

- Boundary one.
- Boundary two.

## Inputs expected

- Required context.
- Files, URLs, questions, or constraints.
- Relevant permission limits.

## Procedure

1. Read `AGENTS.md`, `agent-docs/README.md`, and relevant rules.
2. Confirm the skill scope.
3. Gather only the context needed for the task.
4. Perform the skill-specific work.
5. Record sources, commands, evidence, or file paths.
6. Stop at the defined stop conditions.

## Safety rules

- Preserve canonical Oden docs as the source of truth.
- Do not cross permission gates from `agent-docs/rules/safety-permissions.md`.
- Do not cross browser gates from `agent-docs/rules/browser-safety.md`.
- Do not store secrets, credentials, tokens, cookies, or private keys.
- Do not claim verification that was not performed.

## Output format

```markdown
# Skill Result: Short Topic

## Scope

What was included and excluded.

## Findings Or Work Completed

- Result with source, path, or evidence.

## Verification

- Command or check: result.

## Confidence

High, medium, or low, with a reason.

## Open Questions

- Any unresolved issue, or "None".
```

## Verification

- Check required files, paths, sources, or evidence exist.
- Report the exact verification level reached.
- State any limitations.

## Stop conditions

Stop and ask before:

- Changing canonical Oden structure.
- Adding provider-specific format assumptions.
- Adding runtime dependencies.
- Performing destructive, irreversible, credential-sensitive, or externally visible actions.

