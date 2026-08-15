---
title: Cloud Agent Setup — Define the Environment Agents Run In
description: Configure cloud agent environments with agent-led setup, a saved snapshot, or a Dockerfile, and use builds to prepare dependencies before agents start.
---

# Cloud agent setup

A cloud agent is only as capable as its environment. This page covers how to define one.

## Three approaches

**Agent-led setup** lets the agent work out the install steps for your project itself. It is the fastest way to a working environment and a reasonable starting point for a standard project.

**A saved snapshot** captures a prepared environment for reuse, which suits projects with setup steps that are slow or awkward to reproduce.

**A Dockerfile** referenced from `.cursor/environment.json` gives you explicit, version-controlled control over the image. Use it when the environment needs specific system packages, service dependencies, or a toolchain version your team pins.

## Builds

Builds prepare each environment in the background so agents start with repositories cloned and dependencies installed rather than spending their first minutes on setup.

The Cloud Agents dashboard shows which environment and build each agent used, which is where to look first when an agent behaves differently from what you expect.

## What a good environment includes

Work backwards from verification. Whatever your CI runs to decide a change is safe, the agent should be able to run too.

In practice that means the test suite, the type checker and linter, a working build, and access to any services the tests need. If integration tests require a database, an environment without one will produce changes that pass locally and fail in review.

Secrets belong in the environment configuration rather than in the repository. Scope them the way you would for CI: enough to run the tests, not enough to reach production.

## Related

- [Cloud agents overview](overview.md) — why environments matter
- [Multi-repo](multi-repo.md) — environments spanning several repositories
