---
title: Agent Tools — File Edits, Search, Terminal, and Web Access
description: Review the tools Cursor's agent uses to read and edit files, search your codebase, run shell commands, browse the web, and ask you clarifying questions.
---

# Agent tools

Tools are how the agent affects anything outside its own reasoning. Knowing the set helps you predict what it will try and write requests it can actually act on.

## Available tools

**Search files and folders** locates code by name or content across the repository. This usually runs first on any request that names something without giving a path.

**Read files** pulls file contents into context. The agent reads before editing rather than guessing at what a file contains.

**Edit files** applies changes. Every edit appears in the diff view for review.

**Run shell commands** executes terminal commands: tests, builds, linters, package installs, and git operations.

**Web** fetches documentation and other pages, which matters when working against a library whose API changed after the model's training cutoff.

**Browser** drives a browser session so the agent can check rendered output rather than reasoning about markup.

**Fetch rules** pulls in the [rules](../customize/rules.md) relevant to the current task.

**Image generation** produces images where a task calls for one.

**Ask questions** lets the agent stop and ask you instead of guessing on an ambiguous requirement.

## Tool calls are unlimited per task

A single task can involve any number of tool calls. A well-scoped request produces a short, legible sequence. A vague one produces a long exploratory search that costs time and usage.

## Extending the tool set

[MCP](../customize/mcp.md) adds tools beyond the built-in set, connecting the agent to databases, internal APIs, and third-party services.

## Related

- [Agent overview](overview.md) — how tools fit with instructions and the model
- [MCP](../customize/mcp.md) — connect external systems
