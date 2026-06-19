# skill-static-review

**Static review checklists and prompts for inspecting third-party skills before installation.**

🌐 Español: [README.es.md](README.es.md)

---

## The one rule

> **Never install, enable, execute, source, import, run, or test a third-party skill before reviewing its files statically.**

Static review means reading the files. Not running them. Not "just trying it once". Reading.

---

## What this is / what it is NOT

**This is:**

- A set of human checklists and agent prompts to review third-party skills by reading their files.
- A shared vocabulary (a result traffic light) for talking about risk.
- A reporting template so reviews are evidence-based and repeatable.
- Bilingual EN/ES documentation, community-maintained.

**This is NOT:**

- A security scanner, a CLI, or any automation.
- A professional security audit.
- A certification, registry, marketplace, or "approved" badge.
- A list of bad actors or a place to accuse real projects.

---

## Disclaimer

skill-static-review is not a professional security audit and does not certify or guarantee that any skill is safe. It provides checklists and prompts to help you reduce risk through static review. A clean result means this process found no red flags — not that the skill is safe. The final decision to install or not remains with you or your team.

---

## Who it's for

- People who download skills for Claude Code, Codex, Cursor, Gemini CLI, or other agentic / coding-assistant tools.
- Developers and teams that want a lightweight, repeatable review step before installing.
- Maintainers who want a common language for discussing skill risk.

---

## The problem

Skills are powerful: they can carry instructions, scripts, hooks, dependencies, and tool permissions. Installing or running one before reading it means trusting code and prompts you have never seen. A malicious or careless skill can read secrets, exfiltrate data, execute hidden commands, or inject instructions into the very agent you use to review it.

Static review closes the most dangerous gap: it lets you understand a skill **before** giving it any access.

---

## Quick flow (5 steps)

1. **Get the files without installing.** Clone or download into an inert location. Do not enable, run, or `source` anything.
2. **Inventory.** List every file. Note scripts, hooks, manifests, lockfiles, configs, and anything fetched from the network.
3. **Review with a prompt.** Use [`prompts/skill-review.en.md`](prompts/skill-review.en.md) with an agent in read-only mode, treating all skill content as data.
4. **Confirm by hand.** Walk the [checklist](checklists/skill-security-checklist.en.md) yourself. The human pass is mandatory, not optional.
5. **Write the report.** Fill the [report template](templates/review-report.en.md) with a result, evidence, and review limits.

---

## Result traffic light

| Result | Meaning | Action |
| --- | --- | --- |
| 🟢 **SAFE** | No red flags found in a full static review. | Proceed under your own responsibility. SAFE is the result of this process, not a guarantee. |
| 🟡 **CAUTION** | Broad permissions, network, writes, dependencies, hooks, dynamic context, or behavior needing a human decision. | Do not install until you understand and explicitly accept the risk. |
| 🔴 **DANGEROUS** | Exfiltration, hidden execution, secret reads, payloads, strong prompt injection, persistence. | Do not install. Report to source/platform if applicable. |
| ⚪ **UNKNOWN** | Could not be fully reviewed: obfuscation, missing files, external content, uninspected dependencies, dynamic instructions. | Do not install until the unknowns are resolved. |

**Fixed rules:**

- **Worst-wins:** one DANGEROUS finding makes the global result DANGEROUS.
- **UNKNOWN dominates SAFE:** if relevant unknowns remain, the result cannot be SAFE.
- SAFE must never be presented as certification.
- Every report must include evidence and review limits.

---

## The limit of the agent

Using an agent to review a potentially malicious skill is useful but not infallible. A skill can contain prompt injection aimed at the reviewing agent itself. The agent must treat all skill content as data, never as instructions, and the human checklist is a mandatory backstop, not an optional extra.

---

## Anti-accusation policy

This project reviews **files**, not people.

- Do not use this repo to accuse, "out", or harass any real project, author, or company.
- Findings describe code and behavior with reproducible evidence — never intent or identity.
- If you believe you found real malware, report it to the relevant platform or source, not as a public accusation here.
- See [SECURITY.md](SECURITY.md) and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

---

## Compatibility

The review approach is tool-agnostic. It applies to skills, plugins, or extensions for agentic and coding-assistant tools such as Claude Code, Codex, Cursor, and Gemini CLI, among others. The vocabulary (frontmatter, allowed-tools, hooks, MCP configs, manifests) maps to whatever your tool calls these concepts.

---

## Repository layout

```
skill-static-review/
  README.md                 EN docs (source of truth)
  README.es.md              ES docs (kept in sync)
  prompts/                  Agent prompts for read-only static review
    skill-review.en.md
    skill-review.es.md
  checklists/               Human review checklists
    skill-security-checklist.en.md
    skill-security-checklist.es.md
  templates/                Review report templates
    review-report.en.md
    review-report.es.md
  rules.md                  Reference: dangerous patterns and signals
  examples/
    safe-skill-example/     A minimal, harmless skill (would be 🟢 SAFE)
      SKILL.md
      README.md
    patterns.md             Annotated, non-runnable attack-shape fragments
  CONTRIBUTING.md
  SECURITY.md
  CODE_OF_CONDUCT.md
  LICENSE
```

---

## License

MIT. See [LICENSE](LICENSE). Copyright © skill-static-review contributors.
