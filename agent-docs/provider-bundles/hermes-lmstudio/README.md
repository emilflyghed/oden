# Hermes / LM Studio Bundle

Use this bundle for Hermes Agent with LM Studio or other local/open-model setups that accept copyable system instructions and a tool policy.

## Sources Checked

Checked on 2026-05-12:

- `https://lmstudio.ai/docs/integrations/hermes`
- `https://www.lmstudio.ai/docs/developer/openai-compat/tools`
- `https://hermes-agent.nousresearch.com/docs/user-guide/features/code-execution/`
- `https://hermes-agent.nousresearch.com/docs/reference/toolsets-reference`

## What To Copy

- Put `system-instructions.md` into the provider's global system instructions or profile prompt.
- Put `tool-policy.md` wherever the provider lets you describe tool permissions and execution rules.
- Keep canonical Oden docs in the project when the agent has filesystem access.

## Current Provider Notes

- LM Studio can run a local OpenAI-compatible server, commonly at `http://localhost:1234`.
- LM Studio documents Hermes Agent as a first-class model-provider integration.
- LM Studio tool use depends on the model and supported chat/tool template; results vary by model.
- Hermes Agent supports programmatic tool calling through `execute_code`.
- Hermes toolsets include read-only `safe` tools and broader file, terminal, browser, delegation, code execution, and messaging tools.

## Canonical Docs

Canonical Oden docs remain under `agent-docs/`. These files are copyable instructions for providers that do not natively read the Oden tree.

