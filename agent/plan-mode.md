---
title: Plan Mode — Approve an Approach Before the Agent Writes Code
description: Use plan mode for multi-file changes so Cursor researches your codebase, asks clarifying questions, and produces an implementation plan you approve first.
---

# Plan mode

Plan mode inserts an approval step before any code is written. Toggle it with `Shift+Tab` in the agent input.

## What changes

Instead of editing immediately, the agent:

1. Researches your codebase to find the files a change would touch
2. Asks clarifying questions about requirements it cannot infer
3. Produces a detailed implementation plan
4. Waits for your approval before building

## When to use it

Plan mode earns its extra step when a task spans multiple files, requires research before the approach is clear, or touches something where a wrong direction is expensive to unwind.

For a one-line fix it is overhead. For a change that reaches across a service boundary it saves a review cycle, because disagreements surface in the plan rather than in a large diff.

## Reading the plan critically

The plan is where your judgment has the most leverage. Check that it names the files you expect. A plan that misses a module you know is involved signals the agent has the wrong mental model, and approving it produces a confidently wrong change.

Answer the clarifying questions properly. They are the agent's attempt to resolve genuine ambiguity, and a vague answer propagates into the implementation.

## Related

- [Quickstart](../get-started/quickstart.md) — where plan mode first appears
- [Agent overview](overview.md) — the default non-planning loop
- [Rules](../customize/rules.md) — encode standing constraints so plans respect them
