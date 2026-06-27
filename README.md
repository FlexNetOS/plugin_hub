# plugin_hub

**Catalog of Claude Code plugins and marketplaces used across the FlexNetOS meta workspace.**

A FlexNetOS hub: `registry.json` is the single source of truth, `scripts/validate.py`
keeps it consistent (CI-enforced), and this README mirrors it. Follows the
[Hub Standard](https://github.com/FlexNetOS/template_hub/blob/master/docs/hub-standard.md).

## Scope

In scope: Claude Code plugins and marketplaces (anything installable via a
`plugin.json` or `marketplace.json`).

Out of scope: raw hooks → [`hooks_hub`](https://github.com/FlexNetOS/hooks_hub); slash
commands → [`commands`](https://github.com/FlexNetOS/commands); MCP servers →
[`mcp_hub`](https://github.com/FlexNetOS/mcp_hub). Rule of thumb: *if it ships as a
plugin or marketplace bundle (a `plugin.json` / `marketplace.json`), it belongs here.*

**Not Claude Code plugins** (workspace repos that look like they'd fit but don't):
`oh-my-pi` is a standalone *coding agent* (npm `@oh-my-pi/pi-coding-agent`; its
marketplace.json are test fixtures) → belongs in `tool_hub`. `meta-plugins` is the **`meta`
CLI's** own plugin registry (docker/npm/k8s), not a Claude Code marketplace → different
plugin system, not cataloged here.

## Catalog

| Plugin | Category | Provides | Status | Doc |
|--------|----------|----------|--------|-----|
| [ECC](entries/ecc.md) | plugin | 63 agents · 249 skills · 79 cmds · 4 hooks | stable | [doc](entries/ecc.md) · [install](snippets/ecc.marketplace.json) |
| [oh-my-claudecode](entries/oh-my-claudecode.md) | plugin | 19 agents · 58 skills · 27 cmds · 1 hook | stable | [doc](entries/oh-my-claudecode.md) · [install](snippets/oh-my-claudecode.marketplace.json) |
| [claude-plugins](entries/claude-plugins.md) | marketplace | lists `meta` + `gitkb` | stable | [doc](entries/claude-plugins.md) · [install](snippets/claude-plugins.marketplace.json) |
| [harness](entries/harness.md) | plugin | 35 agents · 41 skills · 0 cmds · 2 hooks | stable | [doc](entries/harness.md) · [install](snippets/harness.marketplace.json) |
| [claude-plugins-official](entries/claude-plugins-official.md) | marketplace | Anthropic; `rust-analyzer-lsp` enabled (+10 avail.) | stable | [doc](entries/claude-plugins-official.md) · [install](snippets/claude-plugins-official.marketplace.json) |

## Entry shape

Each `plugins[]` entry in [`registry.json`](registry.json) looks like:

```json
{
  "id": "oh-my-claudecode",
  "displayName": "oh-my-claudecode",
  "category": "plugin",
  "status": "stable",
  "summary": "Multi-agent orchestration system for Claude Code: skills, commands, hooks, agents.",
  "tags": ["orchestration", "multi-agent"],
  "hosting": "peer",
  "workspaceMember": "oh-my-claudecode",
  "repo": "git@github.com:FlexNetOS/oh-my-claudecode.git",
  "marketplace": "oh-my-claudecode",
  "pluginVersion": "4.14.4",
  "provides": { "skills": 20, "commands": 12, "hooks": 4, "agents": 6, "mcpServers": 0 },
  "installSource": "git",
  "license": "MIT",
  "forked": true,
  "doc": "entries/oh-my-claudecode.md",
  "snippet": "snippets/oh-my-claudecode.marketplace.json"
}
```

`hosting`:

- `peer` — a forked plugin that is already a first-party workspace member (e.g. ECC,
  oh-my-claudecode, claude-plugins).
- `registry-only` — a third-party marketplace pointer; nothing is hosted here.
- `plugin_hub-child` — a fork hosted under this hub via `.meta.yaml` (`subPath`).

Full field reference: [`registry.schema.json`](registry.schema.json).

## Adding a plugin

Add an entry to `registry.json`, create `entries/<id>.md` (and a
`snippets/<id>.marketplace.json` fragment if useful), add a Catalog row, then run
`python3 scripts/validate.py`. See the
[Hub Standard](https://github.com/FlexNetOS/template_hub/blob/master/docs/hub-standard.md).
