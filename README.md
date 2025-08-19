# Weather MCP Server Integration with Claude Desktop

This project demonstrates how to integrate a custom Weather tool with
**Claude Desktop** through the **Model Context Protocol (MCP) server**.

## Prerequisites

-   [Claude Desktop](https://claude.ai/download)
-   [uv](https://github.com/astral-sh/uv) (Python package manager)
-   Python 3.9+

## Setup Instructions

### 1. Run the MCP Server Manually

To verify the server works, run:

``` bash
uv run weather.py
```

### 2. Configure Claude Desktop

Update or create the Claude Desktop configuration file:

``` bash
~/Library/Application Support/Claude/claude_desktop_config.json
```

Add the following configuration:

``` json
{
  "mcpServers": {
    "weather": {
      "command": "<absolute path of uv>",
      "args": [
        "--directory",
        "<absolute path to your project>",
        "run",
        "weather.py"
      ]
    }
  }
}
```

### 3. Replace Placeholders

-   Replace `<absolute path of uv>` with the full path to the uv
    binary.\
    You can find it using:

    ``` bash
    which uv
    ```

-   Replace `<absolute path to your project>` with the folder path where
    `weather.py` resides.

### 4. Restart Claude Desktop

After updating the configuration, restart Claude Desktop.\
The **Weather MCP tool** should now be available for use.

------------------------------------------------------------------------

## File Structure

    .
    ├── weather.py
    └── README.md
