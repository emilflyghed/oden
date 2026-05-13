# Step 7: Validation Suite

## Goal

Add practical validation docs and checks so agents can verify the scaffold is complete and internally consistent.

## Prerequisite

Steps 1 through 6 must be complete.

## Scope

Create or fill:

```text
agent-docs/validation/
  scaffold-checklist.md
  provider-checklist.md
  browser-checklist.md
  release-checklist.md
```

Optional:

- Add a tiny validation script only if it checks static file structure and links without creating a runtime dependency.

## Content Requirements

`scaffold-checklist.md`:

- Required directories and files.
- Required canonical links.
- Common mistakes location.
- Workflow coverage.
- Skill coverage.
- Memory and handoff coverage.

`provider-checklist.md`:

- Each provider points to canonical docs.
- Provider claims were verified or marked uncertain.
- Permission gates are preserved.
- Export instructions are copyable.

`browser-checklist.md`:

- Restricted actions require permission.
- Auth-wall behavior is clear.
- Evidence capture is defined.
- Site skills avoid secrets and brittle pixel-only instructions.

`release-checklist.md`:

- No secrets.
- No generated reference clutter.
- License/provenance noted for copied material.
- Open questions recorded.
- Final handoff ready.

## Optional Static Script

If adding a script, keep it simple and optional. It may check:

- Required files exist.
- Required phrases exist.
- Markdown links to local files resolve.

It must not:

- Require network.
- Require provider credentials.
- Require a model API key.
- Become a runtime dependency.

## Verification

Run:

```bash
find agent-docs/validation -maxdepth 1 -type f | sort
rg -n "AGENTS.md|common-mistakes|provider|browser|permission|handoff|license" agent-docs/validation
```

If an optional script is added, run it and report the exact result.

Manual inspection:

- Confirm validation covers all previous steps.
- Confirm it distinguishes docs-only checks from behavior checks.

Report verification level as `Structure checked`, or `Behavior checked` only if a validation script was run and actually checks behavior.

## Stop And Ask

Ask the user before:

- Adding non-optional dependencies.
- Adding network checks.
- Turning validation into a runtime framework.

