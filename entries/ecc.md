# ECC (Everything Claude Code)

Harness-native engineering plugin for Claude Code and adjacent agent harnesses — a large
catalog of agents, skills, command shims, hooks, rules, and MCP conventions for
engineering teams.

| | |
|---|---|
| **Repo** | [`FlexNetOS/ECC`](https://github.com/FlexNetOS/ECC) (fork of [`affaan-m/ECC`](https://github.com/affaan-m/ECC)) |
| **Category** | plugin |
| **Version** | 2.0.0-rc.1 |
| **License** | MIT |
| **Homepage** | https://ecc.tools |
| **Status** | stable |
| **Hosting** | peer (workspace member `ECC/`) |

## Provides

| Agents | Skills | Commands | Hooks | MCP servers |
|---|---|---|---|---|
| 63 | 249 | 79 | 4 | 0 |

(Per the plugin manifest description; the repo also carries rules and MCP conventions.)

## Install

Snippet: [`snippets/ecc.marketplace.json`](../snippets/ecc.marketplace.json)

```bash
claude plugin marketplace add FlexNetOS/ECC
claude plugin install ecc@ecc
```

ECC ships both a `.claude-plugin/plugin.json` (the plugin) and a
`.claude-plugin/marketplace.json` (it can serve itself as a single-plugin marketplace).
Several of its agents/commands (`architect`, `code-architect`, `/plan-prd`, ADR
templates) are part of the workspace's design/architect tooling.

## Notes

Forked into the FlexNetOS org. Capability counts track the manifest as of v2.0.0-rc.1.
