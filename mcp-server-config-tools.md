# MCP Server Configuration Tools

This document outlines the tools available for configuring the MCP server.

## Configuration File

The main configuration for the MCP server is stored in a `config.json` file. This file contains settings for server ports, tool directories, and logging.

### Example `config.json`:

```json
{
  "server_port": 8080,
  "tool_directory": "/app/tools",
  "log_level": "info"
}
```

## Configuration Management Tools

These tools help manage the MCP server's configuration.

### `get_config`

- **Description:** Retrieves the current server configuration.
- **Usage:**
  ```bash
  mcp-cli get-config
  ```

### `set_config`

- **Description:** Updates a configuration setting.
- **Usage:**
  ```bash
  mcp-cli set-config --key <setting-key> --value <new-value>
  ```
- **Example:**
  ```bash
  mcp-cli set-config --key log_level --value debug
  ```

### `validate_config`

- **Description:** Validates the syntax and values of the configuration file.
- **Usage:**
  ```bash
  mcp-cli validate-config
  ```

## Applying Configuration Changes

After modifying the configuration, the MCP server needs to be restarted for the changes to take effect.

```bash
docker restart mcp-server
```
