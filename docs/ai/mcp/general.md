# General Configuration for AI Verde Data Store MCP Server

This guide provides the necessary configuration details for using the AI Verde Data Store MCP Server.

## Streamable-HTTP

The AI Verde Data Store MCP Server supports the new Streamable-HTTP protocol. This supports OAuth 2.0 authentication, which allows you to log in interactively with your CyVerse user account while adding the AI Verde Data Store MCP Server to your MCP Client.

- Streamable-HTTP URL: https://mcp.cyverse.ai/mcp

You can access your private data at `/iplant/home/<your_username>/` and public community-shared data at `/iplant/home/shared/`.

## Server-Sent Events (HTTP/SSE)

The AI Verde Data Store MCP Server still supports HTTP/SSE, even though the protocol is **deprecated**. This support is maintained to ensure compatibility with many older AI Agents that can only communicate using HTTP/SSE.

- SSE URL: https://mcp.cyverse.ai/sse

You will need to set your HTTP `Authorization` header to login. Please check below for how to set the header.

You can access your private data at `/iplant/home/<your_username>/` and public community-shared data at `/iplant/home/shared/`.

If no user credentials are passed through the HTTP `Authorization` header, you will only be able to access public, community-shared data.


### HTTP Basic Auth

HTTP Basic Auth is a traditional but less secure way to authenticate. In this method, your CyVerse user account credentials must be passed via the HTTP `Authorization` header.

To fill the `Authorization` header, use the following format: `Basic <your_base64_encoded_credentials>`.

You first need to generate the Base64-encoded credential string. Use your CyVerse username (e.g., `foo`) and password (e.g., `mypassword`), separated by a colon (`:`), with the following terminal command:
```bash
echo -n "foo:mypassword" | base64
```

This will generate a Base64-encoded string. Prepend this encoded text with the string `Basic ` (including the space) in the `Authorization` header while you configure your MCP Client.

## Anonymous Access

If you want to access only public community-shared data, you can use the public server.

- Streamable-HTTP URL: https://mcp-public.cyverse.ai/mcp
- SSE URL: https://mcp-public.cyverse.ai/sse

The MCP server will not require any login and grants access to `/iplant/home/shared`.
