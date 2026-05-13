# Site Skill Template

Use this template for durable site-specific browser knowledge.

Site skills are maps, not diaries. They should help future agents interact safely with a site without repeating discovery work.

## Site

- Name:
- Hostname:
- Purpose:
- Last verified:

## When To Use

- Task or research scenario where this site skill applies.

## Public URLs And Entry Points

- URL or path:
- What it is for:
- Auth required: yes/no/unknown.

## Public API Or HTTP Notes

- Endpoint:
- Method:
- Useful parameters:
- Response shape:
- When to prefer this over browser interaction:

Only document public or user-approved endpoints.

## Interaction Notes

- Stable selectors, labels, or landmarks:
- Menus or dialogs:
- Search, filter, pagination, or sorting behavior:
- Loading, delay, or dynamic rendering notes:
- Screenshot/page-state verification needed:

Prefer stable labels, selectors, URLs, and state descriptions over pixel coordinates.

## Permission-Sensitive Actions

List actions that require explicit permission on this site:

- Publishing/submitting:
- Signup:
- Credentials/auth:
- Payment/purchase:
- Messaging:
- Account settings:
- Deletion:
- Upload/download sensitive data:
- Accepting terms:
- Other irreversible or externally visible actions:

## Auth-Wall Behavior

- What indicates an auth wall:
- What the agent may inspect before stopping:
- What the agent must ask the user:

Do not record credentials, cookies, tokens, private account data, or instructions for bypassing auth.

## Evidence Requirements

- Required URL:
- Required screenshot:
- Required page-state or extracted text:
- Timestamp needed: yes/no.
- Confidence criteria:

## Known Gotchas

- Durable issue:
- How to recognize it:
- Safe workaround:

## Do Not Record

- Secrets.
- Credentials.
- Cookies or tokens.
- Private account data.
- One-off task narration.
- Brittle pixel coordinates.
- Instructions to bypass restrictions.

