---
name: heading-numbering
description: Add sequential numbers to the headings of a Markdown document the user is currently editing.
allowed-tools: []
---

# Heading numbering

A tiny, self-contained writing helper. It explains how to number the headings
of a Markdown document. It reads and reasons about text only — it does not run
commands, touch the network, or read any files outside what the user shares.

## What it does

When the user asks to number the headings of a Markdown document they provide,
walk the document top to bottom and prefix each heading with a section number
that reflects its level:

- `#` → `1`, `2`, `3`, …
- `##` → `1.1`, `1.2`, …
- `###` → `1.1.1`, …

## How to behave

1. Use only the text the user has shared in the conversation.
2. Return the renumbered Markdown back to the user.
3. Do not fetch anything, run anything, or modify files on your own.
4. If the document structure is ambiguous, ask the user instead of guessing.

## Out of scope

This skill does not install tools, manage files, access the network, or read
environment variables or secrets. If a task needs any of that, it is outside
this skill — say so and stop.
