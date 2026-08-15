---
title: Rules — Give the Agent Persistent Project Context
description: Define project, user, and team rules so Cursor follows your conventions in every session, with control over when each rule is applied.
---

# Rules

Models do not retain memory between completions. Everything the agent knows about your conventions has to be supplied with the request. Rules are how you supply it once instead of retyping it every session.

When a rule applies, its contents are included at the start of the model context.

## Four kinds of rules

**Project rules** live in `.cursor/rules`, are version-controlled, and are scoped to the codebase they ship with.

**User rules** are global to your Cursor environment and follow you across projects.

**Team rules** are managed centrally from the dashboard on Team and Enterprise plans.

**[AGENTS.md](agents-md.md)** is a plain-markdown alternative for projects that want one file rather than a rules directory.

## Project rule files

Project rules are `.mdc` files under `.cursor/rules`. You can name them anything and organize them into subfolders.

```
.cursor/rules/
  react-patterns.mdc       # recognized as a project rule
  api-guidelines.md        # ignored: wrong extension
  frontend/
    components.mdc
```

The `.mdc` extension is required. A plain `.md` file in that directory is ignored, because it has no frontmatter to carry the fields that control when the rule applies. If you prefer plain markdown, use [AGENTS.md](agents-md.md) instead.

## Controlling when a rule applies

Three frontmatter fields interact to determine inclusion.

| `alwaysApply` | `description` | `globs` | Behavior |
|---|---|---|---|
| `true` | — | — | Always included; other fields ignored |
| `false` | — | provided | Attached when a matching file is in context |
| `false` | provided | — | Included when the agent judges it relevant |
| `false` | — | — | Included only when you `@`-mention it |

### Always applied

For constraints that hold everywhere:

```markdown
---
alwaysApply: true
---
- All source files must include the company copyright header
- Read the relevant source files before proposing changes when
  implementation details are unclear
- Never modify generated files under `dist/` or `build/`
```

### Scoped to a file pattern

For conventions that apply to one part of the tree:

```markdown
---
globs: src/components/**/*.tsx
alwaysApply: false
---
- Use named exports, not default exports
- Co-locate styles in a module CSS file next to the component
- Extract subcomponents once a file grows past roughly 200 lines
- Prefer composition over prop drilling
```

### Selected by description

When the agent should decide based on the task:

```markdown
---
description: RPC service conventions for the backend
alwaysApply: false
---
- Define each service in its own file under `src/services/`
- Validate inputs at the service boundary
- Return structured errors with `code` and `message`; never throw raw strings
```

## Glob patterns

| Pattern | Matches |
|---|---|
| `*` | A single file name segment |
| `**` | Any number of directories, recursively |
| `*.ts` | `.ts` files in the root |
| `**/*.ts` | `.ts` files in any directory |
| `src/**` | Everything under `src/` |

Separate multiple patterns with commas.

## Writing rules that work

Rules compete for context, so keep them specific. "Write clean code" changes nothing. "Return structured errors with a code field" is checkable in a diff.

Prefer several narrow rules over one long one. Narrow rules can be scoped by glob or description, which means the agent sees them when they matter and not otherwise.

## Related

- [AGENTS.md](agents-md.md) — the single-file alternative
- [MCP](mcp.md) — extend tools rather than instructions
- [Agent overview](../agent/overview.md) — where instructions enter the loop
