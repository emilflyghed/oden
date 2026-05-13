# Codex Bundle

Use this bundle to apply Oden behavior in Codex.

## Sources Checked

Checked on 2026-05-12:

- `https://developers.openai.com/codex/guides/agents-md`
- `https://developers.openai.com/codex/skills`
- `https://developers.openai.com/codex/rules`

## What To Copy

Project use:

- Keep the repository root `AGENTS.md`.
- If adopting Oden in another project, copy `AGENTS.md` from this bundle to that project root and keep `agent-docs/` with it.

Global use:

- Copy `global-instructions.md` into your Codex global guidance, usually `~/.codex/AGENTS.md`.
- Keep it short enough that project `AGENTS.md` files remain visible in context.

Optional Codex skills:

- Codex skills use `.agents/skills/<skill-name>/SKILL.md` or user-level skill folders.
- Oden's canonical skills live in `agent-docs/skills/` and are not converted in this step.
- Convert Oden skills only when you need native Codex skill discovery.

## Canonical Docs

Canonical Oden docs remain:

- `agent-docs/README.md`
- `agent-docs/rules/common-mistakes.md`
- `agent-docs/rules/`
- `agent-docs/workflows/`
- `agent-docs/skills/`
- `agent-docs/handoffs/`

Provider files are adapters. Canonical Oden docs take precedence.

