# Checkpoint Workflow

A checkpoint is a short written state snapshot that makes work resumable. It is inspired by graph checkpointing, but in Oden it is a file-based protocol, not a runtime feature.

## When To Create A Checkpoint

Create a checkpoint when:

- Work pauses before completion.
- Context is getting long or unreliable.
- A step reaches a meaningful boundary.
- A risky or permissioned action is about to be requested.
- Verification fails and the next action is not immediate.
- Another agent may need to resume the work.

## Checkpoint Versus Memory

Use a checkpoint for current task state.

Use `agent-docs/memory/decisions.md` for accepted long-lived decisions.

Use `agent-docs/memory/open-questions.md` for unresolved questions that affect future work.

Use `agent-docs/rules/common-mistakes.md` for avoidable mistakes future agents should not repeat.

## Minimum Fields

```markdown
# Checkpoint: Short Topic

## Current Goal

What the agent is trying to accomplish.

## Current Step

Plan or step file being followed.

## Completed Work

What is done.

## Files Changed

- Path and purpose.

## Commands Run

- Command: result.

## Decisions Made

- Decision and source.

## Open Questions

- Question and why it matters.

## Risks Or Constraints

- Known limitation or permission gate.

## Next Action

The next concrete action.
```

## Storage

When a task is incomplete, place resumable handoffs in `agent-docs/handoffs/`. Short checkpoints may also be embedded in a task-specific plan, implementation log, or handoff.

Do not store secrets or credentials in checkpoints.

