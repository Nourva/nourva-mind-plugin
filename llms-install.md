# Installing Nourva Mind

Nourva Mind is a hosted remote MCP server. There is nothing to download, build or run locally.

- Server URL: `https://nourva.ai/m/v1/mcp`
- Transport: Streamable HTTP
- Auth: OAuth 2.1 with PKCE and dynamic client registration. There is no API key, client ID or secret to configure. The first tool call opens Nourva's sign-in page in the browser; the user signs in and presses **Allow**.

## Configuration

Add this entry to the MCP settings file (for Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "nourva-mind": {
      "type": "streamableHttp",
      "url": "https://nourva.ai/m/v1/mcp"
    }
  }
}
```

Clients that name the transport `http` use `"type": "http"` with the same URL.

## Check it works

1. Ask: "What do you remember about me?" The client should call `nourva_memory_recall`.
2. Ask: "How much of my memory am I using?" The client should call `nourva_memory_status`.

## Requirements

- A Nourva account (sign up at https://nourva.ai).
- Nothing else: no Node, Python, Docker or environment variables.

## Notes for the assistant

- Call Nourva Mind only when the user's own context (who they are, their work, plans, preferences or saved projects) would change the answer.
- Never save passwords, keys, tokens or anything the user asked to keep out.
- Support: ai@nourva.ai
