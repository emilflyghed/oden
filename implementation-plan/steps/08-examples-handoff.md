# Step 8: Examples And Handoff

## Goal

Add final examples and handoff material so users and future agents can install, copy, or adapt Oden confidently.

## Prerequisite

Steps 1 through 7 must be complete.

## Scope

Create:

```text
agent-docs/examples/
  README.md
  start-step-example.md
  provider-install-example.md
  browser-research-example.md
agent-docs/handoffs/final-phase2-handoff.md
```

Optional:

- Add a root `README.md` only if the user wants the repo to present Oden publicly. Ask first if uncertain.

## Content Requirements

`start-step-example.md`:

- Show how a user tells an agent to start a step.
- Show what the agent should read.
- Show what the agent should report.

`provider-install-example.md`:

- Show a generic global configuration flow.
- Explain that provider-specific instructions live under `agent-docs/provider-bundles/`.
- Avoid pretending every provider has the same installation mechanism.

`browser-research-example.md`:

- Show safe public research.
- Show where evidence is recorded.
- Show a permission stop for a restricted action.

`final-phase2-handoff.md`:

- Summarize the completed scaffold.
- List created files.
- List verification commands and results.
- List open questions.
- List recommended next steps.

## Do Not

- Do not include secrets or real credentials.
- Do not include examples that publish, purchase, sign up, or enter credentials.
- Do not claim provider installation was tested unless it was.

## Verification

Run:

```bash
find agent-docs/examples agent-docs/handoffs -maxdepth 1 -type f | sort
rg -n "Start step|provider|browser|permission|handoff|verification" agent-docs/examples agent-docs/handoffs
```

Then run the validation checklist from Step 7.

Manual inspection:

- Confirm examples are copyable and safe.
- Confirm final handoff reflects actual files and verification.

Report verification level according to the checks actually run.

## Stop And Ask

Ask the user before:

- Adding a public-facing root README.
- Adding examples for real external services that require accounts.
- Marking provider installation as tested without actually testing it.

