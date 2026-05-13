# Step 2: Core Rules And Memory

## Goal

Create canonical rules and memory files that every provider bundle will reference.

## Prerequisite

Step 1 must be complete.

## Scope

Create or fill:

```text
agent-docs/rules/
  agent-behavior.md
  safety-permissions.md
  verification.md
  common-mistakes.md
  code-quality.md
  browser-safety.md
agent-docs/memory/
  decisions.md
  open-questions.md
  session-log.md
```

## Source Material

Use:

- `references/rules/*.mdc`
- `implementation-plan/01-reference-synthesis.md`
- `implementation-plan/02-product-decisions.md`
- `implementation-plan/03-target-architecture.md`

## Content Requirements

`agent-behavior.md`:

- Clear, concise collaboration.
- Read before editing.
- Distinguish observed, inferred, and assumed facts.
- Preserve user changes.
- Keep scope tight.

`safety-permissions.md`:

- Forbidden/destructive command policy.
- Permission gates.
- Secrets and credentials handling.
- Irreversible action policy.

`verification.md`:

- Verification levels from `implementation-plan/04-step-protocol.md`.
- Exact command/result reporting.
- No fake test claims.
- Failed verification handling.

`common-mistakes.md`:

- Stable location for avoidable mistakes.
- Initial entries from the reference mistakes log, rewritten for Oden.
- A template for new mistake entries.

`code-quality.md`:

- Lint zero-tolerance.
- No silent failures.
- Comments explain why, not obvious what.
- Python guidance only when Python exists in the target project.

`browser-safety.md`:

- Browser research/testing defaults.
- Explicit permission-required actions.
- Auth-wall behavior.
- Evidence and screenshot verification expectations.

Memory files:

- `decisions.md` starts with locked decisions from Phase 1.
- `open-questions.md` starts empty or with provider docs verification as an open item.
- `session-log.md` explains when to add entries.

## Do Not

- Do not create provider-specific variants here.
- Do not bury common mistakes in another folder.
- Do not weaken the browser permission policy.
- Do not add implementation plans for unrelated languages or frameworks.

## Verification

Run:

```bash
test -f agent-docs/rules/common-mistakes.md
rg -n "common-mistakes|permission|verification|silent|browser" agent-docs/rules agent-docs/memory
```

Manual inspection:

- Confirm every rule file is provider-neutral.
- Confirm every provider-relevant rule points to canonical Oden docs rather than provider-only locations.
- Confirm browser permission gates are explicit.

Report verification level as `Structure checked` unless additional checks are run.

## Stop And Ask

Ask the user before:

- Moving common mistakes away from `agent-docs/rules/common-mistakes.md`.
- Relaxing permission requirements.
- Adding mandatory dependencies or runtime behavior.

