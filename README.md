# Lorcana Sim

Lorcana Sim is a **Disney Lorcana simulator** you add to Claude, ChatGPT, Cursor, or VS Code. Paste a deck and ask: Is this legal on Core or Infinity? How often do I ink on curve? Goldfish this list.

Operated by **FMF Tools**.

- Live site: https://lorcana-sim.fmf-x402.workers.dev/
- MCP endpoint (Streamable HTTP): https://lorcana-sim.fmf-x402.workers.dev/mcp
- Install page: https://lorcana-sim.fmf-x402.workers.dev/install
- Tools and prices: https://lorcana-sim.fmf-x402.workers.dev/docs

No account is required. `tools/list`, deck check, and opening-hand odds are free. Paid sims are charged per successful call through MPP on Tempo or x402 on Base (USDC). Bad input is refused and is not charged.

## Install

MCP server URL: `https://lorcana-sim.fmf-x402.workers.dev/mcp`

### Claude Desktop

Settings → Connectors → Add custom connector → URL: `https://lorcana-sim.fmf-x402.workers.dev/mcp`

Or add this to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "lorcana-sim": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://lorcana-sim.fmf-x402.workers.dev/mcp"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add --transport http lorcana-sim https://lorcana-sim.fmf-x402.workers.dev/mcp
```

### Cursor

`~/.cursor/mcp.json` (or `.cursor/mcp.json` in a project):

```json
{
  "mcpServers": {
    "lorcana-sim": {
      "url": "https://lorcana-sim.fmf-x402.workers.dev/mcp"
    }
  }
}
```

### VS Code (Copilot agent mode)

```bash
code --add-mcp '{"name":"lorcana-sim","type":"http","url":"https://lorcana-sim.fmf-x402.workers.dev/mcp"}'
```

### ChatGPT

Settings → Apps & Connectors → Advanced settings → turn on Developer mode → Create connector. Name: Lorcana Sim. MCP server URL: `https://lorcana-sim.fmf-x402.workers.dev/mcp`. Authentication: none.

## Tools

| MCP tool | Price |
|---|---|
| lorcana_deck_check | free |
| lorcana_opening_hand_odds | free |
| lorcana_draw_odds | $0.001 |
| lorcana_ink_odds | $0.001 |
| lorcana_goldfish | $0.003 |

## Licence and fan notice

This repository is MIT licensed. Lorcana Sim is an unofficial fan tool, not affiliated with or endorsed by Disney or Ravensburger. Disney Lorcana and card names are trademarks of their owners. Card data comes from the Lorcast API. Card data tools are free. Paid tools sell only our own computation and return no card data.

Contact: fmf-tools@agentmail.to
