# Claude Code Bundle

Use this bundle to adapt Oden for Claude Code.

## Sources Checked

Checked on 2026-05-12:

- `https://code.claude.com/docs/en/memory`
- `https://code.claude.com/docs/en/slash-commands`
- `https://code.claude.com/docs/en/sub-agents`
- `https://code.claude.com/docs/en/settings`

## What To Copy

Project use:

- Copy `CLAUDE.md` to the project root or `.claude/CLAUDE.md`.
- Copy files in `commands/` to `.claude/commands/`.
- Copy files in `agents/` to `.claude/agents/` if you want Claude Code subagent adapters.

Global use:

- Copy the relevant parts of `CLAUDE.md` into `~/.claude/CLAUDE.md`.

## Current Claude Code Conventions

- Claude Code reads `CLAUDE.md`, not `AGENTS.md`.
- A Claude `CLAUDE.md` can import `AGENTS.md` with `@AGENTS.md`.
- Claude Code skills now cover custom command behavior, but existing `.claude/commands/*.md` files still work.
- Project subagents live under `.claude/agents/` as markdown files with YAML frontmatter.

## Canonical Docs

Canonical Oden docs remain under `agent-docs/`. This bundle imports or references them rather than duplicating the full scaffold.

