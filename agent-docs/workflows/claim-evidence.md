# Claim Evidence Workflow

Use this workflow when correctness depends on a factual claim, external source, provider behavior, architecture decision, browser observation, or failed-verification conclusion.

The goal is to force important claims to carry evidence instead of relying on confidence alone.

## Claim/Evidence Matrix

```markdown
| Claim | Evidence | Confidence | Verification | Risk |
| --- | --- | --- | --- | --- |
| What is believed true | File path, command, URL, source, or browser evidence | High/Medium/Low | Inspection, structure check, provider check, behavior check, or not run | What could be wrong or stale |
```

## When Required

Use a claim/evidence matrix for:

- Provider-specific file names, config paths, or feature claims.
- External facts that may change.
- Architecture decisions or tradeoffs.
- Browser findings.
- Security, credential, payment, publishing, or destructive-action claims.
- Failed verification conclusions.
- Any claim that another agent will rely on later.

## Evidence Rules

- Prefer direct local files, command output, official docs, or observed browser state.
- Separate observed fact from inference.
- Mark stale or unchecked provider claims as uncertain.
- Do not cite chat memory as evidence.
- Do not claim behavior was tested unless it was actually executed.

## Confidence Guide

- `High`: direct source or command supports the claim, and the source is current enough for the task.
- `Medium`: source supports the claim, but scope, freshness, or environment limits remain.
- `Low`: partial evidence only; do not use for high-impact decisions without more research or user confirmation.

## Storage

For short tasks, include the matrix in the final response or active notes.

For resumable work, include it in a checkpoint, handoff, research doc, or task-specific file under `agent-docs/`.
