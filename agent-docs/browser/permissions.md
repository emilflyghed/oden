# Browser Permissions

Browser access in Oden is a guarded research and testing capability. It must not become an autonomous publishing, signup, purchasing, credential-entry, messaging, or account-management system.

## Allowed By Default

Agents may use browser access to:

- Open public pages.
- Search and read public information.
- Inspect dynamic pages.
- Capture screenshots for evidence.
- Read page state and visible UI.
- Use HTTP/API access for static public data when sufficient.
- Try Oden workflows in browser-based tools when no irreversible or externally visible action occurs.
- Verify after safe navigation, scrolling, opening menus, or reading public content.

Use the least invasive method that answers the question. Prefer HTTP, official docs, or static page inspection when a full browser is unnecessary.

## Explicit Permission Required

Stop and ask for explicit user permission before:

- Publishing or submitting information.
- Signing up for accounts.
- Entering credentials.
- Making purchases or payments.
- Sending messages.
- Changing account settings.
- Deleting data.
- Accepting terms.
- Uploading files.
- Downloading private or sensitive files.
- Syncing or reusing browser profiles, cookies, or authenticated sessions.
- Starting cloud browser infrastructure or anything that may incur cost.
- Triggering any irreversible or externally visible action.

The permission request must include:

1. The exact browser action.
2. The page, account, or data it may affect.
3. Why the action is needed.
4. The safer alternative, if one exists.

Do not proceed until the user clearly approves that exact action.

## Auth Walls

- Do not type credentials.
- Do not infer credentials from screenshots, password managers, clipboard contents, or files.
- Do not work around authentication, paywalls, bot checks, or account restrictions.
- Stop and ask the user when an auth wall appears.
- If the user chooses to authenticate manually, wait for the user to confirm they are done before continuing.
- After manual authentication, continue only with the approved research/testing scope.

## Browser Profiles And Cookies

Treat browser profiles, cookies, local storage, and session tokens as sensitive.

- Do not copy, export, sync, print, or store them without explicit permission.
- Do not include them in evidence, handoffs, logs, provider bundles, or examples.
- If a browser tool offers profile sync or cloud profiles, ask before using it.

## Remote Or Cloud Browsers

Remote or cloud browser usage requires explicit permission before setup or launch.

The request must mention:

- Provider or tool.
- Whether billing or quotas may be affected.
- Whether profile state, cookies, or authentication may persist.
- How the session will be stopped or cleaned up.

## Failure And Blocker Handling

If a page blocks access, requires auth, asks for payment, opens a submission flow, or displays a destructive confirmation, stop and report the blocker. Do not click through to see what happens.

