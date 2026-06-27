# harness (team-architecture factory)

A Claude Code **plugin** — a meta-skill that turns a one-line domain description into an
agent team and the skills they use, plus ready-made packaged harnesses you can run in place
or eject into a repo.

| | |
|---|---|
| **Repo** | [`FlexNetOS/harness_hub`](https://github.com/FlexNetOS/harness_hub) (plugin at `harness/`) |
| **Category** | plugin |
| **Marketplace** | `harness-marketplace` |
| **Plugin version** | 1.17.0 |
| **Status** | stable |
| **Hosting** | peer (workspace member `harness_hub/`, sub-path `harness`) |
| **License** | Apache-2.0 (forked from [`revfactory/harness`](https://github.com/revfactory/harness)) |
| **Provides** | 35 agents · 41 skills · 0 commands · 2 hooks · 0 MCP servers |

## What it does

`/harness:harness` configures a harness for a domain: defines specialist agents and
generates the skills they use, across six team-architecture patterns (Pipeline,
Fan-out/Fan-in, Expert Pool, Producer-Reviewer, Supervisor, Hierarchical Delegation). It
also ships packaged harnesses:

- `/harness:meta-plugin` — repo-organization loop (the meta-repo's own org harness)
- `/harness:rust-port` — full-parity Rust port loop
- `/harness:feature-forge` — design → implement → verify construction crew + Ralph loop
- `/harness:bootstrap` — one-command fresh-repo onboarding to `hf` + forge-loop
- `/harness:planning-engineer` — evidence-backed planning/architecture loop

Many of the `harness:*` subagents in this workspace are provided by this plugin.

## Install

Snippet: [`snippets/harness.marketplace.json`](../snippets/harness.marketplace.json)

```bash
claude plugin marketplace add harness_hub/harness   # directory marketplace
claude plugin install harness@harness-marketplace
```

## Notes

Enabled as `harness@harness-marketplace`. Forked into `harness_hub` from upstream
`revfactory/harness` (Apache-2.0). The plugin's MCP-server count is 0 — it ships agents,
skills, and hooks, not MCP servers.
