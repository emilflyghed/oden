# Product Decisions

These decisions are locked for Phase 2 unless the user explicitly changes them.

## Scaffold Type

Oden is a docs/config scaffold consumed directly by agents.

The core output is markdown, rules, skills, provider bundles, examples, and validation guidance. It should be useful when copied into global configuration for an agent provider.

## Runtime Dependency

Oden core does not depend on LangGraph.

Oden borrows LangGraph-style ideas:

- state
- checkpoints
- interrupts
- tool routing
- validation gates
- handoffs

These ideas are represented as files and instructions, not as a mandatory graph engine.

## Browser Capability

Browser capability is part of Phase 2, but only as a guarded research/testing harness.

Allowed by default:

- Open public pages for research.
- Inspect pages and collect evidence.
- Use screenshots and page state for verification.
- Try Oden workflows in browser-based tools when no irreversible action is involved.

Requires explicit user permission:

- Publishing information.
- Signing up for accounts.
- Entering credentials.
- Making purchases or payments.
- Sending messages.
- Changing account settings.
- Deleting, submitting, or committing irreversible data.

## Canonical Memory And Rules

Use a single canonical Oden-owned docs tree. Provider files should point back to it.

Recommended canonical location for Phase 2:

```text
agent-docs/
  README.md
  rules/
  workflows/
  skills/
  memory/
  handoffs/
  provider-bundles/
  validation/
```

`agent-docs/rules/common-mistakes.md` must be the stable common mistakes file. Every provider bundle must tell agents where it is.

## Provider Bundles

Provider integrations are exportable instruction bundles.

Expected use:

> Add this to your global configuration so that it will be used in every session from now on.

Provider bundles must not be the only source of truth. They should summarize and link to canonical Oden docs.

## Phase 2 Style

Phase 2 should favor readable markdown and explicit checklists over clever automation.

Small validation helpers are acceptable if useful, but the scaffold must still work for agents that cannot execute local code.

## Open Items For Phase 2 Agents

Phase 2 agents should verify current provider-specific conventions before writing final export guidance, especially for Cursor, Hermes/LM Studio, ChatGPT, Codex, and Claude Code.

If current documentation conflicts with this plan, stop and ask the user before changing the architecture.

