# md2pdf plugin

Free markdown to PDF for Claude Code, powered by [md2pdf.free](https://md2pdf.free). No account, no API key, nothing stored.

```
/plugin install md2pdf --marketplace SteamDiesel/md2pdf-claude-plugin
```

- **MCP server** `https://md2pdf.free/mcp`: `render_pdf`, `validate_markdown`, `get_markdown_spec`, `send_for_signature`
- **`pdf` skill**: the markdown format, the three styles, and saving PDFs straight to disk with the public API
- **`/md2pdf:make`**: write or convert a document and save the PDF

Documents with signature lines (`[[signature: Jane Smith <jane@example.com>]]`) render as real signature blocks. When you want them signed, `send_for_signature` opens the document in [md2sign](https://md2sign.com) for legally binding e-signatures.

Limits: 200,000 characters per document, 10 PDFs a minute per IP address. See the [privacy policy](https://md2pdf.free/privacy).
