# Using Server Tools

This document describes how to use the tools available on the MCP server.

## Discovering Tools

- To list all available tools, you can use the `list_tools` command (if available) or refer to the tool definitions in the `tools` directory on the server.

## Executing a Tool

- Tools are executed by sending a JSON-RPC request to the MCP server's tool endpoint.
- The request should specify the tool name and its parameters.

### Example Request:

```json
{
  "jsonrpc": "2.0",
  "method": "execute_tool",
  "params": {
    "tool_name": "example_tool",
    "tool_params": {
      "param1": "value1",
      "param2": "value2"
    }
  },
  "id": 1
}
```

## Tool Definitions

- Each tool has a definition file (e.g., `example-tool.json`) that describes its parameters and functionality.
- An example tool definition is available at [example-tool.json](./example-tool.json).
