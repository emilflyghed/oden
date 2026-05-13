# Review Example

Use this example for a final self-review before reporting completion.

## Self-Review

```markdown
## Self-Review

- Scope: stayed within docs/config refinement.
- Files read first: `AGENTS.md`, `agent-docs/README.md`, workflow and validation indexes.
- User edits: no unrelated edits reverted.
- Canonical alignment: canonical docs updated first; provider bundles only point back.
- Permission gates: preserved.
- Common mistakes: checked and updated with durable retry lesson.
- Failure recovery: no failed checks required recovery.
- Verification: static file, text, fence, and dependency checks run.
- Verification level: `Structure checked`.
- Handoff needed: no incomplete work remains.
```

## Review Findings Format

If the user asks for a review, use findings first:

```markdown
## Findings

- High: `agent-docs/workflows/validate.md` - The workflow allows retries but does not require failure classification, so weaker models may loop.

## Open Questions

- None.

## Notes

- No behavior checks were run; this was a docs/config review.
```

If there are no findings, say so directly and name any remaining verification limits.
