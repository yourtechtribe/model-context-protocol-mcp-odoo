[![MseeP.ai Security Assessment Badge](https://mseep.net/pr/yourtechtribe-model-context-protocol-mcp-odoo-badge.png)](https://mseep.ai/app/yourtechtribe-model-context-protocol-mcp-odoo)

# MCP-Odoo

Model Context Protocol server for Odoo integration, allowing AI agents to access and manipulate Odoo data through a standardized interface.

## Overview

MCP-Odoo provides a bridge between Odoo ERP systems and AI agents using the Model Context Protocol (MCP). This enables AI systems to:

- Access partner information
- View and analyze accounting data including invoices and payments
- Perform reconciliation of financial records
- Query vendor bills and customer invoices

## Features

- 🔌 Easy integration with Odoo instances
- 🤖 Standard MCP interface for AI agent compatibility
- 📊 Rich accounting data access
- 🔒 Secure authentication with Odoo

## Installation

```bash
# Clone the repository
git clone https://github.com/yourtechtribe/model-context-protocol-mcp-odoo.git
cd model-context-protocol-mcp-odoo

# Install dependencies
pip install -r requirements.txt
```

## Configuration

Create a `.env` file in the project root with the following variables:

```
ODOO_URL=https://your-odoo-instance.com
ODOO_DB=your_database
ODOO_USERNAME=your_username
ODOO_PASSWORD=your_password
HOST=0.0.0.0
PORT=8080
```

## Usage

Start the MCP server:

```bash
# Using the SSE transport (default)
python -m mcp_odoo_public

# Using stdio for local agent integration
python -m mcp_odoo_public --transport stdio
```

## Documentation

Comprehensive documentation is available in the `docs/` directory:

- [Documentation Home](docs/index.md) - Start here for an overview of all documentation
- [Implementation Guide](docs/implementation_guide.md) - Detailed architecture and implementation details
- [Accounting Functionality](docs/accounting_guide.md) - In-depth guide to accounting features
- [Troubleshooting](docs/troubleshooting.md) - Solutions for common issues
- [Usage Examples](docs/examples/basic_usage.md) - Practical examples to get started

## Development

### Project Structure

- `mcp_odoo_public/`: Main package
  - `odoo/`: Odoo client and related modules
  - `resources/`: MCP resources definitions (tools and schemas)
  - `server.py`: MCP server implementation
  - `config.py`: Configuration management
  - `mcp_instance.py`: FastMCP instance definition

### Adding New Resources

Resources define the capabilities exposed to AI agents through MCP. To add a new resource:

1. Create a new file in the `resources/` directory
2. Define your resource using the `@mcp.tool()` decorator
3. Import your resource in `resources/__init__.py`

For detailed instructions, see the [Implementation Guide](docs/implementation_guide.md).

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

Albert Gil López  
- Email: albert.gil@yourtechtribe.com
- LinkedIn: https://www.linkedin.com/in/albertgilopez/

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. 