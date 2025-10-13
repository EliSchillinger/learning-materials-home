# VS Code Configuration for AI Verde Data Store MCP Server

This document provides example configurations for setting up the remote AI Verde Data Store MCP Server for use with VS Code. Configurations are shown for using Streamable-HTTP.

## Prerequisites

- VS Code installed (latest recommended)  
- Copilot Chat extension enabled (supports MCP)  
- CyVerse account credentials (if not using anonymous access)

## 1. Configure MCP Server

### a. Configure MCP Server for Anonymous Access

Edit the `~/.config/Code/User/mcp.json` file.

Configure VS Code to use remote AI Verde Data Store MCP Server with Streamable-HTTP. Paste the following into your `mcp.json` file.

This configuration allows access only to public data located at `/iplant/home/shared`.

```json
{
    "servers": {
        "ai-verde-datastore": {
            "type": "http",
            "url": "https://mcp.cyverse.ai/mcp"
        }
    }
}
```

### b. Configure MCP Server with CyVerse Account

Pass your CyVerse username and password via HTTP Basic Auth. The header format is: `Basic <base64("username:password")`.

To generate the key, use your CyVerse username (e.g., `foo`) and password (e.g., `mypassword`) separated by a colon (`:`) in the command below:
```bash
echo -n "foo:mypassword" | base64
```

The terminal will then display the resulting Base64-encoded key (e.g., `Zm9vOm15cGFzc3dvcmQ=`).

Copy this key and place it in the `Authorization` header in the `mcp.json` configuration file.
```json
{
    "servers": {
        "ai-verde-datastore": {
            "type": "http",
            "url": "https://mcp.cyverse.ai/mcp",
            "headers": {
				"Authorization": "Basic <YOUR_BASE64_KEY>"
			}
        }
    }
}
```


## 2. Save and Restart VS Code

After saving `mcp.json`, restart VS Code to apply the configuration.

## 3. Verify Connection 

Open Copilot Chat and try running a query, such as:
```bash
list 5 entries in /iplant/home/shared
```

## Reference

[VS Code MCP Server Documentation](https://code.visualstudio.com/docs/copilot/chat/mcp-servers)
