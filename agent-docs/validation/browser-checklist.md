# Browser Checklist

Use this checklist before relying on browser research/testing guidance or exporting browser-related provider instructions.

## Required Browser Docs

- [ ] `agent-docs/browser/README.md`
- [ ] `agent-docs/browser/permissions.md`
- [ ] `agent-docs/browser/research-playbook.md`
- [ ] `agent-docs/browser/site-skill-template.md`
- [ ] `agent-docs/browser/evidence-template.md`
- [ ] `agent-docs/rules/browser-safety.md`
- [ ] `agent-docs/skills/browser-researcher.md`

## Allowed-By-Default Actions

Confirm browser docs allow only guarded, reversible work by default:

- [ ] Reading public pages.
- [ ] Searching and following public links.
- [ ] Inspecting dynamic public pages.
- [ ] Capturing screenshots or page-state evidence when appropriate.
- [ ] Trying Oden behavior where no irreversible or externally visible action occurs.
- [ ] Using HTTP/API requests for static public data when that is sufficient.

## Explicit-Permission Actions

Confirm browser docs require explicit user permission before:

- [ ] Publishing, submitting, posting, or sending information.
- [ ] Signing up for accounts.
- [ ] Entering credentials, tokens, cookies, or private keys.
- [ ] Making purchases or payments.
- [ ] Changing account settings.
- [ ] Deleting data.
- [ ] Accepting terms.
- [ ] Uploading files or downloading sensitive private data.
- [ ] Reusing browser profiles, cookies, or authenticated sessions.
- [ ] Using paid remote or cloud browser services.
- [ ] Taking any irreversible or externally visible action.

## Auth Walls And Secrets

- [ ] Auth-wall behavior says to stop and ask before entering credentials.
- [ ] If the user authenticates manually, docs require waiting for user confirmation before continuing.
- [ ] Evidence docs forbid recording credentials, cookies, tokens, private keys, and secret material.
- [ ] Site skills do not include secrets or credential storage.

## Evidence Capture

- [ ] Evidence template captures date/time, scope, sources, findings, verification, limitations, and permission stops.
- [ ] Research playbook distinguishes direct observation, inference, and unverified claims.
- [ ] Screenshots are treated as supporting evidence, not a replacement for source URLs and written findings.
- [ ] Agents are told not to claim screenshots, page states, or behavior checks that were not actually captured or observed.

## Site Skills

- [ ] Site skill template records safe entrypoints and public API notes.
- [ ] Site skill template avoids brittle pixel-only selectors or visual-only instructions when semantic anchors exist.
- [ ] Site skill template includes permission-sensitive actions and auth-wall behavior.
- [ ] Site skill template includes known gotchas without embedding private data.

## Docs-Only Boundary

- [ ] Browser docs do not introduce a mandatory runtime dependency.
- [ ] Browser docs do not add browser launch, remote daemon, cloud browser, or provider credential setup.
- [ ] If executable browser tooling is added later, it is optional, attributed where needed, and covered by an updated validation result.

## Suggested Commands

```bash
find agent-docs/browser -maxdepth 1 -type f | sort
rg -n "permission|credential|payment|publish|screenshot|evidence|auth|secret|cookie|token" agent-docs/browser agent-docs/rules agent-docs/skills agent-docs/provider-bundles
```
