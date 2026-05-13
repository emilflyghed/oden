# Target Architecture

Oden is a provider-neutral agent operating scaffold.

It gives agents:

- Where to look.
- How to work.
- What must be verified.
- How to pause for permission.
- How to hand off state.
- How to export the same behavior into different agent providers.

## Canonical Tree

Phase 2 should create this tree unless there is a strong reason to adjust it:

```text
.
  AGENTS.md
  agent-docs/
    README.md
    rules/
      README.md
      agent-behavior.md
      safety-permissions.md
      verification.md
      common-mistakes.md
      code-quality.md
      browser-safety.md
    workflows/
      README.md
      research.md
      plan.md
      implement.md
      validate.md
      checkpoint.md
      handoff.md
      start-step.md
    skills/
      README.md
      skill-template.md
      codebase-locator.md
      codebase-analyzer.md
      web-researcher.md
      browser-researcher.md
      provider-bundle-maintainer.md
    memory/
      README.md
      decisions.md
      open-questions.md
      session-log.md
    handoffs/
      README.md
    provider-bundles/
      README.md
      codex/
      claude-code/
      cursor/
      hermes-lmstudio/
      chatgpt/
    validation/
      README.md
      scaffold-checklist.md
      provider-checklist.md
      browser-checklist.md
    browser/
      README.md
      permissions.md
      research-playbook.md
      site-skill-template.md
```

## Root Entrypoint

`AGENTS.md` is the universal project entrypoint.

It should:

- Tell every agent to read `agent-docs/README.md`.
- Point to common mistakes at `agent-docs/rules/common-mistakes.md`.
- State the permission policy for destructive, browser, credential, publishing, payment, and irreversible actions.
- Explain the `Start step X` protocol.
- Explain how to create handoffs.

Provider-specific entrypoints may duplicate a short version, but they must point back to canonical docs.

## State Model

Oden's state model is file-based:

- Stable rules live in `agent-docs/rules/`.
- Workflow state lives in current task docs or handoff docs.
- Long-lived decisions live in `agent-docs/memory/decisions.md`.
- Unknowns live in `agent-docs/memory/open-questions.md`.
- Avoidable mistakes live in `agent-docs/rules/common-mistakes.md`.
- Session continuation lives in `agent-docs/handoffs/`.

Agents must write state down when it affects future work.

## Checkpoints

A checkpoint is a short written summary that makes the work resumable.

Minimum checkpoint fields:

- Current goal.
- Files changed.
- Commands run and results.
- Decisions made.
- Open questions.
- Next recommended action.
- Risks or constraints.

Checkpoints may be embedded in a handoff or in a task-specific implementation log.

## Interrupts

An interrupt is a required pause for user input.

Agents must interrupt for:

- Permissioned browser actions.
- Destructive commands.
- Credentials or auth walls.
- Scope changes that modify the accepted plan.
- Missing product decisions.
- Failed verification that cannot be fixed within the step.

The interrupt message should state the blocked action, why confirmation is needed, and the smallest useful question.

## Tool Routing

Tools are chosen by task:

- Filesystem search/read/write for local implementation.
- Web or browser only when information may be current, external, visual, or behind dynamic pages.
- Browser actions only under the browser permission policy.
- Provider documentation checks before writing provider-specific bundles.

Tool results must be verified against the task. Do not treat a successful command as proof of correct behavior unless the command actually checks the behavior.

## Provider Export Model

Canonical docs are the source. Provider bundles are adapters.

Each provider bundle should include:

- Installation or copy instructions.
- Provider-specific entrypoint file.
- Any commands, agents, rules, or skills supported by that provider.
- A short "what this bundle changes" note.
- A note that canonical docs in `agent-docs/` take precedence.

## Browser Model

Browser docs and skills should define:

- Safe default actions.
- Permission-required actions.
- Research workflow.
- Screenshot/page-state verification.
- Domain skill template.
- Auth-wall behavior.
- Evidence capture format.

If executable browser harness code is copied or adapted in Phase 2, keep it thin, attributed, and optional.

