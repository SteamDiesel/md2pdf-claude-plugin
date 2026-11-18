# md2pdf Claude Code plugin

This plugin mirrors the md2pdf MCP server at `https://md2pdf.free/mcp`. The server (in the private md2pdf app repo, local checkout `../md2pdf`) is the source of truth for tool names, arguments and limits. The skills and READMEs here must describe exactly what that server does.

When the server changes, update:
- `plugins/md2pdf/skills/pdf/SKILL.md`: format, workflow, tools, md2sign handoff
- `plugins/md2pdf/skills/make/SKILL.md`: the guided command
- `README.md` and `plugins/md2pdf/README.md`

Then bump `version` in `plugins/md2pdf/.claude-plugin/plugin.json` (users only get updates when it changes), run `claude plugin validate ./plugins/md2pdf`, and push. To check the current server surface, call `tools/list` on `https://md2pdf.free/mcp`, or read `tests/fixtures/mcp-surface.json` in the app repo.

The server needs no API key. Never add one or any other secret here.
