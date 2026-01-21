## yapi-mcp-claude-plugin

This repo is a claude code plugin within yapi-mcp-server to understanding api documents from https://github.com/YMFE/yapi.

rename the folder to 'yapi-mcp-plugin' if you like.

This project is not finished yet. basically these command/skills work, currently those are enough for MCP to query and understanding you Yapi interface.
- get_project
- get_cat_menu
- list_cat
- get_interface

## How to use
```bash
---------------------
 /yapi
---------------------
  /yapi-mcp:get_project                      get the Yapi Project information. (plugin:yapi-mcp@inline)
  /yapi-mcp:get_interface                    获得特定的接口信息 (plugin:yapi-mcp@inline)
  /yapi-mcp:list_cat                         Plugin command (plugin:yapi-mcp@inline)
  /yapi-mcp:get_cat_menu   
---------------------
```

```
--------------------
/yapi-mcp:get_interface 接口名称(interface name)
--------------------
```
Claude code will automatically using commands and skills to invoke MCP to retrieve project,category information until it collect enough parameters (such as interface id) to print full information. 

## Installing mcp-server-yapi

follow instructions by:
https://github.com/kales0202/mcp-server-yapi

## Installing mcp agent to claude code
```bash
claude mcp add -transport stdio yapi-mcp-server \
     --env YAPI_BASE_URL=<you-yapi-server>  \
     --env YAPI_TOKEN=<you-token-here> \
     -- node <your-path>/mcp-server-yapi/dist/index.js
```

## Providing MCP server to Claude Code
create .mcp.json with contents below. for more details, see documents.

```json
{
  "yapi-mcp-server": {
    "command": "node",
    "args": [
      "<your-path>/mcp-server-yapi/dist/index.js"
    ],
    "env": {
      "YAPI_BASE_URL": "<you-yapi-server>",
      "YAPI_TOKEN": "<you-token-here>",
      "MCP_DEBUG_CONSOLE": "false"
    }
  }
}
```

note: using node for local development, `npx -y ...` for npm (local)registry or market.


## Documents
- [create plugin](https://code.claude.com/docs/en/plugins)
- [Model Context Protocol Option 3: Add a local stdio server](https://code.claude.com/docs/en/mcp#option-3:-add-a-local-stdio-server)
- [Plugin-provided MCP servers](https://code.claude.com/docs/en/mcp#plugin-provided-mcp-servers)
