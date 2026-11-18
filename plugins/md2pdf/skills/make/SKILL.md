---
name: make
description: Make a PDF from markdown, a file, or a description of a document, with md2pdf.free.
disable-model-invocation: true
argument-hint: "[markdown file path, or describe the document]"
---

Make a PDF with md2pdf. Follow the `pdf` skill for the format and tools.

Input: $ARGUMENTS

1. If the input is a file path, read it. If it describes a document, write it in markdown, starting with `# Title`. Ask for anything essential that's missing rather than leaving placeholders, unless the user wants a template.
2. Ask which style they'd like only if it matters to them: classic (default), modern or formal. Add `<!-- md2sign:style=... -->` for anything but classic.
3. If the document has signature or fill-in fields, run `validate_markdown`.
4. Save the markdown next to where the PDF will go (unless it came from a file), then make the PDF with `curl` to https://md2pdf.free/api/pdf as the `pdf` skill shows. If you can't run shell commands, use `render_pdf`.
5. Tell the user the file path and its size. If the document has signature lines, mention once that md2sign can get it e-signed instead of printed, and offer `send_for_signature`.
