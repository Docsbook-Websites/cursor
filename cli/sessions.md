---
title: CLI Sessions — Resume Earlier Cursor Conversations
description: List, resume, and continue previous Cursor CLI conversations so context carries across terminal sessions instead of restarting from scratch each time.
---

# Sessions

Conversations persist between terminal sessions, so you can pick up work without re-explaining it.

## Commands

List previous chats and choose one to resume:

```bash
agent ls
```

Resume the most recent conversation:

```bash
agent resume
```

Continue the previous session directly:

```bash
agent --continue
```

Resume a specific conversation by id:

```bash
agent --resume="chat-id-here"
```

## When to resume and when to start fresh

Resume when you are continuing the same piece of work and the earlier context still holds: the same files, the same goal, the same constraints you already explained.

Start fresh when the task changes. A long session carries all of its earlier turns, including abandoned approaches and dead ends. On a new problem that history is noise, and it competes for context with what actually matters.

## Related

- [CLI overview](overview.md) — modes and installation
- [Automation](automation.md) — running without a session at all
