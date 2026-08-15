---
title: Cursor CLI — Run the Agent from Your Terminal
description: Install the Cursor CLI and use interactive agent, plan, and ask modes to write, review, and modify code without leaving your terminal.
---

# Cursor CLI

The CLI runs the same agent from your terminal. It suits anyone who works primarily in a shell, and it is the entry point for [scripted and CI use](automation.md).

<!-- widget:stepper -->

### Install the CLI

On macOS, Linux, or WSL:

```bash
curl https://cursor.com/install -fsS | bash
```

On Windows with PowerShell:

```powershell
irm 'https://cursor.com/install?win32=true' | iex
```

As with any install script, read it before piping it to a shell if your environment calls for that.

### Start a session

Run `agent` for an interactive session, or open one with an initial prompt:

```bash
agent
agent "refactor the auth module to use JWT tokens"
```

In a session you describe goals, review proposed changes, and approve commands, the same loop as the editor.

### Pick the right mode

Press `Shift+Tab` for plan mode when the task needs a decision first, or `/ask` for read-only exploration when you want no changes at all.

<!-- /widget -->

## Modes

The CLI supports the same modes as the editor.

| Mode | Purpose | How to switch |
|---|---|---|
| Agent | Full tool access for complex tasks | Default |
| Plan | Design the approach first, with clarifying questions | `Shift+Tab`, `/plan`, `--plan`, `--mode=plan` |
| Ask | Read-only exploration, no changes | `/ask`, `--mode=ask` |

Ask mode is worth knowing about. When you want to understand code without any risk of it being modified, read-only is a stronger guarantee than asking nicely.

## Execution controls

<!-- widget:accordion -->

### Sandbox controls

Configure command execution with `/sandbox` or `--sandbox <mode>`, where mode is `enabled` or `disabled`. An interactive menu controls sandboxing and network access, and settings persist across sessions.

### Sudo password prompts

When a command needs elevated privileges, Cursor shows a masked password prompt. The password goes to `sudo` through a secure IPC channel and is never exposed to the model.

### Cloud handoff

Prefix a message with `&` to push the conversation to a [cloud agent](../cloud-agents/overview.md) that keeps running after you close the terminal:

```bash
& refactor the auth module and add comprehensive tests
```

Pick the task up later on web or mobile at [cursor.com/agents](https://cursor.com/agents).

<!-- /widget -->

## Related

- [Sessions](sessions.md) — resume earlier conversations
- [Automation](automation.md) — non-interactive runs for scripts and CI

<!-- widget:cta -->

## Put the agent in your shell

One install command, and the same agent you use in the editor runs where you already work.

[Download Cursor](https://cursor.com/download) · [Automate it in CI](./automation.md)

<!-- /widget -->
