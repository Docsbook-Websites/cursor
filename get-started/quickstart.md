---
title: Quickstart — Your First Change with Cursor
description: Install Cursor, get oriented in an unfamiliar repository, make a small reviewed change, and learn when to switch into plan mode for larger work.
---

# Quickstart

This guide takes you from a fresh install to a reviewed change. The goal is not a large feature. It is to see the full loop once: ask, edit, review, verify.

## 1. Install and sign in

Download Cursor for macOS, Windows, or Linux from [cursor.com](https://cursor.com/download), open the app, and sign in. Then open a folder you already know something about. Familiar code makes it easier to judge whether the agent's output is any good.

## 2. Ask about the codebase

Open the agent panel with `Cmd+I` and ask it to orient you. Something like:

> Explain this codebase. Point me to the main entry points, key modules, and anything I should read before making changes.

The agent searches the repository, reads the files it considers relevant, and summarizes how the pieces fit together. This is the fastest way into an unfamiliar project, and it costs you nothing if the answer is wrong: nothing has been edited yet.

## 3. Make one small change

Ask for candidates before asking for code:

> Suggest three small, safe improvements in this codebase. Explain the tradeoffs and wait for me to choose one.

Good first tasks carry low risk. Copy fixes, small UI corrections, and missing error handling all work well. If you already know what you want, describe the result you expect rather than the steps to get there.

## 4. Review the diff and verify

The diff view shows every change the agent made. Read it before you accept it.

Then ask the agent to run the checks your project already has. Tests, a type checker, a linter, or a local build all serve as evidence that the change holds together. A change that has not been run is a proposal, not a result.

## 5. Switch to plan mode for bigger work

Once the basic loop feels familiar, use [plan mode](../agent/plan-mode.md) for anything that spans several files or needs a decision before coding. Press `Shift+Tab` in the agent input to toggle it.

In plan mode the agent researches the repository, asks clarifying questions, and produces an implementation plan for your approval before it writes code.

## Where to go next

- [Agent overview](../agent/overview.md) — what the agent can actually do
- [Rules](../customize/rules.md) — make your conventions stick across sessions
- [Models and pricing](models-and-pricing.md) — pick a model that fits the task
- [Cursor CLI](../cli/overview.md) — the same agent in your terminal
