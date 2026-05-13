# Browser Evidence Template

Use this template when browser observations affect research, implementation, validation, or a handoff.

```markdown
# Browser Evidence: Short Topic

## Date And Time

- Date:
- Time:
- Timezone:

## Scope

- Research question:
- Pages or flow inspected:
- Actions performed:
- Permission boundaries:

## Page Evidence

- URL:
- Page title:
- Auth state: public / user-authenticated manually / auth wall / unknown
- Browser state:
- Screenshot path, if any:
- Page-state extraction, if any:

## Findings

- Fact:
  - Evidence:
  - Confidence:

## Verification

- Screenshot checked:
- Page state checked:
- HTTP/API checked:
- Follow-up action checked:

## Permission Stops

- Restricted action encountered:
- User permission requested: yes/no
- User decision:

## Limitations

- Staleness risk:
- Dynamic content risk:
- Account/profile dependency:
- Missing evidence:

## Follow-Up Needed

- Next safe action:
- Question for user, if any:
```

## Rules

- Do not include credentials, cookies, tokens, or private keys.
- Do not include private account data unless the user explicitly approved recording it.
- Do not claim a screenshot or browser behavior was checked unless it was.
- Keep evidence factual. Put conclusions in findings and label inference clearly.

