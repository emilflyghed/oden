# Provider Bundle Maintainer

## Name

provider-bundle-maintainer

## When to use

Use this skill when creating, reviewing, or updating exportable Oden instruction bundles for agent providers.

Use this skill when:

- Writing provider bundle files under `agent-docs/provider-bundles/`.
- Checking whether provider-specific instructions match current provider conventions.
- Translating canonical Oden docs into provider-specific entrypoints, commands, rules, or global instruction text.
- Investigating provider drift or conflicting provider instructions.

Do not use this skill to make provider bundles the canonical source of truth.

## Inputs expected

- Provider name.
- Target bundle path.
- Canonical Oden docs that should be represented.
- Current provider documentation or instruction source to verify against.
- Any known provider limitations.

## Procedure

1. Read canonical Oden docs first: `AGENTS.md`, `agent-docs/README.md`, rules, workflows, and relevant skills.
2. Verify current provider conventions before making provider-specific claims.
3. Keep provider files concise and adapter-focused.
4. Preserve canonical rule locations, especially `agent-docs/rules/common-mistakes.md`.
5. Preserve permission gates, browser safety, verification levels, handoff expectations, and docs/config-first architecture.
6. Mark unsupported or unverified provider features as uncertain instead of presenting them as fact.
7. Update canonical docs only when the source behavior changes for all providers.

## Safety rules

- Do not weaken Oden rules to fit a provider limitation.
- Do not invent provider features.
- Do not add provider SDKs, runtime dependencies, or generated tooling unless the current step and user allow it.
- Do not store secrets or provider credentials in bundles.
- Do not make provider-specific files canonical.

## Output format

```markdown
# Provider Bundle Maintenance: Provider

## Provider

Name and target bundle path.

## Sources Checked

- Official doc, local reference, or current project file.

## Canonical Docs Represented

- Oden source file and behavior carried over.

## Changes

- File changed and why.

## Unverified Or Unsupported

- Provider feature or assumption that remains uncertain.

## Verification

- Command, inspection, or provider-doc check and result.
```

## Verification

- Confirm each provider bundle points back to canonical `agent-docs/`.
- Confirm `agent-docs/rules/common-mistakes.md` is referenced.
- Confirm permission gates and verification levels are preserved.
- Report `Provider checked` only when current provider docs or authoritative local references were checked.

## Stop conditions

Stop and ask before:

- Dropping support for a planned provider.
- Adding mandatory runtime behavior or SDKs.
- Treating a provider-specific file as canonical.
- Proceeding when current provider docs conflict with Oden architecture.

