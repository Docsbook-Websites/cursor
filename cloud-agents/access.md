---
title: Launching Cloud Agents from Desktop, Web, Mobile, and Chat
description: Start and manage Cursor cloud agents from the desktop app, browser, iOS, Slack, GitHub, Bitbucket, Linear, or the API, and hand off work between them.
---

# Ways to launch a cloud agent

Cloud agents can be started from wherever the work comes up, which is usually not the editor.

## Entry points

**Cursor Desktop** — select **Cloud** in the dropdown under the agent input.

**Cursor Web** — start and manage agents at [cursor.com/agents](https://cursor.com/agents) from any device.

**Cursor for iOS** — a native app for iPhone and iPad. On Android, open [cursor.com/agents](https://cursor.com/agents) in Chrome and tap **Install App** for a progressive web app.

**Slack** — use the `@cursor` command to kick off an agent.

**GitHub or Bitbucket** — comment `@cursor` on a pull request or issue.

**Linear** — use the `@cursor` command on an issue.

**API** — start agents programmatically from your own systems.

## Why the entry point matters

Each one attaches the agent to context that already exists. An agent started from a pull request comment has the diff and the discussion. One started from a Linear issue has the description and acceptance criteria. Retyping that into a fresh session loses detail and takes longer.

## Handing off from the CLI

The [CLI](../cli/overview.md) can push a conversation to a cloud agent mid-session by prefixing a message with `&`. The task continues running after you close your terminal, and you pick it up on web or mobile.

```bash
& refactor the auth module and add comprehensive tests
```

## Related

- [Cloud agents overview](overview.md) — how cloud agents work
- [Integrations](../integrations/overview.md) — connecting Slack, Linear, and issue trackers
- [CLI](../cli/overview.md) — terminal-side handoff
