---
title: Agent Overview — How Cursor Completes Coding Tasks
description: See how Cursor's agent combines instructions, tools, and a model to search your codebase, edit files, run commands, and complete multi-step coding tasks.
---

# Agent overview

The agent is the part of Cursor that does the work. It completes multi-step coding tasks on its own: searching the codebase, editing files, and running terminal commands. Open it in the sidepane with `Cmd+I`.

## Three components

Every agent is built from the same three pieces.

**Instructions** are the system prompt plus whatever [rules](../customize/rules.md) you have defined. This is the layer you control most directly.

**Tools** are the actions available to it: reading and editing files, searching the repository, running shell commands, fetching from the web, and more. See [tools](tools.md) for the full set.

**Model** is the frontier model you select for the task.

Cursor tunes instructions and tool definitions for each supported model rather than sending one generic prompt everywhere. As new models ship, that adaptation happens on Cursor's side.

## What a task looks like

Given a request, the agent searches for relevant files, reads them, proposes edits, and runs commands to check its work. There is no fixed limit on how many tool calls a single task can make, so a broad request may involve dozens of reads before the first edit appears.

This is why a specific request outperforms a vague one. "Fix the login bug" sends the agent hunting. "Users with expired sessions get a 500 instead of a redirect on /account" points it at the right file almost immediately.

## Checkpoints

The agent snapshots your files before significant changes, so you can preview and roll back if it takes a wrong turn. See [checkpoints](checkpoints.md).

## Queued messages

You do not have to wait for the agent to finish before typing your next instruction.

Press `Enter` while it is working to add a message to the queue. Queued messages appear in order below the active task and run sequentially once the current one finishes. You can drag them to reorder.

<video src="https://cursor.com/docs-static/images/agent/planning/agent-queue.mp4" controls muted loop playsinline width="100%"></video>

Press `Cmd+Enter` to bypass the queue and send immediately. The message attaches to the most recent turn and is processed right away, which is what you want when the agent is heading somewhere wrong and you need to redirect it now.

## Related

- [Tools](tools.md) — what the agent can reach
- [Plan mode](plan-mode.md) — approval before code for larger tasks
- [Rules](../customize/rules.md) — persistent instructions across sessions
