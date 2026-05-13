# Oden Tool Policy For Hermes / LM Studio

## Default Tool Posture

Prefer read-only tools first:

- File search and read.
- Web search and extraction.
- Static inspection.
- Safe screenshots or page-state checks.

Use write, terminal, browser, messaging, code execution, delegation, or patch tools only when the user request and current Oden step justify them.

## Permission Required

Ask the user before:

- Destructive filesystem operations.
- Destructive git or history operations.
- Shell commands that modify broad parts of the system.
- File writes outside the active task scope.
- Publishing, sending, submitting, deleting, or committing externally visible information.
- Signing up, entering credentials, crossing auth walls, making payments, changing settings, accepting terms, uploading files, or irreversible browser actions.
- Messaging platform sends.
- Tool calls that may incur cost or use cloud/browser infrastructure.
- Adding mandatory dependencies or turning Oden into a runtime-first system.

## Code Execution

Hermes `execute_code` can collapse multi-step tool work into one script. Use it only when it materially reduces context or improves determinism.

Rules:

- Print only the final useful summary.
- Do not hide intermediate failures.
- Do not use code execution to bypass permission gates.
- Do not read secrets or private files unless the user explicitly approves.
- Prefer read-only processing unless mutation is in scope.

## Browser Actions

Follow `agent-docs/rules/browser-safety.md`.

Allowed by default: public research, inspection, screenshots, and safe testing.

Requires permission: publishing, signup, credentials, payments, messages, settings changes, deletion, accepting terms, uploads, or irreversible/external actions.

## Verification

Report the exact tools used and results observed. Use Oden verification levels from `agent-docs/rules/verification.md` and choose checks with `agent-docs/validation/verification-matrix.md`.

If a tool call or check fails, use `agent-docs/workflows/failure-recovery.md`: record the failure, classify it, decide whether recovery is in scope, and retry only with a clear reason.
