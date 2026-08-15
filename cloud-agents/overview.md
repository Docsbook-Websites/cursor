---
title: Cloud Agents — Run Agents in Isolated Cloud Environments
description: Run Cursor agents in cloud VMs with cloned repos and installed dependencies, so they can build, test, and verify work without using your local machine.
---

# Cloud agents

Cloud agents run the same agent in an isolated VM instead of on your laptop. The environment mirrors a working development setup: cloned repositories, installed dependencies, secrets, startup commands, and network access.

## Why run agents in the cloud

You can run as many as you want in parallel, and they do not depend on your machine staying online. Close your laptop and the work continues.

Because each agent has its own VM, it can build the software, run the test suite, and interact with what it changed. It can also drive a desktop and browser, and connect to [MCP servers](../customize/mcp.md) for databases, APIs, and third-party services.

The practical difference is verification. A local agent that cannot run your integration suite hands you changes it believes are correct. A cloud agent with a working environment hands you changes it has actually exercised.

## Requirements

Before anyone can start a cloud agent from a repository, an account admin connects source control. Supported providers are GitHub (Cloud and Enterprise Server), GitLab (Cloud and Self-Hosted), Bitbucket Cloud, and Azure DevOps.

The agent clones your repository, works on a separate branch, and pushes changes back for handoff. Read-write access is required for the repository and any dependent repositories or submodules.

## Environments matter more than anything else

An agent is limited by the environment it runs in. One that can write code but cannot run tests, query services, or reach APIs cannot close the loop on its own work.

Environment setup is the highest-leverage configuration step for cloud agents. See [setup](setup.md) for the three ways to define one.

## Related

- [Setup](setup.md) — define the environment agents run in
- [Ways to launch](access.md) — desktop, web, mobile, chat, and API
- [Multi-repo](multi-repo.md) — changes spanning several repositories
