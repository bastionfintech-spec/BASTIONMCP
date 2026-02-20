# Quickstart — Connect in 30 Seconds

BASTION is an MCP server. You connect it to Claude and talk to it in natural language. No SDK, no code, no API wrangling.

---

## Prerequisites

You need one of:
- **Claude Code** (CLI) — [claude.ai/code](https://claude.ai/code)
- **Claude Desktop** (app) — [claude.ai/download](https://claude.ai/download)

That's it.

---

## Step 1: Add the MCP Config

### Claude Code

Save this to `~/.claude/.mcp.json`:

```json
{
  "mcpServers": {
    "bastion": {
      "type": "sse",
      "url": "https://bastionfi.tech/mcp/sse"
    }
  }
}
```

Or copy the provided [`mcp-config.json`](./mcp-config.json) file to that path.

### Claude Desktop

1. Open **Settings** > **Developer** > **Edit Config**
2. Paste the same JSON block above
3. Save

---

## Step 2: Restart Claude

Close and reopen Claude Code or Claude Desktop. The MCP connection initializes on startup.

---

## Step 3: Try It

Open a conversation and ask:

**Market check:**
```
What's the current state of BTC? Show me funding rates, open interest, and any whale activity.
```

**Whale intelligence:**
```
Are there any large whale movements on ETH right now? What are the biggest wallets doing?
```

**Risk evaluation:**
```
I'm long SOL at $145 with a stop at $138 and 5x leverage. Should I hold, reduce, or exit?
```

If Claude responds with live market data, you're connected.

---

## Authentication

### Public tools (no key required)

Market data, whale tracking, funding rates, and general intelligence tools work immediately. No API key needed.

### Portfolio & risk tools (key required)

For portfolio-level access (position evaluation, risk intelligence, personalized analysis), you need a `bst_` API key.

1. Get your key at [bastionfi.tech/account](https://bastionfi.tech/account)
2. Tell Claude in conversation:

```
My BASTION api_key is bst_YOUR_KEY
```

Claude will use this key for authenticated requests in that session.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Claude doesn't recognize BASTION tools | Restart Claude. MCP servers connect on startup. |
| Connection refused / timeout | Verify the URL is exactly `https://bastionfi.tech/mcp/sse` (https, not http). |
| "Unauthorized" on risk tools | Check your API key starts with `bst_`. Re-enter it in the conversation. |
| Tools appear but return errors | Check [status.bastionfi.tech](https://status.bastionfi.tech) for service status. |
| Claude Desktop config not working | Make sure the JSON is valid. No trailing commas. Restart the app fully (quit, not just close window). |

---

## Next Steps

- [`guides/claude-code-setup.md`](./guides/claude-code-setup.md) — Detailed Claude Code configuration
- [`guides/claude-desktop-setup.md`](./guides/claude-desktop-setup.md) — Detailed Claude Desktop configuration
- [`guides/tools-reference.md`](./guides/tools-reference.md) — Full tool catalog with parameters and examples
