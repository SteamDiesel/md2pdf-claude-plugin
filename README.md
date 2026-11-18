# md2pdf for Claude Code

Ask Claude for a PDF and get one. This plugin connects Claude Code to [md2pdf.free](https://md2pdf.free), a free markdown to PDF converter: **no account, no API key, and your documents are never stored.**

- **MCP server**: `https://md2pdf.free/mcp`, to check documents, make PDFs and hand contracts to md2sign for e-signature
- **`pdf` skill**: teaches Claude the format (markdown plus signature lines and three styles) and how to save PDFs straight to disk
- **`/md2pdf:make`**: a one-step "write it, save the PDF" command

## Install

In Claude Code:

```
/plugin marketplace add SteamDiesel/md2pdf-claude-plugin
/plugin install md2pdf@md2pdf
```

Or from your terminal:

```bash
claude plugin marketplace add SteamDiesel/md2pdf-claude-plugin
claude plugin install md2pdf@md2pdf
```

Just want the MCP server? `claude mcp add --transport http md2pdf https://md2pdf.free/mcp`. In claude.ai or Claude Desktop, add a custom connector with that address. It needs no sign-in.

## Try it

```
/md2pdf:make A one-page project proposal for a website redesign, modern style
```

or just say: *"Turn notes.md into a PDF"*, *"Make a formal letter of offer for Sam Lee as a PDF"*.

## How it works

Write normal markdown. Start with `# Title` (it names the file), and pick a style with one line that doesn't print:

```markdown
<!-- md2sign:style=formal -->
# Consulting Agreement
...
[[signature: Sam Lee <sam@acme.com> | role: Contractor]]
```

Signature lines render as proper signature blocks, exactly as they look in [md2sign](https://md2sign.com). When the document needs signing, skip printing and scanning: Claude can hand it to md2sign with `send_for_signature`, which returns a one-time link that opens it as a draft ready to send for legally binding e-signature.

Limits: 200,000 characters per document, 10 PDFs a minute per IP address.

## Links

- Editor: https://md2pdf.free
- Format for agents: https://md2pdf.free/llms.txt
- Support: support@md2sign.com

MIT licensed. md2pdf is a service by the md2sign team; using it is subject to the [Terms](https://md2pdf.free/terms) and [Privacy Policy](https://md2pdf.free/privacy).
