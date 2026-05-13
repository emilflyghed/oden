# Step 6: Browser Research Harness

## Goal

Add Oden's guarded browser research/testing capability.

## Prerequisite

Steps 1 through 5 must be complete.

## Scope

Create or fill:

```text
agent-docs/browser/
  README.md
  permissions.md
  research-playbook.md
  site-skill-template.md
  evidence-template.md
```

This step must add the guarded browser capability to the scaffold as docs/config. Executable browser-harness code is optional and requires user confirmation before copying source, adding dependencies, launching browsers, or using cloud/browser infrastructure.

## Required Policy

Allowed by default:

- Open public pages.
- Search and read.
- Inspect dynamic pages.
- Capture screenshots.
- Use HTTP/API access for static public data.
- Try Oden behavior in browser tools when no irreversible action occurs.

Requires explicit permission:

- Publishing or submitting information.
- Signing up.
- Entering credentials.
- Making payments or purchases.
- Sending messages.
- Changing account settings.
- Deleting data.
- Accepting terms.
- Any irreversible or externally visible action.

Auth walls:

- Do not type credentials.
- Stop and ask the user.
- If the user chooses to authenticate manually, wait for them and continue only after confirmation.

## Harness Design

Use browser-harness principles:

- Thin interface.
- Screenshots first for visual tasks.
- Verify after meaningful actions.
- Prefer HTTP/API for static public data.
- Keep domain skills durable and non-secret.
- Avoid heavy orchestration layers.

Executable code is not required for the docs/config scaffold. If the user explicitly confirms executable code should be included:

- Keep it optional.
- Keep it small and inspectable.
- Preserve MIT license notices for copied browser-harness code.
- Do not create cloud/browser billing behavior without explicit user confirmation.
- Do not copy large unused domain-skill libraries.

## Browser Skill Files

`research-playbook.md` should explain:

- When browser use is justified.
- How to capture evidence.
- How to cite URLs and timestamps.
- How to handle dynamic pages.
- How to stop at restricted actions.

`site-skill-template.md` should include:

- Site purpose.
- URLs/endpoints.
- Stable selectors or interaction notes.
- Known gotchas.
- Permission-sensitive actions.
- Last verified date.
- Evidence requirements.

`evidence-template.md` should include:

- URL.
- Date/time.
- Browser state.
- Screenshot path if any.
- Extracted facts.
- Confidence.
- Follow-up needed.

## Do Not

- Do not create an autonomous browser publishing system.
- Do not type credentials.
- Do not scrape sites in ways that violate user instructions.
- Do not add cloud browser usage that may incur cost without asking.
- Do not copy all reference domain skills by default.

## Verification

Run:

```bash
find agent-docs/browser -maxdepth 1 -type f | sort
rg -n "permission|credential|payment|publish|screenshot|evidence|auth" agent-docs/browser agent-docs/rules agent-docs/skills
```

Manual inspection:

- Confirm browser restrictions are present in browser docs, rules, skills, and provider bundles.
- Confirm no executable browser harness code, dependency, local browser launch, or cloud browser setup was added unless the user confirmed it.
- If executable code was added, run its documented smoke test and report the exact result.

Report verification level as:

- `Structure checked` for docs-only integration.
- `Behavior checked` only if a runnable browser harness smoke test was executed.

## Stop And Ask

Ask the user before:

- Adding executable browser harness code.
- Copying browser-harness source into the repo.
- Launching cloud browser infrastructure.
- Performing permission-required browser actions.
