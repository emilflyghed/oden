# Decisions

This file records accepted long-lived decisions for Oden.

## Locked Product Decisions

- Oden is a docs/config scaffold consumed directly by agents.
- Oden core does not depend on LangGraph, LangChain, or a provider SDK.
- Oden borrows LangGraph-style concepts as file-based protocols: state, checkpoints, interrupts, tool routing, validation gates, and handoffs.
- Canonical Oden content lives under `agent-docs/`.
- Provider-specific files and export bundles are adapters; canonical docs take precedence.
- `agent-docs/rules/common-mistakes.md` is the stable common mistakes file.
- Browser capability is part of Oden as guarded research/testing guidance.
- Browser actions that publish, sign up, enter credentials, make payments, send messages, change account settings, delete data, submit information, accept terms, or cause irreversible/external effects require explicit user permission.
- Phase 2 should favor readable markdown and explicit checklists over automation.
- Small validation helpers may be added later only if they support the docs/config scaffold and remain optional for agents that cannot execute local code.
- Git initialization is out of scope unless the user explicitly asks for it.

## Source Of Decisions

These decisions come from the Phase 0/Phase 1 discussion and the implementation plan in `implementation-plan/`.
