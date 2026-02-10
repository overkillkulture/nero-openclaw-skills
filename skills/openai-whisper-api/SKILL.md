---
name: openai-whisper-api
description: Transcribe audio via OpenAI Audio Transcriptions API (Whisper).
homepage: https://platform.openai.com/docs/guides/speech-to-text
metadata:
  {
    "openclaw":
      {
        "emoji": "☁️",
        "requires": { "bins": ["curl"], "env": ["OPENAI_API_KEY"] },
      },
  }
---

# OpenAI Whisper API

Transcribe audio files using OpenAI's Whisper API.

## When to use

Use this skill when the user asks to:

- Transcribe audio or video files
- Convert speech to text
- Get transcriptions from recordings
- Process audio files for text extraction

## Quick start

```bash
# Basic transcription
curl https://api.openai.com/v1/audio/transcriptions \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: multipart/form-data" \
  -F file="@audio.mp3" \
  -F model="whisper-1"

# With response format
curl https://api.openai.com/v1/audio/transcriptions \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -F file="@audio.mp3" \
  -F model="whisper-1" \
  -F response_format="text"
```

## Supported formats

- mp3, mp4, mpeg, mpga, m4a, wav, webm

## Response formats

- `json` (default) – includes text and metadata
- `text` – plain text only
- `srt` – SubRip subtitle format
- `vtt` – WebVTT subtitle format
- `verbose_json` – includes word-level timestamps

## Environment

- `OPENAI_API_KEY` – Required for API access

## File size limit

- Maximum 25 MB per file
- For larger files, split into chunks first
