# Release Checklist

Use this checklist before packaging, exporting, or handing off Oden as a usable instruction bundle.

## Scope And State

- [ ] Confirm the release scope: local scaffold, provider bundle export, example package, or final handoff.
- [ ] Confirm `agent-docs/README.md` build state matches the completed steps.
- [ ] Confirm `agent-docs/memory/session-log.md` records durable completed-step context.
- [ ] Confirm `agent-docs/memory/open-questions.md` is current.
- [ ] Confirm unfinished work has a handoff under `agent-docs/handoffs/`.

## Secrets And Sensitive Data

- [ ] No credentials, API keys, tokens, cookies, private keys, or recovery codes are present.
- [ ] No private account data or authenticated session details are present.
- [ ] Browser evidence does not expose secrets or private user data unless the user explicitly approved it for that task.
- [ ] Provider bundles do not instruct agents to paste secrets into global configuration.

## Generated Clutter

- [ ] No generated reference tree was copied into the scaffold unintentionally.
- [ ] No temporary logs, cache files, screenshots, browser profiles, package locks, or dependency folders are included unless they are intentional release artifacts.
- [ ] No runtime dependency files were added unless the current step explicitly allowed them and they remain optional.
- [ ] No unrelated local experiment files are included.

## License And Provenance

- [ ] Copied or closely adapted material has provenance noted in the relevant doc or release notes.
- [ ] Reference material from GIVERNY is treated as allowed by the project decision, but copied architecture or phrasing should still be attributed when substantial.
- [ ] Browser-harness reference ideas are adapted narrowly unless executable code is explicitly approved.
- [ ] Provider docs are cited by source URL and checked date when provider-specific claims are changed.
- [ ] Required license files or notices are preserved if substantial third-party material is copied.

## Provider Readiness

- [ ] Provider bundle checklists pass for Codex, Claude Code, Cursor, Hermes/LM Studio, and ChatGPT.
- [ ] Provider claims are either current-docs verified or clearly marked as needing re-check.
- [ ] Copy/export instructions are complete enough for a user to install manually.
- [ ] Permission gates are preserved in every exported provider bundle.

## Browser Readiness

- [ ] Browser checklist passes.
- [ ] Browser usage remains guarded research/testing guidance.
- [ ] Permission stops are clear for publish, signup, credentials, payments, messages, account changes, deletion, uploads, accepting terms, and irreversible or external effects.

## Final Handoff

- [ ] Final handoff states completed steps.
- [ ] Final handoff lists changed files or directories.
- [ ] Final handoff lists verification commands and results.
- [ ] Final handoff names known gaps and open questions.
- [ ] Final handoff gives the next recommended action.
- [ ] Final response reports the actual verification level reached.

## Suggested Commands

```bash
find . -maxdepth 4 -type f -not -path './references/*' | sort
rg -n "TODO|OPEN|secret|token|cookie|credential|license|provenance|handoff|permission" AGENTS.md agent-docs implementation-plan
```
