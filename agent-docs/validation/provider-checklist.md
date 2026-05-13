# Provider Checklist

Use this checklist when creating, changing, or exporting provider bundles. Canonical Oden docs remain the source of truth; provider files are adapters.

## Provider Inventory

- [ ] `agent-docs/provider-bundles/README.md` lists every supported provider bundle.
- [ ] `agent-docs/provider-bundles/codex/` exists.
- [ ] `agent-docs/provider-bundles/claude-code/` exists.
- [ ] `agent-docs/provider-bundles/cursor/` exists.
- [ ] `agent-docs/provider-bundles/hermes-lmstudio/` exists.
- [ ] `agent-docs/provider-bundles/chatgpt/` exists.

## Canonical Source Links

For each provider bundle:

- [ ] The README or entrypoint points back to `AGENTS.md`.
- [ ] The README or entrypoint points back to `agent-docs/README.md`.
- [ ] Common mistakes point to `agent-docs/rules/common-mistakes.md`.
- [ ] Rules point to `agent-docs/rules/`.
- [ ] Workflows point to `agent-docs/workflows/`.
- [ ] Skills point to `agent-docs/skills/`.
- [ ] Handoffs point to `agent-docs/handoffs/`.
- [ ] Provider-specific wording does not override canonical Oden docs unless it is clearly an adapter constraint.

## Provider-Specific Files

- [ ] Codex bundle includes a project `AGENTS.md` adapter and copyable global instructions.
- [ ] Claude Code bundle includes `CLAUDE.md`, slash-command adapters, and subagent adapters.
- [ ] Cursor bundle includes `.mdc` rule adapters with correct scope metadata for the intended usage.
- [ ] Hermes/LM Studio bundle includes system instructions and tool policy suitable for local/open-model use.
- [ ] ChatGPT bundle includes copyable global and project instructions.

## Provider Claims

- [ ] File names, config locations, and feature claims were checked against current provider docs before changing them.
- [ ] If current provider docs were not checked in this session, the bundle marks uncertain claims or points to the last checked date.
- [ ] `agent-docs/provider-bundles/README.md` records sources checked and warns future agents to re-check provider docs before changing provider-specific details.
- [ ] The final response states whether provider details reached `Provider checked` or only `Structure checked`.

## Permission Gates

For each provider bundle, confirm that it preserves explicit permission requirements for:

- [ ] Destructive git or filesystem actions.
- [ ] Credentials, auth walls, tokens, cookies, and secret material.
- [ ] Publishing, submitting, sending messages, or externally visible actions.
- [ ] Signups, purchases, payments, and account settings.
- [ ] Browser actions with irreversible or external effects.
- [ ] Mandatory dependencies or changing Oden from docs/config-first to runtime-first.

## Export Instructions

- [ ] Installation or copy instructions are plain enough for a user to apply in that provider.
- [ ] Instructions do not require copying unrelated reference clutter.
- [ ] Instructions do not imply that provider bundles replace canonical Oden docs.
- [ ] Instructions identify what the bundle changes for that provider.
- [ ] Instructions explain how to refresh the bundle after canonical docs change.

## Suggested Commands

```bash
find agent-docs/provider-bundles -maxdepth 3 -type f | sort
rg -n "AGENTS.md|agent-docs/README.md|common-mistakes|permission|credential|payment|publish|handoff" agent-docs/provider-bundles
```
