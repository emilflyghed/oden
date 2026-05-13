# Browser Research Example

Use this pattern for safe public research with browser or web tools.

## Safe Public Research Request

```text
Research the public documentation for this tool and summarize the current install options. Capture source URLs and note anything uncertain.
```

## Agent Reads

The agent should read:

- `agent-docs/browser/README.md`
- `agent-docs/browser/permissions.md`
- `agent-docs/browser/research-playbook.md`
- `agent-docs/browser/evidence-template.md`
- `agent-docs/rules/browser-safety.md`
- `agent-docs/skills/browser-researcher.md`

## Allowed Work

The agent may:

- Search public web pages.
- Open public documentation.
- Inspect public page state.
- Capture screenshots or page-state notes when they support the finding.
- Use public HTTP/API responses for static public data when that is enough.

## Evidence Location

Record evidence using `agent-docs/browser/evidence-template.md` or a task-specific copy of that template.

Example evidence note:

```text
Date/time: 2026-05-12 14:30 Europe/Stockholm
Scope: Public documentation for example install options.
Sources:
- https://example.invalid/docs/install
Finding: The docs describe local and container install paths.
Verification: Public page opened and install section inspected.
Limitations: No account-only docs were accessed.
Permission stops: None.
```

## Permission Stop Example

If research reaches a restricted action, stop:

```text
I reached a sign-in page. Entering credentials or crossing the auth wall requires explicit permission. Do you want to authenticate manually and tell me when to continue, or should I continue with public sources only?
```

Other permission stops include:

- Publishing, submitting, posting, or sending information.
- Signing up for an account.
- Entering credentials, tokens, cookies, or private keys.
- Making payments or purchases.
- Changing account settings.
- Deleting data.
- Accepting terms.
- Uploading files or downloading sensitive private data.
- Reusing browser profiles, cookies, or authenticated sessions.
- Any irreversible or externally visible action.

## Final Report

The agent should report:

- Sources used.
- What was directly observed.
- What was inferred.
- What remains uncertain.
- Whether screenshots or page-state evidence were captured.
- Any permission stop reached.

Do not claim browser behavior, screenshots, or provider installation were tested unless they actually were.
