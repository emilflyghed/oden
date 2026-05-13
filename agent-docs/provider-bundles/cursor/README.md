# Cursor Bundle

Use this bundle to adapt Oden for Cursor.

## Sources Checked

Checked on 2026-05-12:

- `https://docs.cursor.com/en/context/rules`

## What To Copy

Project use:

- Copy files in `rules/` to `.cursor/rules/`.
- Keep the project root `AGENTS.md` and `agent-docs/` in place.

Global use:

- Put the short global behavior from `rules/oden-core.mdc` into Cursor Settings -> Rules if you want it across all projects.

## Current Cursor Conventions

- Project rules live in `.cursor/rules`.
- Rule files use MDC frontmatter.
- User rules are global through Cursor Settings -> Rules.
- `AGENTS.md` is supported as a simpler markdown instruction alternative.
- `.cursorrules` is legacy; prefer project rules.

## Canonical Docs

These Cursor rules are adapters. Canonical Oden docs remain under `agent-docs/`.

