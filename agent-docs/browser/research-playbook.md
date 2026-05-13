# Browser Research Playbook

Use browser research when public web search, local files, or direct HTTP are not enough.

## When Browser Use Is Justified

Use a browser when:

- The page is dynamic and cannot be understood from static HTML.
- Visual state, layout, screenshots, or UI interaction matters.
- A workflow needs safe browser-based testing.
- A page requires JavaScript-rendered content.
- The user has manually authenticated and confirmed that the agent may continue inside the approved scope.

Do not use a browser when:

- Official docs or local files already answer the question.
- Static HTTP or API access is sufficient.
- The next action is permission-gated and the user has not approved it.

## Research Procedure

1. Read `agent-docs/rules/browser-safety.md` and `agent-docs/browser/permissions.md`.
2. State the browser research question and scope.
3. Prefer official docs, HTTP/API, or static reading first when practical.
4. Open only pages relevant to the task.
5. Use screenshots or page state to understand dynamic/visual content.
6. After every meaningful safe action, verify the visible or page-state result.
7. Record evidence with `agent-docs/browser/evidence-template.md`.
8. Stop at auth walls, payment prompts, signup flows, submission flows, destructive dialogs, or externally visible actions.

## Evidence Requirements

Record:

- URL.
- Date/time when the observation may become stale.
- Browser state or visible result.
- Screenshot path if one was captured.
- Extracted facts.
- Confidence.
- Limitations and follow-up needed.

If evidence affects future work, write it under `agent-docs/`, the active task notes, or a handoff. Do not rely on chat memory.

## Dynamic Page Handling

- Wait for loading or visible state before drawing conclusions.
- Prefer screenshots for visual claims.
- Prefer DOM/page-state extraction for text-heavy or hidden data claims.
- Verify that clicks, menu opens, filters, or navigation changed the expected state.
- Treat popups, modals, cookie banners, and dialogs as page state that must be recorded if they affect the result.

## Safe Interaction Defaults

Allowed without extra permission when in scope:

- Navigate to public pages.
- Scroll.
- Open non-destructive menus.
- Read public content.
- Capture screenshots.
- Copy public URLs or public text into evidence.

Requires permission:

- Any action listed in `agent-docs/browser/permissions.md`.

## Site Skills

If the task reveals stable site-specific knowledge, add a durable site skill using `site-skill-template.md`.

Site skills should capture:

- Stable URL patterns.
- Public endpoints.
- Robust selectors or interaction notes.
- Known gotchas.
- Permission-sensitive actions.
- Last verified date.

Do not record secrets, cookies, task diaries, brittle pixel coordinates, or one-off narration.

## Reporting

Use this shape:

```markdown
# Browser Research: Topic

## Scope

Pages and actions inspected.

## Evidence

- URL:
- Date/time:
- Screenshot path, if any:
- Page state:

## Findings

- Fact supported by evidence.

## Permission Stops

- Restricted action encountered, or "None".

## Confidence And Limits

Confidence level and why.
```

