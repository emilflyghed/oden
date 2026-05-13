# Scaffold Checklist

Use this checklist to verify the canonical Oden docs/config scaffold. This is a structure check unless an executable helper or example is actually run.

## Required Root Entrypoints

- [ ] `AGENTS.md` exists at the repository root.
- [ ] `AGENTS.md` tells agents to read `agent-docs/README.md`.
- [ ] `AGENTS.md` links or names `agent-docs/rules/common-mistakes.md`.
- [ ] `AGENTS.md` preserves permission gates for destructive actions, credentials, publishing, payments, browser irreversible actions, and mandatory dependency changes.
- [ ] `agent-docs/README.md` exists and describes the canonical directory map.
- [ ] `agent-docs/README.md` states that canonical docs take precedence over provider bundles.

## Required Directories

- [ ] `agent-docs/rules/`
- [ ] `agent-docs/workflows/`
- [ ] `agent-docs/skills/`
- [ ] `agent-docs/memory/`
- [ ] `agent-docs/handoffs/`
- [ ] `agent-docs/provider-bundles/`
- [ ] `agent-docs/validation/`
- [ ] `agent-docs/browser/`

## Required Rule Files

- [ ] `agent-docs/rules/README.md`
- [ ] `agent-docs/rules/agent-behavior.md`
- [ ] `agent-docs/rules/safety-permissions.md`
- [ ] `agent-docs/rules/verification.md`
- [ ] `agent-docs/rules/common-mistakes.md`
- [ ] `agent-docs/rules/code-quality.md`
- [ ] `agent-docs/rules/browser-safety.md`

Confirm that `common-mistakes.md` is treated as the stable location for avoidable errors and cross-checks.

## Required Workflow Files

- [ ] `agent-docs/workflows/README.md`
- [ ] `agent-docs/workflows/task-intake.md`
- [ ] `agent-docs/workflows/research.md`
- [ ] `agent-docs/workflows/plan.md`
- [ ] `agent-docs/workflows/implement.md`
- [ ] `agent-docs/workflows/validate.md`
- [ ] `agent-docs/workflows/failure-recovery.md`
- [ ] `agent-docs/workflows/review.md`
- [ ] `agent-docs/workflows/checkpoint.md`
- [ ] `agent-docs/workflows/handoff.md`
- [ ] `agent-docs/workflows/claim-evidence.md`
- [ ] `agent-docs/workflows/start-step.md`

Confirm that workflow coverage includes task intake, research, planning, implementation, validation, failure recovery, review, checkpointing, handoff, claim/evidence, and `Start step X`.

## Required Skill Files

- [ ] `agent-docs/skills/README.md`
- [ ] `agent-docs/skills/skill-template.md`
- [ ] `agent-docs/skills/codebase-locator.md`
- [ ] `agent-docs/skills/codebase-analyzer.md`
- [ ] `agent-docs/skills/web-researcher.md`
- [ ] `agent-docs/skills/browser-researcher.md`
- [ ] `agent-docs/skills/provider-bundle-maintainer.md`

Confirm that skills are provider-neutral and point back to canonical rules, workflows, browser safety, and common mistakes when relevant.

## Required Memory And Handoff Files

- [ ] `agent-docs/memory/README.md`
- [ ] `agent-docs/memory/decisions.md`
- [ ] `agent-docs/memory/open-questions.md`
- [ ] `agent-docs/memory/session-log.md`
- [ ] `agent-docs/handoffs/README.md`

Confirm that decisions, open questions, completed-session notes, and incomplete-task handoffs each have a clear home.

## Required Validation And Browser Files

- [ ] `agent-docs/validation/README.md`
- [ ] `agent-docs/validation/scaffold-checklist.md`
- [ ] `agent-docs/validation/provider-checklist.md`
- [ ] `agent-docs/validation/browser-checklist.md`
- [ ] `agent-docs/validation/release-checklist.md`
- [ ] `agent-docs/validation/verification-matrix.md`
- [ ] `agent-docs/browser/README.md`
- [ ] `agent-docs/browser/permissions.md`
- [ ] `agent-docs/browser/research-playbook.md`
- [ ] `agent-docs/browser/site-skill-template.md`
- [ ] `agent-docs/browser/evidence-template.md`
- [ ] `agent-docs/examples/README.md`
- [ ] `agent-docs/examples/start-step-example.md`
- [ ] `agent-docs/examples/provider-install-example.md`
- [ ] `agent-docs/examples/browser-research-example.md`
- [ ] `agent-docs/examples/task-intake-example.md`
- [ ] `agent-docs/examples/failure-recovery-example.md`
- [ ] `agent-docs/examples/review-example.md`

## Canonical Link Checks

- [ ] Root and provider entrypoints point to `agent-docs/README.md`.
- [ ] Rule references point to `agent-docs/rules/`.
- [ ] Common mistake references point to `agent-docs/rules/common-mistakes.md`.
- [ ] Workflow references point to `agent-docs/workflows/`.
- [ ] Skill references point to `agent-docs/skills/`.
- [ ] Memory references point to `agent-docs/memory/`.
- [ ] Handoff references point to `agent-docs/handoffs/`.
- [ ] Browser references point to `agent-docs/browser/`.

## Docs-Only Boundary

- [ ] The core scaffold does not require LangGraph, LangChain, provider SDKs, model API keys, or a runtime.
- [ ] Any helper script, if present later, is optional and not required by provider bundles.
- [ ] Verification reports separate static structure checks from executed behavior checks.

## Suggested Commands

```bash
find agent-docs -maxdepth 2 -type f | sort
rg -n "agent-docs/README.md|common-mistakes|handoff|permission|provider|browser" AGENTS.md agent-docs
```
