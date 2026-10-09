# agent-boilerplate-v2

A starting point for agent-ready repos: one shared `.agents/` folder, a small set of skills, and verification built in.

Copy `.agents/`, `.cursor/`, `.codex/`, `AGENTS.md`, `NOTICE.md` and `.gitignore` into a new project. Then run the `verify-create` skill in that project to generate its own `verify-<app>` skill with feature maps.

## Known gaps

- `.codex/mcp.json` is a symlink as requested, but Codex documents `.codex/config.toml` (TOML) for project MCP servers. Generate that file from `.agents/mcp.json`, or Codex will not see the servers.
- `.agents/mcp.json` is not a documented path in Cursor or Codex. It is only the source file the symlinks point at.
- Symlinked MCP files and nested skills have not been tested with Cursor cloud agents.
- `.agents/metl/` is empty until its purpose is decided.
