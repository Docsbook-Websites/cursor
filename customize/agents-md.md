---
title: AGENTS.md — Plain Markdown Instructions for the Agent
description: Use a single AGENTS.md file to give Cursor project instructions in plain markdown, and learn when it is the better choice over a .cursor/rules directory.
---

# AGENTS.md

`AGENTS.md` holds agent instructions in plain markdown. It is a simpler alternative to a `.cursor/rules` directory: one file, no frontmatter, no extension requirements.

## When to prefer it

Use `AGENTS.md` when your project has a modest set of conventions that apply broadly, or when you want instructions that are readable to anyone opening the repository, including people who do not use Cursor.

Use [project rules](rules.md) instead when you need conditional application. Rules can be scoped to file patterns or selected by the agent based on a description; `AGENTS.md` has no such targeting.

A project can start with `AGENTS.md` and move to rules when conventions diverge enough that applying all of them at once stops making sense.

## What to put in it

The useful content is what a new contributor would need told to them, and what a capable stranger would otherwise get wrong:

- Which package manager and scripts the project uses
- Where the important directories are and what belongs in each
- Conventions that are not enforced by a linter
- Anything genuinely surprising about the build, tests, or deployment

Leave out what the code already shows. Restating the framework or listing the dependency versions consumes context without adding information.

## Related

- [Rules](rules.md) — conditional and scoped instructions
- [Agent overview](../agent/overview.md) — how instructions reach the model
