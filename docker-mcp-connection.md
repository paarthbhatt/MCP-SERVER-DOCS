# Connecting Docker Desktop with MCP Server

This guide explains how to connect Docker Desktop to the MCP server.

## Prerequisites

- Docker Desktop installed on your local machine.
- Access to the MCP server.

## Steps

1.  **Configure Docker Daemon:**
    - Open Docker Desktop settings.
    - Go to the "Docker Engine" tab.
    - Add the MCP server's address to the `hosts` array in the `daemon.json` configuration.
    ```json
    {
      "hosts": ["tcp://<mcp-server-ip>:<port>"]
    }
    ```
    - Apply and restart Docker Desktop.

2.  **Set Docker Context:**
    - Open a terminal.
    - Create a new Docker context for the MCP server.
    ```bash
    docker context create mcp-server --docker "host=tcp://<mcp-server-ip>:<port>"
    ```
    - Switch to the new context.
    ```bash
    docker context use mcp-server
    ```

3.  **Verify Connection:**
    - Run a Docker command to verify the connection to the MCP server.
    ```bash
    docker info
    ```
    - You should see information about the MCP server's Docker environment.
