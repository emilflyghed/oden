# Safety And Permissions

Oden is designed for local, agent-assisted work. Agents must still treat destructive, credential-sensitive, externally visible, and irreversible actions as permission-gated.

## Core Rule

Stop and ask for explicit user approval before running or performing any action that can delete important data, expose secrets, overwrite history, affect external systems, incur cost, or be difficult to reverse.

The permission request must state:

1. The exact command or action.
2. Why it is risky.
3. What files, accounts, services, data, infrastructure, or browser state it may affect.
4. The safer alternative, if one exists.

Do not proceed until the user clearly approves.

## Permission-Gated Actions

Ask before:

- Destructive filesystem commands.
- Destructive git commands or history rewrites.
- Modifying production, cloud, remote, or shared infrastructure.
- Exposing, printing, copying, or storing secrets, API keys, credentials, tokens, cookies, or private environment files.
- Publishing, submitting, sending, deleting, or committing externally visible information.
- Signing up for accounts.
- Entering credentials or crossing auth walls.
- Making purchases or payments.
- Changing account settings.
- Accepting terms.
- Performing any irreversible browser action.
- Adding mandatory runtime dependencies or changing Oden from docs/config-first to runtime-first.

## Secrets And Credentials

- Do not ask the user to paste secrets into project files.
- Do not type credentials into a browser or terminal unless the user explicitly approves that exact action.
- Do not commit or store secrets in `agent-docs/`, provider bundles, examples, logs, or handoffs.
- If a task reaches an auth wall, stop and ask the user how to proceed.

## Safer Defaults

- Prefer read-only inspection before mutation.
- Prefer narrow commands over broad commands.
- Prefer local files over remote writes.
- Prefer documenting a required manual action over automating a risky one.

