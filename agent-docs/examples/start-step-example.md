# Start Step Example

Use this pattern when a project includes an implementation plan split into numbered steps.

## User Prompt

```text
Start step 3.
```

## Agent Reads

The agent should read, in order:

1. `AGENTS.md`
2. `agent-docs/README.md`
3. `implementation-plan/README.md`
4. `implementation-plan/04-step-protocol.md`
5. `implementation-plan/steps/03-*.md`
6. Relevant canonical rules, workflows, skills, memory, validation docs, or browser docs named by the step.

If the requested step file is missing, the agent should list available step files and stop before guessing.

## Agent Scope Confirmation

The agent should briefly confirm the step scope before editing:

```text
Step 3 is scoped to workflow protocol docs. I will create or update only the workflow files named by the step, then run the listed verification.
```

## Agent Work Pattern

The agent should:

- Inspect the current workspace before editing.
- Make only the changes described by the step.
- Preserve user changes and avoid unrelated refactors.
- Stop for permission if the step requires it.
- Run the verification commands listed by the step.
- Update memory, handoff, or implementation-log files only when the step asks for it or when durable context needs to be preserved.

## Agent Final Report

The final report should include:

- What changed.
- The main files changed.
- The verification commands run.
- The actual verification level reached.
- Any open questions or follow-up risks.

Example:

```text
Step 3 is complete.

Changed:
- agent-docs/workflows/research.md
- agent-docs/workflows/plan.md
- agent-docs/workflows/implement.md
- agent-docs/workflows/validate.md
- agent-docs/workflows/checkpoint.md
- agent-docs/workflows/handoff.md
- agent-docs/workflows/start-step.md

Verification run:
- find agent-docs/workflows -maxdepth 1 -type f | sort
- rg -n "checkpoint|handoff|verification|permission" agent-docs/workflows

Verification level: Structure checked.
```
