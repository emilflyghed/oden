# Step 3: Workflow Protocol

## Goal

Create Oden's provider-neutral workflow protocols for research, planning, implementation, validation, checkpoints, handoffs, and `Start step X`.

## Prerequisite

Steps 1 and 2 must be complete.

## Scope

Create or fill:

```text
agent-docs/workflows/
  research.md
  plan.md
  implement.md
  validate.md
  checkpoint.md
  handoff.md
  start-step.md
```

## Source Material

Use:

- GIVERNY research, plan, implement, commit/status, and handoff ideas.
- LangGraph-inspired state, checkpoint, interrupt, and routing ideas.
- `implementation-plan/04-step-protocol.md`.

## Content Requirements

`research.md`:

- Research maps existing facts and code.
- Research must not silently become implementation.
- Research docs should include sources, confidence, and open questions.

`plan.md`:

- Plans must be step-based, scoped, verifiable, and resumable.
- Plans must list assumptions and stop points.
- Plans must be revised when user decisions change.

`implement.md`:

- Follow the accepted plan.
- Keep each step atomic.
- Record deviations and ask before architecture changes.
- Preserve user edits.

`validate.md`:

- Explain verification levels.
- Require exact commands and results.
- Require residual risk reporting.

`checkpoint.md`:

- Define checkpoint fields.
- Explain when to create one.
- Distinguish checkpoint from long-term memory.

`handoff.md`:

- Define handoff format.
- Explain when to create handoffs.
- Include a template.

`start-step.md`:

- Explain how agents respond to `Start step X`.
- Reference `implementation-plan/README.md` while this project is being built.
- Define what to do after Oden is installed in another project.

## Do Not

- Do not make these workflows provider-specific.
- Do not require a graph runtime.
- Do not create Claude-only slash command content yet.

## Verification

Run:

```bash
find agent-docs/workflows -maxdepth 1 -type f | sort
rg -n "checkpoint|handoff|Start step|verification|research|plan|implement" agent-docs/workflows
```

Manual inspection:

- Confirm all workflows are provider-neutral.
- Confirm user-interrupt conditions are included.
- Confirm the workflows are actionable without a runtime.

Report verification level as `Structure checked`.

## Stop And Ask

Ask the user before:

- Requiring LangGraph or another runtime.
- Changing the workflow phase model.
- Removing the `Start step X` protocol.

