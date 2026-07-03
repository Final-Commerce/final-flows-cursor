# Final Flows — Cursor plugin

Build real point-of-sale software from Cursor. This plugin connects Cursor to
the [Final Flows MCP server](https://build.finalpos.com), so your agent can
design, preview, validate, and deploy POS / kiosk / self-checkout apps on the
[Final](https://finalpos.com) commerce platform.

## What your agent gets

- **Grounded API lookups** — version-locked command-frame, REST API, and
  engine-component catalogs, so generated code calls real methods and fields.
- **Vetted screen blueprints** — product grids, carts, payment surfaces,
  receipts — type-checked patterns to adapt instead of hallucinating UI.
- **Cloud flows with checkpoints** — every file write lands as a restorable
  checkpoint, mirrored into the Final builder for the flow's owner.
- **Live previews** — a real Vite dev server in a cloud sandbox, on a public
  HTTPS URL.
- **Built-in persistence** — custom data tables that sync across every station
  and keep working offline at the point of sale.
- **Encrypted secrets vault** — the agent requests credentials by name; values
  are typed by a human into the builder and never pass through the model.
- **Validation gates + deploy** — the same server-side guardrails, typechecks,
  and secret scans Final's own builder uses, then one-call deploys to Final
  web-hosting.

## Install

Install from the Cursor Marketplace, or add the MCP server directly to
`.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "final-flows": {
      "url": "https://build.finalpos.com/api/mcp"
    }
  }
}
```

## Sign in

On first use, Cursor walks you through OAuth against your Final organization —
sign in and approve, and the connection is scoped to your org's flows.

Prefer a static key? Mint an organization API key in the Final builder
(chat rail → cable icon → "Connect your AI tool") and use:

```json
{
  "mcpServers": {
    "final-flows": {
      "url": "https://build.finalpos.com/api/mcp",
      "headers": { "Authorization": "Bearer sk_..." }
    }
  }
}
```

Every tool call is scoped to your own organization. Revoke the key (or the
OAuth connection) at any time to cut off access.

## Links

- Platform: https://finalpos.com
- Builder: https://build.finalpos.com
- Privacy: https://finalpos.com/legal/privacy
- Terms: https://finalpos.com/legal/terms
- Support: support@finalpos.com
