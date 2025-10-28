# Claude Desktop Configuration for AI Verde Data Store MCP Server

This guide shows how to connect Claude Desktop to the remote AI Verde Data Store MCP server over Streamable-HTTP using the Connectors UI.

## Prerequisites
- Claude Desktop installed
- Claude Pro plan (free plan users cannot add new connectors)
- CyVerse account credentials (if not using anonymous acccess)


## 1. Open Connectors in Claude

1. Launch Claude Desktop.
2. Go to `File` → `Settings` → `Connectors`.
3. Click the `Add custom connector` button (Note: This button is not available to free plan users).

## 2. Add the AI Verde Data Store MCP Server

Fill in the fields:

- Name: `AI-Verde Datastore`
- URL (full access): `https://mcp.cyverse.ai/mcp`
- URL (anonymous public data access): `https://mcp-public.cyverse.ai/mcp`

Click the `Save` button.

## 3. Verify the Connection

Open a chat in Claude and try a simple request.
