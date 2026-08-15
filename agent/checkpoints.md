---
title: Checkpoints — Preview and Roll Back Agent Changes
description: Use Cursor's automatic checkpoints to snapshot your files before significant agent edits, preview any point in the session, and restore when a task goes wrong.
---

# Checkpoints

Checkpoints are snapshots of your files taken during an agent session. The agent creates them automatically before significant changes, capturing the state of everything it is about to modify.

## Restoring

Click any checkpoint in the chat timeline to preview your files as they were at that point. If that state is the one you want, restore it and all modified files revert.

You can also restore from the **Restore Checkpoint** button on an earlier request, or from the **+** button that appears when hovering over a message.

## When they help

Checkpoints matter most in exploratory work, where you are not sure the approach is right until you see it. They make a wrong turn cheap: revert and rephrase instead of unpicking edits by hand.

The same applies to large refactors and iterative sessions where several attempts precede the one you keep.

## Checkpoints are not version control

Checkpoints are stored locally and are entirely separate from Git. They exist to undo agent changes within a session.

Use Git for anything you need to keep: permanent history, sharing work, or recovering across machines. Commit at meaningful points during agent sessions, exactly as you would when writing the code yourself.

## Related

- [Agent overview](overview.md) — where checkpoints fit in a task
- [Plan mode](plan-mode.md) — avoid wrong turns instead of reverting them
