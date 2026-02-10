---
name: nano-pdf
description: Edit PDFs with natural-language instructions using the nano-pdf CLI.
homepage: https://pypi.org/project/nano-pdf/
metadata:
  {
    "openclaw":
      {
        "emoji": "📄",
        "requires": { "bins": ["nano-pdf"] },
        "install":
          [
            {
              "id": "uv",
              "kind": "uv",
              "package": "nano-pdf",
              "bins": ["nano-pdf"],
              "label": "Install nano-pdf (uv)",
            },
          ],
      },
  }
---

# Nano PDF

Edit PDFs with natural-language instructions.

## When to use

Use this skill when the user asks to:

- Edit an existing PDF
- Extract or rearrange pages
- Merge multiple PDFs
- Add watermarks or text overlays

## Quick start

```bash
nano-pdf "Remove pages 3-5" input.pdf -o output.pdf
nano-pdf "Add a watermark saying DRAFT" input.pdf
nano-pdf "Merge these PDFs" file1.pdf file2.pdf -o merged.pdf
```

## Key flags

- `-o, --output` – output file path
- `--model` – override default model (default: gemini/gemini-2.0-flash)
- `--verbose` – show detailed processing info

## Environment

- `GEMINI_API_KEY` or `OPENAI_API_KEY` depending on model used
