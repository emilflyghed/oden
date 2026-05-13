# Browser Researcher

## Name

browser-researcher

## When to use

Use this skill when research requires browser interaction, visual confirmation, dynamic page state, authenticated state controlled by the user, or screenshots.

Use this skill when:

- Static HTTP or web search is insufficient.
- The page is rendered dynamically.
- Visual layout or UI state matters.
- A browser-based Oden workflow needs safe testing.
- The user has manually authenticated and confirmed the agent may continue.

Do not use this skill for simple static pages that can be read through HTTP or web search.

## Inputs expected

- Target URL or research question.
- Whether authentication is expected.
- Evidence requirements such as screenshot, visible state, extracted text, or timestamp.
- Permission limits for the session.

## Procedure

1. Read `agent-docs/rules/browser-safety.md`.
2. Prefer non-browser HTTP or official docs when sufficient.
3. Open public pages for research or safe testing.
4. Use screenshots or page state to understand visible behavior.
5. After every meaningful interaction, verify the page state changed as expected.
6. Record evidence: URL, date or timestamp, screenshot path if any, observed state, extracted facts, confidence, and limits.
7. Stop at auth walls or restricted actions.

## Safety rules

- Browser work is research/testing only by default.
- Do not publish, submit, sign up, enter credentials, pay, purchase, send messages, change settings, delete data, accept terms, upload files, or trigger externally visible or irreversible actions without explicit user permission.
- Do not type credentials.
- If the user authenticates manually, wait for their confirmation before continuing.
- Do not store cookies, tokens, credentials, or private browser state in docs.

## Output format

```markdown
# Browser Research: Topic

## Scope

What page or flow was inspected.

## Evidence

- URL:
- Date/time:
- Screenshot path, if any:
- Page state observed:

## Findings

- Fact supported by browser evidence.

## Verification

- Page state, screenshot, or command used to verify.

## Permission Stops

- Restricted action encountered, or "None".

## Confidence

High, medium, or low, with a reason.
```

## Verification

- Use screenshot or page-state evidence for visual/dynamic claims.
- State when only static reading was performed.
- Report any interaction and its observed result.

## Stop conditions

Stop and ask before:

- Any restricted browser action.
- Auth walls or credential entry.
- Cloud/browser infrastructure that may incur cost.
- Copying or storing sensitive browser data.

