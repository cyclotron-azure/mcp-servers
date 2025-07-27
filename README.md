# MCP Servers Index

This repository serves as an index and collection of Model Context Protocol (MCP) servers for the Cyclotron Azure organization. MCP is an open protocol that enables secure connections between host applications (like Claude Desktop, VS Code, or other AI tools) and data sources.

## Purpose

The MCP Servers Index repository provides:

- A curated list of available MCP servers with descriptions and usage instructions
- Example configurations for integrating MCP servers with VS Code and other tools
- Documentation and best practices for MCP server development and deployment
- Sample configurations to help users get started quickly

## Available MCP Servers

| Server Name | Description | VS Code mcp.json | Repository Link | Status |
|-------------|-------------|------------------|-----------------|--------|
| filesystem | File system access for local files | `{ "command": "npx", "args": ["-y", "@modelcontextprotocol/server-filesystem", "/tmp/mcp-demo"] }` | [modelcontextprotocol/server-filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) | Stable |
| memory | In-memory context server for testing and demos | `{ "command": "npx", "args": ["-y", "@modelcontextprotocol/server-memory"] }` | [modelcontextprotocol/server-memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) | Stable |
| ado | Azure DevOps MCP server | `{ "type": "stdio", "command": "npx", "args": ["-y", "@azure-devops/mcp", "your-ado-org-name}"] }` | [microsoft/azure-devops-mcp](https://github.com/microsoft/azure-devops-mcp) | Beta |
| playwright | Playwright MCP server | `{ "command": "npx", "args": ["-y", "@playwright/mcp@latest"], "type": "stdio", "env": {} }` | [playwright/mcp](https://www.npmjs.com/package/@playwright/mcp) | Beta |
| sequential-thinking | Sequential Thinking MCP server | `{ "command": "npx", "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"] }` | [modelcontextprotocol/server-sequential-thinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking) | Beta |
| git | Git MCP server | `{ "command": "uvx", "args": ["mcp-server-git"] }` | [modelcontextprotocol/server-git](https://github.com/modelcontextprotocol/servers/tree/main/src/git) | Beta |
| context7 | Upstash Context7 MCP server | `{ "type": "stdio", "command": "npx", "args": ["-y", "@upstash/context7-mcp"] }` | [upstash/context7](https://github.com/upstash/context7) | Beta |
| microsoft.docs.mcp | Microsoft Docs MCP server | `{ "type": "http", "url": "https://learn.microsoft.com/api/mcp" }` | [microsoftdocs/mcp](https://github.com/microsoftdocs/mcp) | Beta |
| azure-ai-foundry | MCP Server for Azure AI Foundry, providing unified tools for models, knowledge, and evaluation (experimental). | `{ "type": "stdio", "command": "uvx", "args": ["--prerelease=allow", "--from", "git+https://github.com/azure-ai-foundry/mcp-foundry.git", "run-azure-ai-foundry-mcp", "--envFile", "${workspaceFolder}/.env"] }` | [azure-ai-foundry/mcp-foundry](https://github.com/azure-ai-foundry/mcp-foundry) | Beta |

## Additional Resources
  
[View example mcp.json configuration](./mcp.json)

## Using MCP Servers with VS Code

### Prerequisites

1. **VS Code**: Ensure you have Visual Studio Code installed
2. **MCP Extension**: Install the MCP extension for VS Code (when available)
3. **Node.js**: Some MCP servers may require Node.js runtime

### Configuration

To use MCP servers with VS Code, you'll need to create or modify your `mcp.json` configuration file. This file should be placed in your VS Code settings directory or workspace.

#### Basic Setup

1. Create an `mcp.json` file in your project root or VS Code settings folder
2. Configure the MCP servers you want to use
3. Restart VS Code to apply the configuration


### Configuration Options

Each MCP server entry in the configuration supports the following options:

- **`command`**: The executable command to run the server
- **`args`**: Array of command-line arguments
- **`env`**: Environment variables for the server process
- **`cwd`**: Working directory for the server process (optional)

### Environment Variables

Many MCP servers require API keys or other configuration through environment variables. You can set these in:

1. **System environment variables**
2. **The `env` section of your mcp.json**
3. **A `.env` file** (if supported by the server)

### Troubleshooting

#### Common Issues

1. **Server not starting**: Check that the command path is correct and dependencies are installed
2. **Permission errors**: Ensure the server has appropriate file system permissions
3. **API key issues**: Verify that required API keys are properly set in environment variables

#### Debug Mode

To enable debug logging for MCP servers:

1. Set the environment variable `MCP_DEBUG=true`
2. Check VS Code's output panel for MCP-related logs
3. Review server-specific logs in the configured working directory

## Contributing

We welcome contributions to the MCP Servers Index! Here's how you can help:

### Adding a New MCP Server

1. Fork this repository
2. Add your server information to the table above
3. Include example configuration in the `examples/` directory
4. Update documentation as needed
5. Submit a pull request

### Guidelines

- Ensure your MCP server follows the official MCP specification
- Provide clear documentation and usage examples
- Include proper error handling and logging
- Test your configuration examples before submitting

## Resources

- [MCP Official Documentation](https://modelcontextprotocol.io)
- [MCP GitHub Repository](https://github.com/modelcontextprotocol)
- [VS Code MCP Extension](https://marketplace.visualstudio.com/search?term=mcp)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Support

For questions or issues:

1. Check the [Issues](../../issues) section of this repository
2. Review the documentation for specific MCP servers
3. Consult the official MCP documentation

---

*This repository is maintained by the Cyclotron Azure organization. For more information about our projects, visit our [organization page](https://github.com/cyclotron-azure).*