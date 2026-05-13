# Step 4: Skill System

## Goal

Create provider-neutral Oden skills and a template that can later be adapted into provider-specific skill formats.

## Prerequisite

Steps 1 through 3 must be complete.

## Scope

Create or fill:

```text
agent-docs/skills/
  skill-template.md
  codebase-locator.md
  codebase-analyzer.md
  web-researcher.md
  browser-researcher.md
  provider-bundle-maintainer.md
```

## Skill Model

An Oden skill is a small, durable instruction file with:

- Name.
- When to use it.
- Inputs expected.
- Procedure.
- Safety rules.
- Output format.
- Verification.
- Stop conditions.

Skills should be reusable across providers. Provider-specific exports may convert them later.

## Source Material

Use:

- GIVERNY codebase locator, codebase analyzer, websearcher, and meta-agent patterns.
- Browser-harness skill and domain-skill patterns.
- Oden rules from Step 2.

## Required Skills

`codebase-locator.md`:

- Finds where relevant code/docs live.
- Read-only by default.
- Outputs paths and short reasons.
- Does not analyze deeply or propose fixes.

`codebase-analyzer.md`:

- Explains how selected code/docs work.
- Read-only by default.
- Outputs data flow, contracts, risks, and confidence.
- Does not implement.

`web-researcher.md`:

- Uses current external sources when facts may have changed.
- Prefers primary sources.
- Records links, dates, and confidence.
- Separates source facts from inference.

`browser-researcher.md`:

- Uses browser only when page interaction, visual confirmation, auth state, or dynamic content is needed.
- Follows browser permission gates.
- Records screenshots/page-state evidence where relevant.

`provider-bundle-maintainer.md`:

- Verifies current provider conventions before changing bundles.
- Keeps canonical docs as source of truth.
- Avoids provider-specific drift.

## Do Not

- Do not create autonomous subagent requirements.
- Do not assume a provider supports a specific skill mechanism.
- Do not copy domain-specific browser skills wholesale unless they are needed for Oden.

## Verification

Run:

```bash
find agent-docs/skills -maxdepth 1 -type f | sort
rg -n "When to use|Procedure|Output|Verification|Stop" agent-docs/skills
```

Manual inspection:

- Confirm every skill has safety and output expectations.
- Confirm skills are provider-neutral.
- Confirm browser skill requires permission for restricted actions.

Report verification level as `Structure checked`.

## Stop And Ask

Ask the user before:

- Adding provider-only skill formats in this step.
- Creating a large library of domain skills.
- Requiring subagents or parallel delegation as a baseline behavior.

