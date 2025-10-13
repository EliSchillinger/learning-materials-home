# General Configuration for AI Verde Data Store MCP Server

This document provides details of configuration information of the AI Verde Data Store MCP Server.

## MCP Server Host Information

### HTTP/SSE
The AI Verde Data Store MCP Server still supports HTTP/SSE, even though the protocol is **deprecated**. This support is maintained to ensure compatibility with many older AI Agents that can only communicate using HTTP/SSE.

The AI Verde Data Store MCP Server supports both `http` and `https`:

- HTTP URL: http://mcp.cyverse.ai/sse
- HTTPS URL: https://mcp.cyverse.ai/sse

### Streamable HTTP
The AI Verde Data Store MCP Server supports the new Streamable-HTTP protocol:

- HTTP URL: http://mcp.cyverse.ai/mcp
- HTTPS URL: https://mcp.cyverse.ai/mcp


## Authentication for Providate Data Access

### HTTP Basic Auth
The AI Verde Data Store MCP Server currently supports HTTP Basic Auth for accessing private data. In this method, your CyVerse user account credentials are included in the HTTP `Authorization` Header.

To use this, you must set the Authorization header in the following format: `Basic <base64("username:password")>`.

You first need to generate the Base64-encoded credential string. Use your CyVerse username (e.g., `foo`) and password (e.g., `mypassword`), separated by a colon (`:`), in the command below:
```bash
echo -n "foo:mypassword" | base64
```

Copy the resulting Base64-encoded text. When you configure your agent, you must prepend this encoded text with the string `Basic ` (including the space) in the `Authorization` header.