# Agent setup

Everything shared lives in `.agents/`. Other tools point at it.

## Layout

```
.agents/
  mcp.json        the one MCP server list
  metl/           (placeholder)
  skills/
    saiyan/       front door: playbooks/ and principals/
    task-create/  turn a goal into a written plan
    task-execute/ run the plan unit by unit
    task-progress/ decisions, progress, what's left
    typescript/   TS rules, applies to .ts and .tsx
    bruh/         restate the last message in plain language (manual only)
    verify-create/ generate a verify-<app> skill for a project
    verify-example/ template: SKILL.md, features/, reference/, scripts/
.cursor/mcp.json  -> ../.agents/mcp.json
.codex/mcp.json   -> ../.agents/mcp.json
```

## How work flows

1. Real engineering work starts with `saiyan`, which picks a playbook.
2. Bigger work: `task-create` writes `.agents/tasks/<slug>/plan.md`, then `task-execute` runs it, logging with `task-progress`.
3. Every project gets a `verify-<app>` skill, made with `verify-create`, so agents can prove behavior on the real app.
4. If you write the same correction twice, fix it in structure (a script, a lint rule, a check), not another paragraph here.

## Notes

- Skills live in `.agents/skills/`, which Cursor and Codex read. Claude Code reads `.claude/skills/`, so add `ln -s ../.agents/skills .claude/skills` if you use it.
- Cursor reads MCP servers from `.cursor/mcp.json`. Codex reads `.codex/config.toml`, not `.codex/mcp.json`. See the README.
- Keep skill names unique across the repo and your global skills. Cursor does not document which one wins on a clash.
