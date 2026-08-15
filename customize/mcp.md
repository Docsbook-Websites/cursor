---
title: MCP — Connect Cursor to External Tools and Data
description: Configure Model Context Protocol servers so Cursor can reach your databases, APIs, and internal services, with stdio, SSE, and HTTP transports.
---

# Model Context Protocol

MCP connects Cursor to systems outside your repository: databases, internal APIs, issue trackers, and third-party services. Rather than describing your infrastructure in every prompt, you give the agent a way to query it.

You can write an MCP server in any language that can print to stdout or serve an HTTP endpoint.

## Transports

| Transport | Runs | Deployment | Users | Input | Auth |
|---|---|---|---|---|---|
| `stdio` | Local | Managed by Cursor | Single user | Shell command | Manual |
| SSE | Local or remote | Deployed as a server | Multiple | SSE endpoint URL | OAuth |
| Streamable HTTP | Local or remote | Deployed as a server | Multiple | HTTP endpoint URL | OAuth |

Use `stdio` for anything personal that runs on your own machine. Use SSE or HTTP when a server should be shared across a team, since both support OAuth and central deployment.

## Supported capabilities

Cursor supports the core MCP capabilities and one extension:

- **Tools** — functions the model can execute
- **Prompts** — templated messages and workflows
- **Resources** — structured data sources to read and reference
- **Roots** — server-initiated queries about URI or filesystem boundaries
- **Elicitation** — server-initiated requests for more information from you
- **Apps** — interactive UI returned by a tool, as an extension

MCP Apps follow progressive enhancement: a tool that returns UI still works normally against a host that cannot render it.

## Installing servers

Official plugins are available in the Cursor Marketplace with one-click install from the Customize page. Community servers are catalogued at [cursor.directory](https://cursor.directory).

Team admins can distribute servers through a team marketplace, where they appear alongside personal and workspace servers.

## Configuring servers manually

Custom servers are declared in `mcp.json`.

A local server launched as a subprocess:

```json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["-y", "mcp-server"],
      "env": {
        "API_KEY": "value"
      }
    }
  }
}
```

A remote server over HTTP or SSE:

```json
{
  "mcpServers": {
    "server-name": {
      "url": "http://localhost:3000/mcp",
      "headers": {
        "API_KEY": "value"
      }
    }
  }
}
```

Treat credentials in this file the way you treat any other secret. Prefer environment variables over literals, and keep files containing real keys out of version control.

## Scoping what you expose

An MCP server defines what the agent can reach. A server with write access to production is a server the agent can write to production with.

Give each server the narrowest useful scope: read-only credentials where reading is enough, and a staging target rather than production where that answers the same question.

## Related

- [Agent tools](../agent/tools.md) — the built-in set MCP extends
- [Cloud agents](../cloud-agents/overview.md) — MCP servers work there too
