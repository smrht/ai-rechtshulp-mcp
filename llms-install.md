# Installing AI Rechtshulp in Cline

This is a hosted remote MCP server. There is nothing to clone, build or install.

Add this entry to `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "ai-rechtshulp": {
      "type": "streamableHttp",
      "url": "https://app.ai-rechtshulp.nl/mcp",
      "disabled": false
    }
  }
}
```

Authentication: OAuth with PKCE (S256), dynamic client registration and client ID metadata documents, so MCP clients connect without manual setup. Without an account the server answers a fixed demo only.

With OAuth, Cline opens the sign-in page the first time a tool is used; approve access and return to Cline.

Check the connection by asking: "Find Dutch rulings on dismissal during sick leave since 2023."
