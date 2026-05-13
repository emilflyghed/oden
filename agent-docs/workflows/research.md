# Research Workflow

Research maps what is true before an agent plans or implements. It must not silently become implementation.

## When To Use

Use this workflow when:

- The agent needs to understand existing files, code, docs, references, or provider behavior.
- The user asks for investigation, comparison, review, or discovery.
- Facts may be current, external, visual, or dependent on a dynamic page.
- A future plan needs reliable sources and explicit assumptions.

## Procedure

1. State the research question and scope.
2. Read local canonical docs first: `AGENTS.md`, `agent-docs/README.md`, relevant rules, and relevant task docs.
3. Inspect relevant local files before drawing conclusions.
4. Use web or browser research only when local context is insufficient or the facts may have changed.
5. Record sources as paths, commands, URLs, or browser evidence.
6. Separate observed facts from inferences and assumptions.
7. List open questions and confidence.
8. Stop before editing implementation files unless the user explicitly changes the task to implementation.

## Output Format

```markdown
# Research: Short Topic

## Question

What was researched.

## Scope

What was included and excluded.

## Sources

- Local file, command, URL, or browser evidence.

## Findings

- Observed fact.

## Inferences

- Reasoned conclusion based on findings.

## Open Questions

- Unknown that affects planning or implementation.

## Confidence

High, medium, or low, with a short reason.
```

## Stop Conditions

Stop and ask the user before:

- Expanding research into implementation.
- Relying on unverifiable external claims for an architectural decision.
- Crossing browser permission gates.
- Adding dependencies, changing runtime assumptions, or changing canonical Oden structure.

