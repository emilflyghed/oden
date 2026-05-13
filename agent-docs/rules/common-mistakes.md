# Common Mistakes

This is Oden's stable common mistakes file.

Path:

```text
agent-docs/rules/common-mistakes.md
```

Agents must check this file before starting substantial work and update it when they make an avoidable mistake that future agents should not repeat.

## Current Entries

### M-000: Using The Reference Mistakes Path Instead Of Oden's Path

- Mistake: The upstream reference points to `.agent/rules/common-mistakes.mdc`, but Oden's canonical location is `agent-docs/rules/common-mistakes.md`.
- Consequence: Future agents may miss project-specific lessons if mistakes are recorded in the wrong location.
- Correct behavior: Always read and update `agent-docs/rules/common-mistakes.md` for Oden projects.

### M-001: Claiming Verification That Was Not Performed

- Mistake: Saying work is tested or working after only reading files.
- Consequence: The user receives false confidence and future agents inherit unreliable state.
- Correct behavior: Report the exact verification level reached and list the commands or checks actually run.

### M-002: Letting Provider Bundles Become The Source Of Truth

- Mistake: Updating provider-specific instructions without updating canonical Oden docs.
- Consequence: Provider behavior drifts and agents receive conflicting instructions.
- Correct behavior: Keep canonical rules, workflows, skills, and memory under `agent-docs/`; provider bundles are adapters.

### M-003: Retrying Without Diagnosis

- Mistake: Re-running a failed command or check without recording the failure, classifying the cause, or changing the retry meaningfully.
- Consequence: The agent wastes context, hides the real blocker, and may make random out-of-scope changes.
- Correct behavior: Use `agent-docs/workflows/failure-recovery.md`; record the exact failure, classify it, decide whether the fix is in scope, and retry only when the cause is understood.
- Added: 2026-05-12.

## New Entry Template

```markdown
### M-XXX: Short Mistake Name

- Mistake: What went wrong.
- Consequence: Why it matters.
- Correct behavior: What future agents should do instead.
- Added: YYYY-MM-DD.
```

Only add durable, actionable lessons. Do not use this file as a session diary.
