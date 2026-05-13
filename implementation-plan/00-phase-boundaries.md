# Phase Boundaries

## Phase 1

Phase 1 writes this implementation plan only. It does not build Oden.

Allowed Phase 1 outputs:

- Markdown implementation-plan files.
- Step definitions for Phase 2.
- Architecture, rule, provider, skill, browser, validation, and handoff plans.

Not allowed in Phase 1:

- Creating the final `AGENTS.md`, `CLAUDE.md`, provider bundles, skills, or `agent-docs/` scaffold.
- Adding a package, CLI, runtime, browser harness, tests, scripts, or dependency files.
- Installing dependencies.
- Running implementation validation for files that do not exist yet.

## Phase 2

Phase 2 builds the scaffold from these plan files.

The scaffold must be docs/config first. Executable helpers are allowed only when they directly validate, export, or support the scaffold and can be ignored by providers that only consume markdown.

Phase 2 must preserve these boundaries:

- Canonical Oden content lives in Oden-owned docs.
- Provider-specific files are generated or manually adapted views of canonical content.
- Browser automation is a guarded research/testing capability, not an autonomous publishing or purchasing system.
- Agent workflows are enforceable through instructions, checklists, checkpoints, and handoff artifacts rather than a mandatory runtime.
