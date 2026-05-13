# Step 1: Repo Foundation

## Goal

Create the initial Oden scaffold tree and root entrypoints without implementing provider-specific bundles or browser integration yet.

## Scope

Create:

```text
AGENTS.md
agent-docs/
  README.md
  rules/README.md
  workflows/README.md
  skills/README.md
  memory/README.md
  memory/decisions.md
  memory/open-questions.md
  memory/session-log.md
  handoffs/README.md
  provider-bundles/README.md
  validation/README.md
  browser/README.md
```

Optional if the repository is not initialized:

- Ask the user before running `git init`.

## Content Requirements

`AGENTS.md` must:

- State that Oden is docs/config-first.
- Tell agents to read `agent-docs/README.md`.
- Point to `agent-docs/rules/common-mistakes.md`, even though Step 2 creates it.
- State that browser actions with publishing, signup, credentials, payments, submissions, account changes, or irreversible effects require explicit permission.
- Tell agents to follow implementation plans and step files when present.

`agent-docs/README.md` must:

- Explain the directory map.
- State canonical docs take precedence over provider bundles.
- Explain where rules, workflows, skills, memory, handoffs, provider bundles, validation, and browser docs live.

The `README.md` files in subdirectories should be short orientation files, not full implementations.

## Do Not

- Do not create final rules yet.
- Do not create provider-specific bundles yet.
- Do not copy browser-harness code yet.
- Do not add runtime dependencies.
- Do not create a CLI or package.

## Verification

Run structure checks:

```bash
find agent-docs -maxdepth 2 -type d | sort
find agent-docs -maxdepth 2 -type f | sort
test -f AGENTS.md
```

Manual inspection:

- Confirm `AGENTS.md` points to `agent-docs/README.md`.
- Confirm `AGENTS.md` points to `agent-docs/rules/common-mistakes.md`.
- Confirm no provider bundle implementation was created.

Report verification level as `Structure checked`.

## Stop And Ask

Ask the user before:

- Initializing git.
- Changing the canonical tree.
- Adding scripts, packages, or runtime dependencies.

