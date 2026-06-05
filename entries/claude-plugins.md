# claude-plugins (gitkb marketplace)

A Claude Code plugin **marketplace** (`gitkb`) — a thin registry that lists installable
plugins rather than shipping capabilities itself.

| | |
|---|---|
| **Repo** | [`FlexNetOS/claude-plugins`](https://github.com/FlexNetOS/claude-plugins) |
| **Category** | marketplace |
| **Marketplace name** | `gitkb` |
| **Status** | stable |
| **Hosting** | peer (workspace member `claude-plugins/`) |

## Lists

| Plugin | Source | What it is |
|---|---|---|
| `meta` | git-subdir `gitkb/meta` @ `claude-plugin` | Multi-repo workspace management — skills, hooks, and the `meta` MCP server |
| `gitkb` | git-subdir `gitkb/gitkb-claude-plugin` @ `plugin` | Knowledge base + code intelligence: agent memory, tasks, call graphs, 42 MCP tools |

## Install

Snippet: [`snippets/claude-plugins.marketplace.json`](../snippets/claude-plugins.marketplace.json)

```bash
claude plugin marketplace add FlexNetOS/claude-plugins
claude plugin install meta@gitkb
claude plugin install gitkb@gitkb
```

## Notes

This is the `meta`-workspace MCP/skill plugin source (the `meta` plugin here exposes the
same `meta_*` MCP tools cataloged in [`mcp_hub`](https://github.com/FlexNetOS/mcp_hub) —
cross-reference, not duplicate).
