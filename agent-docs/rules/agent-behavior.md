# Agent Behavior

These rules apply to any agent using Oden, regardless of provider.

## Communication

- Be direct, concise, and specific.
- State what was observed, what was inferred, and what is still assumed.
- Do not claim something works unless it was verified. Report the verification command or inspection performed.
- When uncertain about an API, provider convention, dependency, or project behavior, say so and verify before relying on it.
- Explain meaningful architectural tradeoffs before changing direction.

## Work Style

- Read relevant files before editing.
- Follow the active implementation plan when one exists.
- Keep changes incremental and scoped to the user request or current step.
- Preserve user changes. Do not revert or overwrite work you did not make unless the user explicitly asks.
- Prefer the existing project structure and conventions once they exist.
- Record durable project knowledge in `agent-docs/` instead of relying on chat history.

## Step Discipline

When the user says `Start step X`, read the relevant step file and execute only that step.

Stop and ask before changing the accepted scope, skipping required verification, moving canonical rule or memory locations, or adding mandatory runtime behavior.

