# claude-plugins-official (Anthropic marketplace)

Anthropic's official Claude Code plugin **marketplace** — a third-party (non-FlexNetOS)
pointer, cataloged here because the workspace uses plugins from it.

| | |
|---|---|
| **Owner** | Anthropic (`support@anthropic.com`) |
| **Category** | marketplace |
| **Marketplace name** | `claude-plugins-official` |
| **Status** | stable |
| **Hosting** | registry-only (third-party pointer; not hosted in the FlexNetOS org) |

## Lists (installed in the workspace cache)

`claude-code-setup`, `code-review`, `frontend-design`, `github`, `hookify`, `playwright`,
`ralph-loop`, `rust-analyzer-lsp`, `superpowers`, `typescript-lsp`,
`ui5-typescript-conversion`.

**Enabled across the workspace:** `rust-analyzer-lsp@claude-plugins-official`. The rest are
cached/available — enable per-repo as needed.

## Install

Snippet: [`snippets/claude-plugins-official.marketplace.json`](../snippets/claude-plugins-official.marketplace.json)

```bash
claude plugin marketplace add anthropics/claude-code   # Anthropic's official marketplace
claude plugin install rust-analyzer-lsp@claude-plugins-official
```

## Notes

External dependency, documented for completeness — not forked or hosted by FlexNetOS. Some
of its plugins overlap names with FlexNetOS-wired MCP servers (e.g. `github`, `playwright`);
the workspace's canonical wiring for those lives in
[`mcp_hub`](https://github.com/FlexNetOS/mcp_hub) — cross-reference, not duplicate.
