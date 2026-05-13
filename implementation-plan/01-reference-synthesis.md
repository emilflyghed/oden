# Reference Synthesis

This synthesis is the design input for Phase 2. It fuses the useful parts of the local references into Oden's own scaffold.

## Local Rules

Use the rules in `references/rules/` as the quality floor:

- Communicate clearly and distinguish observed facts, inferences, and assumptions.
- Read relevant files before editing.
- Keep changes incremental and scoped.
- Treat lint warnings and test failures as blockers.
- Verify with commands or explicit inspection levels; do not call inspection a test.
- Keep persistent agent memory in a known project location.
- Track avoidable mistakes in a common mistakes file.
- Avoid silent failures and broad exception swallowing.
- Require explicit user approval for destructive commands or irreversible actions.
- Prefer modern Python practices when Python is used.

Oden should convert these into provider-neutral markdown under a canonical rules directory, then export provider-specific views.

## GIVERNY

Use GIVERNY's workflow discipline:

- Research, plan, implement, validate, and commit/handoff are distinct modes.
- Artifacts beat memory. Important context must be written down.
- Subtasks should be atomic, scoped, and independently verifiable.
- Agents need explicit role, sandbox, input data, success criteria, and output format.
- Handoffs should happen before context becomes unreliable.
- The orchestrating agent should avoid silent deviations from an approved plan.

Oden should adapt this as a general workflow protocol for any agent, not only Claude Code.

## Browser Harness

Use browser-harness as the model for browser access:

- Keep the browser layer thin and understandable.
- Prefer HTTP/API access for static data and browser access only when needed.
- Connect to a real browser profile only with explicit user awareness.
- Use screenshots and page state to verify meaningful actions.
- Treat site-specific skills as durable maps, not session diaries.
- Do not type credentials or cross auth walls without asking the user.
- Expose raw escape hatches only behind clear safety rules.

For Oden, browser automation is included for research and for trying the project. It must not publish, sign up, make payments, enter credentials, or perform irreversible actions unless the user explicitly grants permission for that action.

## LangGraph

Borrow LangGraph architecture, not the core dependency:

- State is explicit and evolves through steps.
- Checkpoints preserve enough context to resume.
- Interrupts are first-class when user input or permission is needed.
- Tool execution needs routing, permissions, and result validation.
- Parallel work should be structured and bounded.
- A persistent store and short-term checkpoint serve different purposes.

Oden should express these concepts as markdown protocols and file conventions. A future optional runtime can implement them later if needed.

## Provider References

Oden must support agents that consume configuration differently:

- Codex: repo instructions and optional global instruction/skill material.
- Claude Code: project instructions, commands, and agents.
- Cursor: rule files and global settings guidance.
- Hermes and LM Studio: exportable system instructions and local/open-model tool policy guidance.
- ChatGPT: a copyable global/project instruction bundle.

Provider details change. Phase 2 agents must verify current provider-specific file formats before finalizing export instructions, but the canonical Oden rules must remain provider-neutral.

## Source Policy

The user permits copying and rewriting from the references as needed. Still:

- Preserve license notices when copying MIT-licensed source files.
- Prefer rewriting prose into Oden's own voice unless exact wording is intentionally useful.
- Do not copy secrets, generated files, lockfiles, or reference repository metadata into Oden.
- Document provenance where copied code or substantial adapted text is used.

