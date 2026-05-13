# Review Workflow

Use this workflow when the user asks for a review, or before finalizing substantial implementation work.

Review is not implementation. It checks correctness, scope, verification, safety, and handoff quality.

## Review Modes

Use one of these modes:

- `Code review`: inspect changes for bugs, regressions, missing tests, and risks.
- `Docs/config review`: inspect structure, links, canonical source alignment, provider drift, and permission gates.
- `Self-review`: final pass over the agent's own work before reporting completion.

## Code Review Output

When the user asks for a review, lead with findings:

```markdown
## Findings

- Severity: file/path:line - Issue and impact.

## Open Questions

- Question or assumption.

## Notes

- Brief context only if useful.
```

If there are no findings, say that clearly and mention remaining test gaps or residual risk.

## Self-Review Checklist

Before a completion response, check:

- Did the work stay within the user request or active step?
- Were relevant files read before editing?
- Were user changes preserved?
- Are canonical docs and provider bundles aligned?
- Were permission gates preserved?
- Was `common-mistakes.md` checked before substantial work?
- Were failures handled through `failure-recovery.md`?
- Was verification run and reported honestly?
- Is the reported verification level no stronger than the evidence?
- Is a checkpoint or handoff needed?

## Docs/Config Review Checklist

- Required files exist.
- Required headings or sections exist.
- Links and canonical paths point to the right locations.
- Provider adapters do not become the source of truth.
- Browser and credential safety language is intact.
- No runtime or dependency files were added accidentally.

## Stop Conditions

Stop and ask before:

- Fixing review findings that change scope.
- Weakening permission gates.
- Changing provider-specific behavior without checking current provider docs.
- Reclassifying a failed check as acceptable without user approval.
