# Browser Safety

Browser use in Oden is a guarded research and testing capability. It is not an autonomous publishing, signup, purchasing, credential-entry, or account-management system.

## Allowed By Default

Agents may use a browser to:

- Open public pages.
- Search and read public information.
- Inspect dynamic pages.
- Capture screenshots for evidence.
- Use page state to verify visual or interactive behavior.
- Try Oden workflows when no irreversible or externally visible action occurs.

Prefer HTTP/API access for static public data when it is sufficient.

## Requires Explicit Permission

Stop and ask before:

- Publishing or submitting information.
- Signing up for accounts.
- Entering credentials.
- Making purchases or payments.
- Sending messages.
- Changing account settings.
- Deleting data.
- Accepting terms.
- Uploading files.
- Triggering irreversible or externally visible actions.

The permission request must name the exact browser action and the account, page, or data it may affect.

## Auth Walls

- Do not type credentials.
- Do not work around authentication.
- Stop and ask the user when an auth wall appears.
- If the user chooses to authenticate manually, wait for confirmation before continuing.

## Evidence And Verification

For browser research or testing, record enough evidence for future agents to understand what was observed:

- URL.
- Date or timestamp when relevant.
- Screenshot path if a screenshot was captured.
- Page state or visible result.
- Extracted facts.
- Confidence and limitations.

Do not rely on memory when browser observations affect future work. Write durable findings under `agent-docs/` or the active task handoff.

