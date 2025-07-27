# Copilot Instructions for MCP Servers Index

## Project Overview
- This repository is an index and documentation hub for Model Context Protocol (MCP) servers used by Cyclotron Azure.
- It does **not** contain server code, but rather lists, describes, and provides configuration examples for MCP servers.
- The main audience is developers and users integrating MCP servers with tools like VS Code.

## Key Files & Structure
- `README.md`: Main documentation, usage, and contribution guide.
- `mcp.json`: Example configuration for connecting to MCP servers from VS Code or other tools.
- `LICENSE`: MIT license for the repository.

## Essential Knowledge for AI Agents
- **No build/test workflow**: This repo is documentation and configuration only. There are no build scripts, tests, or code to run.
- **MCP server integration**: Focus is on how to configure and use MCP servers, not on server implementation.
- **Configuration patterns**: All MCP server configurations are managed via `mcp.json` (see `README.md` for schema and examples).
- **Environment variables**: API keys and secrets are set via the `env` field in `mcp.json` or system environment variables.
- **Debugging**: Enable debug logs by setting `MCP_DEBUG=true` in the environment.
- **Adding servers**: To add a new MCP server, update the documentation table and provide example configuration.

## Project-Specific Conventions
- All documentation and configuration examples should be clear, minimal, and copy-paste ready.
- Use the table format in `README.md` for listing servers.
- Example configurations must use valid JSON and include all required fields (`command`, `args`, `env`).
- Do not add code, scripts, or server implementations to this repository.

## Integration Points
- Integrates with VS Code via the MCP extension and `mcp.json`.
- References external MCP server packages (e.g., `@modelcontextprotocol/server-filesystem`).
- API keys for third-party services (e.g., Brave Search) are required for some servers.

## Examples
- See `README.md` for a sample `mcp.json` configuration and troubleshooting steps.
- Example server entry:
  ```json
  {
    "command": "npx",
    "args": ["-y", "@modelcontextprotocol/server-brave-search"],
    "env": { "BRAVE_API_KEY": "your-brave-api-key" }
  }
  ```

## What NOT to Do
- Do not add application/server code or tests.
- Do not invent new configuration patterns—follow the documented schema.
- Do not change the table or configuration schema without updating documentation.

---

For more, see `README.md` and https://modelcontextprotocol.io .
