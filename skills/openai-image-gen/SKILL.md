---
name: openai-image-gen
description: Batch-generate images via OpenAI Images API. Random prompt sampler + index.html gallery.
homepage: https://platform.openai.com/docs/api-reference/images
metadata:
  {
    "openclaw":
      {
        "emoji": "🖼️",
        "requires": { "bins": ["python3"], "env": ["OPENAI_API_KEY"] },
      },
  }
---

# OpenAI Image Generation

Batch-generate images using OpenAI's DALL-E API with automatic gallery creation.

## When to use

Use this skill when the user asks to:

- Generate multiple images from prompts
- Create an image gallery
- Batch process image generation
- Sample random prompts for generation

## Quick start

```bash
# Generate single image
python3 generate.py --prompt "A sunset over mountains" --output sunset.png

# Batch generate from prompts file
python3 generate.py --prompts prompts.txt --output-dir ./images/

# Generate with random prompt sampling
python3 generate.py --random-sample 5 --prompts prompts.txt
```

## Features

- Batch generation from text file
- Random prompt sampling
- Automatic `index.html` gallery generation
- Configurable output directory
- Support for different DALL-E models

## Environment

- `OPENAI_API_KEY` – Required for API access

## Output

Images are saved to the specified directory with an auto-generated `index.html` gallery for easy viewing.
