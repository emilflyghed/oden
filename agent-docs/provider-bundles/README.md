# Provider Bundles

This directory holds exportable instructions for specific agent providers.

Provider bundles are adapters. Canonical Oden behavior lives in `agent-docs/` and takes precedence.

## Bundles

- `codex/`: project and global Codex instructions.
- `claude-code/`: Claude Code `CLAUDE.md`, command, and subagent adapters.
- `cursor/`: Cursor rule adapters.
- `hermes-lmstudio/`: local/open-model system instructions and tool policy.
- `chatgpt/`: copyable global and project instructions for ChatGPT.

## Canonical Source

All bundles must point back to:

- `AGENTS.md`
- `agent-docs/README.md`
- `agent-docs/rules/common-mistakes.md`
- `agent-docs/rules/`
- `agent-docs/workflows/`
- `agent-docs/skills/`
- `agent-docs/handoffs/`

Do not edit provider bundles as the only source of a behavior change. Update canonical Oden docs first, then refresh the affected provider adapters.

## Sources Checked

Provider conventions were checked on 2026-05-12:

- Codex: `https://developers.openai.com/codex/guides/agents-md`, `https://developers.openai.com/codex/skills`, `https://developers.openai.com/codex/rules`
- Claude Code: `https://code.claude.com/docs/en/memory`, `https://code.claude.com/docs/en/slash-commands`, `https://code.claude.com/docs/en/sub-agents`, `https://code.claude.com/docs/en/settings`
- Cursor: `https://docs.cursor.com/en/context/rules`
- Hermes/LM Studio: `https://lmstudio.ai/docs/integrations/hermes`, `https://www.lmstudio.ai/docs/developer/openai-compat/tools`, `https://hermes-agent.nousresearch.com/docs/user-guide/features/code-execution/`, `https://hermes-agent.nousresearch.com/docs/reference/toolsets-reference`
- ChatGPT: `https://help.openai.com/en/articles/8096356-chat-preferences-for-chatgpt`, `https://help.openai.com/en/articles/10169521-using-projects-in-chatgpt`

Re-check provider docs before changing provider-specific file names, config locations, or feature claims.
