# Failure Recovery Example

Use this example when a check fails.

## Failed Check

```text
rg -n "failure-recovery" agent-docs/workflows agent-docs/provider-bundles
```

Example result:

```text
No matches in provider bundles.
```

## Recovery Note

```markdown
## Failure Recovery

- Failed check: `rg -n "failure-recovery" agent-docs/workflows agent-docs/provider-bundles`
- Relevant output: workflow doc exists, provider bundles do not mention it.
- Class: Implementation defect.
- In scope: yes.
- Recovery action: Add concise provider adapter pointers to canonical workflow docs.
- Retry command: `rg -n "failure-recovery" agent-docs/workflows agent-docs/provider-bundles`
- Result: pass after provider pointers were added.
- Residual risk: Provider behavior itself was not tested.
- Common mistake update needed: no; this was a task-specific miss, not a durable new lesson.
```

## Rules Demonstrated

- The failed output is recorded.
- The cause is classified before retrying.
- The retry is meaningfully different because files were updated first.
- The final verification level remains `Structure checked` unless provider behavior was actually tested.
