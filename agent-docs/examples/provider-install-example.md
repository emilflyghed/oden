# Provider Install Example

Use this pattern when adding Oden to an agent provider's global or project-level instructions.

## Generic Flow

1. Keep the canonical Oden scaffold available to the agent:

```text
AGENTS.md
agent-docs/
```

2. Choose the provider bundle:

```text
agent-docs/provider-bundles/codex/
agent-docs/provider-bundles/claude-code/
agent-docs/provider-bundles/cursor/
agent-docs/provider-bundles/hermes-lmstudio/
agent-docs/provider-bundles/chatgpt/
```

3. Read the provider bundle README.

4. Copy the provider-specific instruction text into that provider's supported global, project, rule, command, or system-instruction location.

5. Keep the provider bundle pointing back to canonical Oden docs:

```text
AGENTS.md
agent-docs/README.md
agent-docs/rules/common-mistakes.md
agent-docs/rules/
agent-docs/workflows/
agent-docs/skills/
agent-docs/handoffs/
```

6. Ask the provider agent to confirm it can find the canonical docs before starting real work.

## Example User Prompt

```text
Add this Oden bundle to your global configuration so it applies to future sessions. Use the provider-specific bundle under agent-docs/provider-bundles/, and keep agent-docs/ as the canonical source.
```

## Provider Differences

Do not assume every provider has the same installation mechanism.

- Codex uses `AGENTS.md`-style instruction files and global/project instructions.
- Claude Code supports memory files, slash commands, and subagents.
- Cursor supports rule files such as `.mdc` rules.
- Hermes/LM Studio use local/open-model system instructions and tool policies.
- ChatGPT uses copyable custom instructions or project instructions.

Check the provider bundle and current provider docs before changing provider-specific file names, config paths, or feature claims.

## Safe Claims

Say:

```text
The provider bundle has copyable instructions for this provider.
```

Do not say:

```text
Provider installation is tested.
```

unless installation was actually performed in that provider.

## Verification

For a static scaffold check, use:

```bash
find agent-docs/provider-bundles -maxdepth 3 -type f | sort
rg -n "AGENTS.md|agent-docs/README.md|common-mistakes|permission|credential|payment|publish|handoff" agent-docs/provider-bundles
```

Report the result as `Structure checked` unless provider behavior or provider docs were actually checked in the current session.
