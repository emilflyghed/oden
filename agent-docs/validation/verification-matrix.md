# Verification Matrix

Use this matrix to choose the minimum practical verification for common Oden task types.

Always report the strongest level actually reached from `agent-docs/rules/verification.md`.

## Matrix

| Task Type | Minimum Checks | Typical Level |
| --- | --- | --- |
| Docs/config change | Required files exist, headings/sections present, canonical links correct, targeted `rg` for required terms | `Structure checked` |
| Provider bundle change | Structure checks plus current provider docs or authoritative local provider references for file names, config paths, and feature claims | `Provider checked` if provider docs were checked; otherwise `Structure checked` |
| Browser guidance change | Browser files exist, permission gates present, auth-wall behavior clear, evidence requirements present | `Structure checked` |
| Browser workflow execution | Approved browser flow actually run, page state or screenshot recorded, permission stops respected | `Behavior checked` |
| Research task | Sources listed, facts separated from inference, confidence stated, open questions recorded | `Inspected` or `Provider checked` when provider docs were checked |
| Code change, if future code exists | Relevant tests, lint, build, or executable command run where available | `Behavior checked` when the command actually checks behavior |
| Failed validation | Exact failure recorded, recovery class assigned, in-scope fix attempted or blocker reported | Level reached before failure, plus residual risk |
| Handoff/finalization | Files changed, commands run, decisions, open questions, risks, and next action recorded | `Structure checked` if handoff contents were inspected |

## Default Commands

For docs/config changes:

```bash
find agent-docs -maxdepth 3 -type f | sort
rg -n "required-term|canonical-path|permission|verification" AGENTS.md agent-docs
```

For provider bundle changes:

```bash
find agent-docs/provider-bundles -maxdepth 3 -type f | sort
rg -n "AGENTS.md|agent-docs/README.md|common-mistakes|permission|verification|handoff" agent-docs/provider-bundles
```

For browser guidance changes:

```bash
find agent-docs/browser -maxdepth 1 -type f | sort
rg -n "permission|credential|payment|publish|screenshot|evidence|auth|secret|cookie|token" agent-docs/browser agent-docs/rules agent-docs/skills agent-docs/provider-bundles
```

For markdown structure:

```bash
find agent-docs -type f -print0 | xargs -0 awk 'BEGIN{bad=0} /^```/{c[FILENAME]++} END{for (f in c) if (c[f] % 2) {print "unmatched fences: " f; bad=1} exit bad}'
```

## Reporting Rule

If the chosen check could not be run, report:

- Why it could not run.
- What was checked instead.
- The weaker verification level actually reached.
- Residual risk.
