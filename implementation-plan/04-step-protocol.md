# Step Protocol

This protocol controls Phase 2 implementation.

## When The User Says `Start step X`

The agent must:

1. Open `implementation-plan/README.md`.
2. Open this file.
3. Open `implementation-plan/steps/XX-*.md`.
4. Confirm the step scope in one or two sentences.
5. Inspect the current workspace before editing.
6. Make only the changes described by the step.
7. Run the verification listed by the step.
8. Update any required implementation log or memory files described by the step.
9. Stop with a concise summary, changed files, verification, and open questions.

## Scope Control

Do not combine steps unless the user explicitly asks.

If a step reveals that a previous step is incomplete, fix only the missing prerequisite needed for the current step and report it clearly.

If a later step would be easier to do now, do not do it. Record the observation in the appropriate memory or handoff file.

## Editing Rules

- Read before editing.
- Keep changes scoped.
- Avoid unrelated refactors.
- Preserve user changes.
- Use existing files and conventions once they exist.
- Do not create provider-specific content that conflicts with canonical Oden docs.

## Verification Levels

Every final response must say which verification level was reached:

- `Not run`: no verification command or inspection was performed.
- `Inspected`: files were read and checked manually.
- `Structure checked`: expected files/links/headings were checked.
- `Provider checked`: provider bundle was checked against current provider docs or local references.
- `Behavior checked`: an executable helper, browser workflow, or example was actually run.

Do not call a level higher than what was actually done.

## Required Stop Points

Stop and ask the user before:

- Destructive git or filesystem operations.
- Changing the scaffold from docs/config-first to runtime-first.
- Adding mandatory external dependencies.
- Publishing, submitting, signing up, making payments, entering credentials, or making irreversible browser changes.
- Copying large source trees from references instead of adapting narrow parts.
- Removing or moving canonical memory/rule locations.
- Changing the step sequence.

## Handoff Requirement

If the agent cannot finish a step in the current session, it must create or update a handoff with:

- Step number.
- Completed work.
- Remaining work.
- Current files changed.
- Commands run.
- Known failures.
- Next action.

The target Phase 2 location is `agent-docs/handoffs/`.

If that directory does not exist yet, create a temporary handoff under `implementation-plan/handoffs/` and move the pattern into the scaffold once Step 1 creates the canonical tree.

## Common Mistakes

If the agent makes an avoidable mistake during Phase 2, it must update `agent-docs/rules/common-mistakes.md` once that file exists.

Before that file exists, record the mistake in the final response and add it during Step 2.

