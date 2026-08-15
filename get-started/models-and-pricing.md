---
title: Models and Pricing — Usage Pools and Plan Limits
description: Understand Cursor's two usage pools, how third-party model rates draw down your budget, and which plan fits individual, team, or enterprise use.
---

# Models and pricing

Cursor supports frontier models from several providers. Your plan determines how much usage is included and which pool it draws from.

> Pricing and model availability change often. Check [cursor.com/docs/models](https://cursor.com/docs/models) for current rates before making a purchasing decision.

## Two usage pools

Paid individual plans include two separate pools, each resetting on your monthly billing cycle.

**Cursor Models** covers the models Cursor hosts directly. This pool carries significantly more included usage, which makes it the sensible default for everyday work.

**Other Models** covers third-party models, charged at each model's API price. Paid plans include a monthly allowance in this pool, with the option to pay for more.

Both pools are visible in your editor settings and on your usage dashboard.

## How model choice affects cost

Models differ in API cost by more than an order of magnitude. A high-end model may cost several times what a mid-tier one does for the same token count, so your model selection determines how quickly the included allowance runs down.

A practical approach:

- Use the hosted Cursor models for routine edits, exploration, and iteration
- Reach for a premium third-party model when the task is genuinely hard: subtle debugging, architectural work, or code you cannot easily verify yourself
- Watch the usage dashboard for the first month to learn your own pattern

On Teams and Enterprise plans, Cursor Router can select the model per request based on your configured optimization mode.

## Plans

Paid individual plans include unlimited tab completions, extended agent usage, Bugbot, and access to [cloud agents](../cloud-agents/overview.md). Tiers differ mainly in how much third-party model usage is included.

Teams and Enterprise plans add centrally managed [team rules](../customize/rules.md), shared MCP distribution, and administrative control over source control connections.

Regional data residency is available on eligible models and carries a pricing uplift. See Cursor's privacy and data governance documentation for supported regions and functions.

## Related

- [Quickstart](quickstart.md) — get running before you tune model choice
- [Agent overview](../agent/overview.md) — how the model fits with tools and instructions
