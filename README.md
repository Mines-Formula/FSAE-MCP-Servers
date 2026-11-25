# Overview
`FSAE-MCP` is a read-only MCP server that exposes critical team workflows for coding agents.

## Architecture
This should be designed in a way so that an agent calls the MCP server, the MCP server than calls API endpoints for the relevant services. The MCP server should be hosted on `fsaelinux`

**Insert Diagram Here**

The architecture is intended to be a modular monolith, so that adding capabilities is fairly easy, but from the user perspective, only one MCP ever needs to be registered. However, it should be noted that this is intended for a *read-only* MCP server. If write actions are needed at a future point, a new MCP server with least-privilege permissions should be created.

## How to add
Once implemented, the MCP server can be registered using:
```bash
codex mcp add formula-wiki \
  --url https://your-server/mcp
```

## Next Steps

This is just the MCP server, once this is up and running on `fsaelinux`, you'll want to make a new repo, something along the lines of `FSAE-plugins`. A plugin will be the easiest way to have users access your MCP server, and allow for easy updating to add future skills or MCP's in the future.
