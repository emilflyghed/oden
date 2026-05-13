# Plan Workflow

Planning turns known facts into scoped, verifiable, resumable work.

## When To Use

Use this workflow when:

- The user asks for a plan.
- A task is large enough to exceed one safe implementation pass.
- Work needs to be split into `Start step X` sessions.
- Architecture, provider behavior, browser behavior, or validation strategy needs agreement before editing.

## Plan Requirements

A plan must be:

- Step-based.
- Scoped to clear files or responsibilities.
- Verifiable with explicit checks.
- Resumable by another agent.
- Clear about assumptions and unknowns.
- Clear about stop points requiring user confirmation.
- Aligned with canonical Oden docs in `agent-docs/`.

## Procedure

1. Read the relevant research, decisions, open questions, rules, and current files.
2. Define the goal and non-goals.
3. List assumptions and unresolved questions.
4. Split work into atomic steps.
5. For each step, define scope, files, success criteria, verification, and stop points.
6. Include handoff expectations for incomplete work.
7. Ask the user to confirm decisions that affect architecture, permissions, provider support, or runtime assumptions.
8. Revise the plan when user decisions change.

## Step Template

```markdown
# Step N: Short Name

## Goal

What this step accomplishes.

## Scope

Files or directories this step may change.

## Do Not

Boundaries for this step.

## Verification

Commands, inspections, or behavior checks required.

## Stop And Ask

Conditions that require user confirmation.
```

## Stop Conditions

Stop and ask before:

- Changing the accepted phase or step sequence.
- Making a docs/config scaffold depend on a runtime.
- Weakening permission gates.
- Removing canonical memory or rule locations.
- Making provider-specific instructions canonical.

