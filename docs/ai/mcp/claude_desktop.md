# Claude Desktop Configuration for AI Verde Data Store MCP Server

This guide shows how to connect Claude Desktop to the AI Verde Data Store MCP server over Streamable-HTTP using the Connectors UI.

## Prerequisites
- Claude Desktop installed
- Claude Pro plan (free plan users cannot add new connectors)
- CyVerse account credentials (if not using anonymous access)


## 1. Open Connectors in Claude

1. Launch Claude Desktop.
2. Go to `File` → `Settings` → `Connectors`.
3. Click the `Add custom connector` button (Note: This button is not available to free plan users).

## 2. Add the AI Verde Data Store MCP Server

### a. Anonymous Access

Fill in the fields:

- Name: `AI-Verde Data Store Public`
- URL (anonymous public data access): `https://mcp-public.cyverse.ai/mcp`

Click the `Save` button.

### b. Full Access with CyVerse Account

Fill in the fields:
- Name: `AI-Verde Data Store`
- URL (full access): `https://mcp.cyverse.ai/mcp`

Click the `Save` button.

When adding `https://mcp.cyverse.ai/mcp`, you will be prompted for the following information to log in.
- Client ID: `mcp-client`
- Client Secret: `<empty>` **(leave it empty, as one is not required)**


## 3. Verify the Connection

Open a chat in Claude and try a simple request.
