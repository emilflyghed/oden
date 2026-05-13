# Handoff Workflow

A handoff lets another agent continue work without relying on chat history.

## When To Create A Handoff

Create or update a handoff when:

- The current session cannot finish the active step.
- The next agent needs exact continuation context.
- There are partial edits, failed checks, or unresolved decisions.
- The user pauses or redirects substantial work.
- Context is getting too long to trust.

## Location

Store handoffs in:

```text
agent-docs/handoffs/
```

Use a clear filename, for example:

```text
YYYY-MM-DD-step-N-short-topic.md
```

## Handoff Template

```markdown
# Handoff: Short Topic

## Date

YYYY-MM-DD

## Current Goal

What the user wants accomplished.

## Current Step

Plan file or task scope being followed.

## Completed Work

- What is already done.

## Files Changed

- Path and purpose.

## Commands Run

- Command: pass/fail and relevant output.

## Known Failures

- Failed check, error, or blocker.

## Decisions Made

- Decision and source.

## Open Questions

- Question and why it matters.

## Constraints

- Scope limits, permission gates, provider uncertainty, or runtime limits.

## Next Recommended Action

The smallest useful next step.
```

## Rules

- Do not include secrets, tokens, credentials, cookies, or private keys.
- Do not claim verification that was not performed.
- Include failed commands and known limitations.
- Keep handoffs factual and resumable.

