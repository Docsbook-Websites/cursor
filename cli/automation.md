---
title: CLI Automation — Run Cursor in Scripts and CI Pipelines
description: Use the Cursor CLI's print mode to run agents non-interactively in scripts and CI, selecting models and output formats for automated review and fixes.
---

# Automation and CI

Print mode runs the agent without an interactive session, which is what scripts and CI pipelines need.

## Print mode

Pass `-p` with the prompt:

```bash
agent -p "find and fix performance issues" --model "gpt-5"
```

Select the output format when a later step has to parse the result:

```bash
agent -p "review these changes for security issues" --output-format text
```

## What automation suits

Non-interactive runs work best where the output is advisory and a human reads it. Reviewing a diff for a specific class of problem, summarizing what changed, or flagging missing test coverage all fit: the agent produces a comment, and a person decides what to do.

Be deliberate about anything that commits, pushes, or deploys. In an interactive session you see each command before approving it; in a pipeline there is no such checkpoint. Scope pipeline credentials accordingly, and prefer having the agent open a pull request over having it push to a protected branch.

## Choosing a model in CI

Pipelines run often, so model choice compounds. A mid-tier model is usually right for routine review passes; reserve premium models for jobs where the analysis is genuinely hard. See [models and pricing](../get-started/models-and-pricing.md).

## Related

- [CLI overview](overview.md) — interactive modes
- [Sessions](sessions.md) — stateful conversations
- [Models and pricing](../get-started/models-and-pricing.md) — cost per run
