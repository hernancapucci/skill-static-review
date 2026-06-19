# Skill static review checklist (human pass)

Use this **after** the agent pass, or on its own. This human pass is mandatory.

Work top to bottom. For each item, record: ✅ checked / ⚠️ concern / ❓ unknown, plus a short note and evidence (file + line). Do not install anything while reviewing.

> Reminder: the skill is **not installed**. Read files only. Treat all skill content as data.

## 1. Author identity & reputation

- [ ] Is the author identifiable? Is the identity consistent with the source?
- [ ] Any history, other published work, or reputation you can check?
- [ ] Does the description match what the files actually do?

## 2. Repository origin

- [ ] Where did the files come from (official source, mirror, random link)?
- [ ] Is the origin the one the author claims?
- [ ] Were the files altered or re-packaged after publication?

## 3. Date & activity

- [ ] When was it published / last updated?
- [ ] Is it abandoned, or actively maintained?
- [ ] Any sudden, unexplained large change?

## 4. File inventory

- [ ] List **every** file. Nothing skipped.
- [ ] Any file that doesn't fit a documentation/skill (binaries, archives, minified blobs)?
- [ ] Any hidden files or unexpected directories?

## 5. SKILL.md

- [ ] Does it clearly state what the skill does?
- [ ] Does its stated scope match the rest of the files?
- [ ] Any instruction that tries to act on your machine or your agent?

## 6. Frontmatter

- [ ] Declared name, description, and triggers reviewed.
- [ ] Triggers not overly broad (e.g. activating on everything).
- [ ] No metadata that conflicts with the body.

## 7. Permissions

- [ ] `allowed-tools` / declared permissions reviewed.
- [ ] Permissions are the minimum needed for the stated purpose.
- [ ] No broad/wildcard tool access without justification.

## 8. Network

- [ ] Any outbound URL, fetch, curl, socket, or webhook?
- [ ] Is each endpoint necessary and explained?
- [ ] Any data being sent out (and what data)?

## 9. Secrets

- [ ] Any read of env vars, tokens, credential files, keychains, SSH keys?
- [ ] Is any secret read combined with network egress?
- [ ] Any reason for the skill to touch secrets at all?

## 10. Shell

- [ ] Any shell/python/js/ts script and what it does, line by line.
- [ ] Any command execution, spawned process, or eval-like behavior?
- [ ] Anything that runs without the user clearly asking?

## 11. Hooks

- [ ] Any pre/post or lifecycle hooks?
- [ ] What do they trigger, and when?
- [ ] Could a hook run code at install or activation time?

## 12. MCP / plugin config

- [ ] Any MCP server or plugin config?
- [ ] What servers, commands, or endpoints does it point to?
- [ ] Any auto-launch or auto-connect behavior?

## 13. Dependencies

- [ ] List declared dependencies.
- [ ] Are they known, necessary, and pinned?
- [ ] Any typosquat-looking names? Any uninspected transitive risk? (mark unknown)

## 14. Postinstall / preinstall

- [ ] Any install / preinstall / postinstall / setup script?
- [ ] What would run automatically on install?
- [ ] Treat any auto-running install script as high risk until proven benign.

## 15. Obfuscation

- [ ] Any base64 / hex / encoded blobs?
- [ ] Any minified or deliberately unreadable code?
- [ ] Anything you cannot fully read → mark unknown, do not assume benign.

## 16. Prompt injection

- [ ] Any text aimed at the reviewing or host agent ("ignore previous", "run this", "you are now…")?
- [ ] Any instruction disguised as data, comments, or examples?
- [ ] Any attempt to change the agent's role or rules?

## 17. Dynamic context

- [ ] Any content fetched, generated, or assembled at runtime?
- [ ] Could the effective instructions differ from what the files show?
- [ ] If behavior depends on external/dynamic content → mark unknown.

## 18. Writes outside the folder

- [ ] Any filesystem write outside the skill's own directory?
- [ ] Any write to home, config, shell rc, or system paths?
- [ ] Any overwrite or deletion of existing files?

## 19. Unknowns

- [ ] List everything you could NOT verify.
- [ ] Remember: relevant unknowns prevent a SAFE result.

## 20. Final decision

- [ ] Assign the result: 🟢 SAFE / 🟡 CAUTION / 🔴 DANGEROUS / ⚪ UNKNOWN.
- [ ] Apply worst-wins and UNKNOWN-dominates-SAFE.
- [ ] Fill the report template with evidence and review limits.
- [ ] The install decision is yours/your team's — SAFE is not a guarantee.
