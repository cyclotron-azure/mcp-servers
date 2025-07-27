---
mode: 'agent'
model: GPT-4.1
tools: ['githubRepo', 'codebase', 'fetch']
description: 'Add a new MCP server to the README table using a GitHub repo URL.'
---

# Add MCP Server Prompt

You are an intelligent assistant designed to help maintain the MCP Servers Index.

## Goal
Given a GitHub repository URL for an MCP server, your task is to:
1. Use the `#fetch` tool to retrieve the main information about the repository (description, package name, usage, etc.).
2. Extract the relevant configuration details (command, args, env, etc.) for running the MCP server.
3. Add a new row to the MCP servers table in `README.md` with:
   - Server Name
   - Description (from the repo or package)
   - JSON configuration (as shown in the table)
   - Repository link
   - Status (default to "Beta" if not specified)
4. Update `mcp.json` with the new server configuration.

## Guidance
- Only use information that can be verified from the repository or its documentation.
- Format the JSON configuration as a single-line code block for the table.
- Do not add example configurations below the table.
- If the repository does not provide enough information, note this in your response.

## Return format
Update the `README.md` table with the new server entry, following the existing format.

## Example usage
User: Add the MCP server from https://github.com/example/mcp-server-foo
