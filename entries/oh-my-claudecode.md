# oh-my-claudecode

Multi-agent orchestration system for Claude Code — planner/architect/designer agents,
consensus planning (ralplan), team workflows, and lifecycle hooks.

| | |
|---|---|
| **Repo** | [`FlexNetOS/oh-my-claudecode`](https://github.com/FlexNetOS/oh-my-claudecode) (fork of [`Yeachan-Heo/oh-my-claudecode`](https://github.com/Yeachan-Heo/oh-my-claudecode)) |
| **Category** | plugin |
| **Version** | 4.14.4 |
| **License** | MIT |
| **Status** | stable |
| **Hosting** | peer (workspace member `oh-my-claudecode/`) |

## Provides

| Agents | Skills | Commands | Hooks | MCP servers |
|---|---|---|---|---|
| 19 | 58 | 27 | 1 | 0 |

Notable: the `architect`/`planner`/`designer` agents and the `/plan --consensus`
(**ralplan**) workflow — the consensus design loop used to set the Hub Standard.

## Install

Snippet: [`snippets/oh-my-claudecode.marketplace.json`](../snippets/oh-my-claudecode.marketplace.json)

```bash
claude plugin marketplace add FlexNetOS/oh-my-claudecode
claude plugin install oh-my-claudecode@oh-my-claudecode
```

## Notes

Forked into the FlexNetOS org. Capability counts track the manifest as of v4.14.4.
