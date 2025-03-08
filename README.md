# Weather MCP Server

This is a learning project exploring the Model Context Protocol (MCP) concept. The project implements a simple weather service that provides weather alerts and forecasts using the National Weather Service (NWS) API.

## About This Project

This project was created as an exercise in learning and implementing MCP (Model Context Protocol) following the documentation at:
https://modelcontextprotocol.io/quickstart/server#core-mcp-concepts

MCP is a protocol that allows AI assistants to access external tools and data sources. This project demonstrates how to create an MCP server that can be used with Claude or other MCP-compatible assistants.

## Features

- `get_alerts`: Retrieve active weather alerts for a US state
- `get_forecast`: Get weather forecast for a specific location using latitude and longitude

## Requirements

- Python 3.9+
- `httpx` library
- `mcp` library

## Setup Instructions

1. Clone this repository
2. Install the dependencies:

   ```
   pip install mcp httpx
   ```

   or use uv:

   ```
   uv pip install mcp httpx
   ```

3. Configure the MCP server in your AI assistant:

### In Claude Desktop

Add the following to the Claude Desktop configuration:

```json
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": [
        "--directory",
        "/ABSOLUTE/PATH/TO/PARENT/FOLDER/weather",
        "run",
        "weather.py"
      ]
    }
  }
}
```

### In Cursor

Go to Cursor Settings -> MCP Servers -> Add MCP Server

- Name: Weather (or any name you prefer)
- Type: Command
- Command: uv run /ABSOLUTE/PATH/TO/PARENT/FOLDER/weather/weather.py

## Usage Examples

Once the MCP server is set up, you can ask the AI assistant to:

- "What are the current weather alerts in CA?"
- "Get me the weather forecast for latitude 37.7749 and longitude -122.4194"

## License

This project is for educational purposes.

## Acknowledgements

- National Weather Service (NWS) API for providing weather data
- MCP documentation for guidance on implementing the server
