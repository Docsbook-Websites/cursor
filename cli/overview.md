---
title: Cursor CLI — Run the Agent from Your Terminal
description: Install the Cursor CLI and use interactive agent, plan, and ask modes to write, review, and modify code without leaving your terminal.
---

# Cursor CLI

The CLI runs the same agent from your terminal. It suits anyone who works primarily in a shell, and it is the entry point for [scripted and CI use](automation.md).

## Install

On macOS, Linux, or WSL:

```bash
curl https://cursor.com/install -fsS | bash
```

On Windows with PowerShell:

```powershell
irm 'https://cursor.com/install?win32=true' | iex
```

As with any install script, read it before piping it to a shell if your environment calls for that.

## Interactive sessions

Start a session with `agent`, or open one with an initial prompt:

```bash
agent
agent "refactor the auth module to use JWT tokens"
```

In a session you describe goals, review proposed changes, and approve commands, the same loop as the editor.

## Modes

The CLI supports the same modes as the editor.

| Mode | Purpose | How to switch |
|---|---|---|
| Agent | Full tool access for complex tasks | Default |
| Plan | Design the approach first, with clarifying questions | `Shift+Tab`, `/plan`, `--plan`, `--mode=plan` |
| Ask | Read-only exploration, no changes | `/ask`, `--mode=ask` |

Ask mode is worth knowing about. When you want to understand code without any risk of it being modified, read-only is a stronger guarantee than asking nicely.

## Sandbox controls

Configure command execution with `/sandbox` or `--sandbox <mode>`, where mode is `enabled` or `disabled`. An interactive menu controls sandboxing and network access, and settings persist across sessions.

## Sudo prompts

When a command needs elevated privileges, Cursor shows a masked password prompt. The password goes to `sudo` through a secure IPC channel and is never exposed to the model.

## Cloud handoff

Prefix a message with `&` to push the conversation to a [cloud agent](../cloud-agents/overview.md) that keeps running after you close the terminal:

```bash
& refactor the auth module and add comprehensive tests
```

## Related

- [Sessions](sessions.md) — resume earlier conversations
- [Automation](automation.md) — non-interactive runs for scripts and CI
