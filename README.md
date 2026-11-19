# Monitive for Cursor

Monitor URLs, check incidents, and assert service health — all from inside your AI agent.

This is a thin, open-source Cursor plugin that installs the Monitive MCP server into Cursor in
one click, created and maintained by [Monitive](https://www.monitive.com). Once installed, Cursor agents
gain tools to create and manage uptime monitors, query incident status, and assert that URLs are healthy —
without leaving the editor. Documentation: https://monitive.com/docs/mcp/

> **Marketplace status:** The Cursor Marketplace listing is coming soon (submission in progress). Until
> it is approved, use the install instructions below.

## Install

### One-click

[Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=monitive&config=eyJ1cmwiOiJodHRwczovL2FwaS5tb25pdGl2ZS5jb20vbWNwIn0=)

This button will also be available directly from the Cursor Marketplace once the listing is approved.

### Manual (.cursor/mcp.json)

Add the following to your `.cursor/mcp.json` (OAuth — recommended):

```json
{
  "mcpServers": {
    "monitive": {
      "url": "https://api.monitive.com/mcp"
    }
  }
}
```

On first use, Cursor will prompt you to authorize via OAuth. Follow the browser prompt to connect your
Monitive account.

#### API key (alternative)

For trusted server-to-server contexts where OAuth is not practical, you can use a Bearer API key instead:

```json
{
  "mcpServers": {
    "monitive": {
      "url": "https://api.monitive.com/mcp",
      "headers": { "Authorization": "Bearer ${env:MONITIVE_API_KEY}" }
    }
  }
}
```

Set `MONITIVE_API_KEY` to an API key from your Monitive dashboard at https://my.monitive.com/keys. Keys follow the
`mk_live_...` format; keys created before 17 November 2026 start `umk_live_...` and keep working.

## What you get

Once connected, your Cursor agent gains tools to:

- **List monitors** — query all monitors in your account with their current status
- **Create a monitor** — set up a new HTTP/HTTPS monitor for any URL
- **Check incidents** — retrieve open or recent incidents for a monitor or your whole account
- **Assert URL health** — verify that a specific URL is up and returning an expected status code
- **Get monitor details** — inspect configuration, uptime history, and response times

## Auth

OAuth 2.1 is the default and recommended method — Cursor auto-discovers the authorization server for the
remote MCP endpoint. Bearer API keys are supported for trusted server-to-server contexts where interactive
OAuth is not available.

## Contributing

This repository is a thin wrapper; all monitoring behavior lives in the Monitive API backend. If you
notice a problem with the plugin manifest, install flow, or documentation, issues and pull requests are
welcome here.

---

Built by [Monitive](https://www.monitive.com).
