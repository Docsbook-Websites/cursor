---
title: Cursor Documentation — AI Coding Agent for Real Codebases
description: Learn how to use Cursor's agent, rules, MCP integrations, cloud agents, and CLI to ship changes across your codebase from editor, terminal, or browser.
---

# Cursor Documentation

Cursor is a coding agent built for work on real codebases. It reads your repository, proposes changes, runs the commands your project already uses, and hands you a diff to review.

This site covers how the agent works, how to shape its behavior for your team, and how to run it outside the editor.

## Start here

If you have not installed Cursor yet, begin with the [quickstart](get-started/quickstart.md). It takes you from install to a reviewed change in five steps.

- [Quickstart](get-started/quickstart.md) — install, explore a repo, make your first change
- [Models and pricing](get-started/models-and-pricing.md) — usage pools, model rates, and plans

## Sections

### [Agent](agent/overview.md)

How the agent combines instructions, tools, and a model to complete a task. Covers the [tool set](agent/tools.md), [checkpoints and recovery](agent/checkpoints.md), and [plan mode](agent/plan-mode.md) for larger work.

### [Customize](customize/rules.md)

Make the agent follow your conventions. [Rules](customize/rules.md) give it persistent project context, [MCP](customize/mcp.md) connects it to your external systems, and [AGENTS.md](customize/agents-md.md) offers a plain-markdown alternative to rule files.

### [Cloud Agents](cloud-agents/overview.md)

Run agents in isolated cloud VMs instead of on your laptop. Covers [environment setup](cloud-agents/setup.md), the [ways to launch an agent](cloud-agents/access.md), and [multi-repo work](cloud-agents/multi-repo.md).

### [CLI](cli/overview.md)

Drive the agent from your terminal. Covers [installation and modes](cli/overview.md), [sessions](cli/sessions.md), and [non-interactive runs](cli/automation.md) for scripts and CI.

### [Integrations](integrations/overview.md)

Connect Cursor to the tools your team already uses, including [source control providers](integrations/source-control.md) and chat and issue trackers.

## About this site

This documentation site was built on [Docsbook](https://docsbook.io) as a worked example of a structured, searchable docs site. It describes Cursor based on the official documentation at [cursor.com/docs](https://cursor.com/docs), which remains the authoritative source for product details.
