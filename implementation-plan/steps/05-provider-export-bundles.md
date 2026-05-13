# Step 5: Provider Export Bundles

## Goal

Create exportable instruction bundles for major agent providers while keeping canonical Oden docs as the source of truth.

## Prerequisite

Steps 1 through 4 must be complete.

## Scope

Create:

```text
agent-docs/provider-bundles/
  README.md
  codex/
    README.md
    AGENTS.md
    global-instructions.md
  claude-code/
    README.md
    CLAUDE.md
    commands/
    agents/
  cursor/
    README.md
    rules/
  hermes-lmstudio/
    README.md
    system-instructions.md
    tool-policy.md
  chatgpt/
    README.md
    global-instructions.md
    project-instructions.md
```

The exact provider filenames may change if current provider docs require it. Verify before finalizing.

## Provider Verification

Before writing final provider guidance, verify current provider conventions with official docs or locally available provider docs.

Minimum checks:

- Codex: project instruction entrypoint and any skill/global instruction conventions.
- Claude Code: project memory, slash commands, and agent configuration conventions.
- Cursor: current rule file format and global/project rule guidance.
- Hermes/LM Studio: system instruction and tool/RPC guidance for local models.
- ChatGPT: current global/project instruction capabilities and practical export format.

If official docs are unavailable, write the bundle as a conservative copyable instruction bundle and record the uncertainty in `agent-docs/memory/open-questions.md`.

## Content Requirements

Every provider bundle must:

- Explain what to copy or install.
- Point to canonical `agent-docs/`.
- Mention `agent-docs/rules/common-mistakes.md`.
- Preserve browser permission gates.
- Preserve verification levels.
- Explain handoff expectations.
- Avoid claiming provider features that were not verified.

Provider-specific files should be concise adapters, not full forks of all canonical docs.

## Bundle Guidance

Codex:

- Root/project instructions should point to `agent-docs/README.md`.
- Global instructions should explain Oden's workflow, memory, common mistakes, verification, and browser permissions.

Claude Code:

- `CLAUDE.md` should point to canonical docs.
- Commands should map to Oden workflows where useful, such as research, plan, implement, validate, and handoff.
- Agents should map to Oden skills where useful.

Cursor:

- Rule files should preserve Oden rules in Cursor-compatible form.
- Keep rules focused and avoid duplicating the entire docs tree.

Hermes/LM Studio:

- Provide system instructions for local/open models.
- Include a strict tool policy.
- State that tool execution and browser actions need permission gates.

ChatGPT:

- Provide a copyable global instructions file.
- Provide a project instructions variant.
- Include concise references to Oden file locations for projects where files are available.

## Do Not

- Do not let provider bundles become canonical.
- Do not invent unsupported provider features.
- Do not require provider users to run a Python package.
- Do not weaken permissions to fit provider limitations.

## Verification

Run:

```bash
find agent-docs/provider-bundles -maxdepth 3 -type f | sort
rg -n "agent-docs|common-mistakes|permission|verification|handoff" agent-docs/provider-bundles
```

Manual inspection:

- Confirm every bundle points back to canonical docs.
- Confirm provider-specific claims were verified or marked as uncertain.
- Confirm browser permissions survived every bundle.

Report verification level as `Provider checked` only if current provider docs were checked. Otherwise report `Structure checked` and list unverified provider assumptions.

## Stop And Ask

Ask the user before:

- Dropping support for one of the listed providers.
- Adding a mandatory runtime or provider SDK.
- Creating generated bundle tooling instead of static docs.
- Making a provider bundle the canonical source.

