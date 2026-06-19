# Example: a skill that would be 🟢 SAFE

This folder holds a minimal, harmless skill (`SKILL.md`) used to show what a
clean static review looks like. It is an **illustration**, not a guarantee — a
real review still walks the full checklist.

## Why this would be 🟢 SAFE under this process

Going through the checklist signals:

- **Author / origin / activity** — out of scope for the example, but in a real
  review you would confirm these.
- **File inventory** — a single `SKILL.md` plus this README. No binaries,
  archives, or hidden files.
- **SKILL.md & frontmatter** — the declared purpose (numbering Markdown
  headings) matches the body exactly. The description is honest and narrow.
- **Permissions** — `allowed-tools: []`. It requests no tools at all.
- **Network** — none. No URLs, fetch, curl, sockets, or webhooks.
- **Secrets** — none. It never reads env vars, tokens, or credential files.
- **Shell** — none. No commands, no spawned processes, no eval.
- **Hooks / MCP / plugins** — none.
- **Dependencies / install scripts** — none. Nothing to install, so no
  preinstall/postinstall risk.
- **Obfuscation** — none. Everything is plain, readable Markdown.
- **Prompt injection** — none. The instructions guide the assistant's own
  behavior on user-provided text; they don't try to seize the reviewing agent,
  change its role, or push it to act on the system.
- **Dynamic context** — none. The behavior is fully visible in the file.
- **Writes outside the folder** — none. It only returns text to the user.
- **Unknowns** — none that block a SAFE result.

## The honest caveat

Even here, 🟢 SAFE is the **result of this static review**, not a certification.
It means no red flags were found in the files as written. The decision to use
the skill still belongs to you or your team.
