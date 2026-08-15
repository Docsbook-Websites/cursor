---
title: Source Control — Connect GitHub, GitLab, Bitbucket, or Azure DevOps
description: Connect a source control provider so Cursor cloud agents can clone repositories, work on separate branches, and push changes back for review.
---

# Source control

A source control connection is a prerequisite for [cloud agents](../cloud-agents/overview.md). Without it, agents cannot clone a repository or push their work back.

## Supported providers

- **GitHub** — Cloud and Enterprise Server
- **GitLab** — Cloud and Self-Hosted
- **Bitbucket Cloud**
- **Azure DevOps**

An account admin makes this connection once for the account, before anyone can start a cloud agent from a repository.

## How agents use it

The agent clones your repository, works on a separate branch, and pushes changes there for handoff. Your default branch is not written to directly, so review happens the same way it does for human contributors.

Read-write access is required for the repository and for any dependent repositories or submodules the work touches.

## Access scope

The connection determines what agents can reach. Grant access to the repositories that need it rather than to everything an admin account can see, particularly on accounts that also hold infrastructure or credentials repositories.

## Launching from a pull request

Once connected, you can comment `@cursor` on a GitHub pull request or issue, or on a Bitbucket pull request, to start an agent with that context already attached.

## Related

- [Cloud agents overview](../cloud-agents/overview.md) — what the connection enables
- [Integrations](overview.md) — chat and issue tracker connections
