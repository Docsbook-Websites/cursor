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

## Common questions

<!-- widget:accordion -->

### Which pool does my request draw from?

It depends on the model you select. Choosing one of the models Cursor hosts draws from the Cursor Models pool; selecting a specific third-party model draws from the Other Models pool at that model's API rate.

### Why did my included usage run out faster this month?

Almost always model selection. Because API costs differ by an order of magnitude between tiers, a month spent on a premium model consumes the same allowance far faster than a month on a hosted one. The usage dashboard breaks this down.

### Does a bigger model always produce better code?

No. On routine edits within a well-described codebase, the difference is often invisible while the cost is not. Premium models earn their price on genuinely hard problems: subtle debugging, unfamiliar architecture, or code you cannot easily verify yourself.

### What do Teams and Enterprise plans add?

Centrally managed [team rules](../customize/rules.md), shared MCP server distribution, administrative control over source control connections, and Cursor Router for automatic per-request model selection.

<!-- /widget -->

## Related

- [Quickstart](quickstart.md) — get running before you tune model choice
- [Agent overview](../agent/overview.md) — how the model fits with tools and instructions

<!-- widget:cta -->

## Try it before you tune it

Most teams settle on a model mix after a week of real use, not from a pricing table.

[Download Cursor](https://cursor.com/download) · [See current pricing](https://cursor.com/pricing)

<!-- /widget -->
