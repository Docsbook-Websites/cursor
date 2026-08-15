---
title: Multi-Repo Cloud Agents — Coordinated Changes Across Repositories
description: Run a Cursor cloud agent across frontend, backend, infrastructure, and shared-library repositories so it can make coordinated changes and open matching pull requests.
---

# Multi-repo environments

Some changes do not fit in one repository. An API field added in the backend has to be consumed by the frontend; a shared library bump ripples into every service that depends on it.

A multi-repo environment gives the agent the full workspace. It can inspect all of the repositories involved, make coordinated changes, and open pull requests in each repository it modified.

## When to use one

Use a multi-repo environment when a single logical change genuinely spans separate frontend, backend, infrastructure, or shared-library repositories, and the pieces have to agree with each other to work.

For a change contained in one repository, a single-repo environment starts faster and keeps the review surface smaller.

## Current limitation

Long-running agents are not yet available for multi-repo environments. Scope multi-repo tasks to work that completes in a single session rather than tasks you expect to run for an extended period.

## Reviewing the result

Multi-repo work produces several pull requests that only make sense together. Note the ordering: a consumer merged before the provider it depends on will break.

Because coordinated changes are exactly where a plausible-looking diff can be subtly wrong, this is a good case for [plan mode](../agent/plan-mode.md) before the agent starts.

## Related

- [Cloud agents overview](overview.md) — the single-repo default
- [Setup](setup.md) — defining environments
