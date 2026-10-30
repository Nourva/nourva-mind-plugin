# Nourva Mind

Plugin that connects agents to [Nourva Mind](https://nourva.ai/memory), your private memory across AI apps, through Nourva's official remote [Model Context Protocol](https://modelcontextprotocol.io/) server.

Recall what matters about you, such as your work, projects, preferences and plans, and continue saved work from any app, only when you ask.

## Install

1. Open **Settings → Plugins**.
2. Search for **Nourva Mind**.
3. Click **Install**, then complete the Nourva sign-in prompt and press **Allow**.

## MCP

```json
{
  "mcpServers": {
    "nourva-mind": {
      "type": "http",
      "url": "https://nourva.ai/m/v1/mcp"
    }
  }
}
```

Auth is OAuth 2.1 with PKCE and dynamic client registration. No API key or client ID to configure.

## What agents can do

| Tool | Kind | What it does |
| --- | --- | --- |
| `nourva_memory_recall` | read-only | Recall the user's own context when they ask about themselves |
| `nourva_memory_ledger` | read-only | List what the memory holds |
| `nourva_memory_status` | read-only | How much the memory holds and the plan's limits |
| `nourva_memory_resume` | read-only | Continue saved work from the private work journal |
| `nourva_memory_propose` | write | Propose a lasting fact the user stated; reviewed before it is kept |
| `nourva_memory_save` | write | Save where the work stands to the work journal |
| `nourva_memory_forget_work` | destructive | Delete one work journal entry |

The hosted server is the source of truth for tool names and schemas.

## Privacy

- Tool calls run as the Nourva user who authorizes the connection, and see only that user's memory.
- Nothing is read from the host app's chats; only what the user asks to keep is saved.
- Keys, passwords and government ID numbers are removed before anything is saved.
- Policy: https://nourva.ai/policy#mind-apps · Terms: https://nourva.ai/terms

## Support

ai@nourva.ai

## License

MIT
