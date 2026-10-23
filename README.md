# Synorb MCP server

Cited context for AI agents. Synorb reads company newsrooms, SEC filings, central bank publications, research, speeches and podcasts, and returns each item as a Manifest: a structured summary with claims, tags and a link to the original source.

- **URL:** `https://mcp.synorb.com/mcp` (Streamable HTTP)
- **Sign-in:** a Synorb Key in the `Authorization: Bearer` header; ChatGPT and Claude sign in with OAuth instead
- **Docs:** https://synorb.com/docs/mcp

This repository holds the server's public metadata and connection examples. The server itself is hosted by Synorb; there is nothing to install.

## Connect

**ChatGPT and Claude.** Synorb is in review for the ChatGPT app directory and the Claude connector directory. Once it is listed, search for Synorb, connect, and sign in with a Synorb account; signing in creates one if you do not have one. Until then, use a key as below.

**Any other MCP client.** Get a Synorb Key at https://synorb.com/connect/start, then:

```json
{
  "mcpServers": {
    "synorb": {
      "type": "streamable-http",
      "url": "https://mcp.synorb.com/mcp",
      "headers": { "Authorization": "Bearer YOUR_SYNORB_KEY" }
    }
  }
}
```

Discovery tools (`synorb-catalog`, `synorb-stream-search`, `synorb-details`, `synorb-configure-beacon`) work without a key. Reading Manifests and account tools need a key or a sign-in.

## Tools

| Tool | What it does |
|---|---|
| `synorb-stream-search` | Find the streams that cover a company, person, publisher or topic |
| `synorb-catalog` | Browse the catalog of streams and surfaces |
| `synorb-details` | A stream's sources and recent activity |
| `synorb-manifests` | Read cited Manifests, filtered by date, publisher type, named source or SEC form |
| `synorb-configure-beacon` | Propose a Beacon (a saved search) from a plain-English goal; saves nothing |
| `synorb-save-beacon` | Save a Beacon after the user says yes |
| `synorb-beacons` | List saved Beacons, or read one |
| `synorb-update-beacon` | Change a saved Beacon |
| `synorb-archive-beacon` | Archive a saved Beacon |
| `synorb-profile` | The account's plan, usage and reset date |

Reading Manifests counts against the account's monthly allowance. Searching streams and viewing stream details do not.

## Try asking

- Which streams cover NVIDIA?
- What did the Federal Reserve publish recently? Cite the sources.
- Show the latest 8-K filings for Apple.
- Propose a Beacon that monitors Federal Reserve publications with a 7-day lookback.

## Files

- `server.json`: the entry for the official MCP Registry (`com.synorb/mcp`).
- `LICENSE`: MIT, for the files in this repository.

## Links

- Site: https://synorb.com
- MCP docs: https://synorb.com/docs/mcp
- Free, keyless news for agents from the same team: [Hanging Context](https://github.com/Synorb/hanging-context)
