# Web Researcher

## Name

web-researcher

## When to use

Use this skill for current or external facts that cannot be verified from local files alone.

Use this skill when:

- Provider conventions may have changed.
- API, framework, product, legal, pricing, model, or documentation details may be current.
- The user asks to look something up or verify a source.
- Local references are insufficient or stale.

Do not use this skill when local files already answer the question and the fact is stable.

## Inputs expected

- One clear research question.
- Preferred source type, if any.
- Date sensitivity or version constraints.
- Any domains the user requires or forbids.

## Procedure

1. Answer one question at a time.
2. Prefer primary sources: official docs, release notes, standards, canonical repositories, or vendor pages.
3. Use recent sources when the fact is time-sensitive.
4. Cross-check when the first source is ambiguous, unofficial, or conflicts with local assumptions.
5. Record source URLs and access dates when relevant.
6. Separate source facts from agent inference.
7. If reliable sources cannot be found, say so directly.

## Safety rules

- Do not fabricate URLs or citations.
- Do not use unofficial sources as definitive when primary sources are available.
- Do not browse into account, credential, purchase, or signup flows without user permission.
- Respect provider-specific documentation requirements from the active environment.

## Output format

```markdown
# Web Research: Question

## Answer

Direct answer in 1-3 sentences.

## Sources

- URL - What it supports.

## Source Facts

- Fact from source.

## Inference

- Any conclusion drawn from the facts, or "None".

## Confidence

High, medium, or low, with a reason.

## Caveats

- Version, date, or reliability limitation, or "None".
```

## Verification

- Include the URLs used.
- State if sources were primary or secondary.
- State if the information is date-sensitive.

## Stop conditions

Stop and ask before:

- Making a provider architecture change based on conflicting docs.
- Continuing when only low-confidence sources are available for a high-impact decision.
- Crossing browser or credential permission gates.

