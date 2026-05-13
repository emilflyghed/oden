# ChatGPT Bundle

Use this bundle when copying Oden behavior into ChatGPT global or project instructions.

## Sources Checked

Checked on 2026-05-12:

- `https://help.openai.com/en/articles/8096356-chat-preferences-for-chatgpt`
- `https://help.openai.com/en/articles/10169521-using-projects-in-chatgpt`

## What To Copy

Global use:

- Copy `global-instructions.md` into ChatGPT custom instructions.
- Keep it concise; OpenAI documents a 1500-character limit for the longer custom-instruction fields.

Project use:

- Copy `project-instructions.md` into ChatGPT project instructions.
- If possible, attach or paste the relevant Oden docs for the project.

## Current ChatGPT Conventions

- Custom instructions apply across chats after they are enabled.
- Project instructions apply only inside that project and override global custom instructions.
- Projects can hold files, instructions, chats, and memory.
- ChatGPT cannot reliably follow local file references unless the files are available in the conversation or project.

## Canonical Docs

If ChatGPT is working inside a project that includes Oden files, canonical docs remain under `agent-docs/`.

