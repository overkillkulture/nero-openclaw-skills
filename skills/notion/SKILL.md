---
name: notion
description: "Create, read, and update Notion pages, databases, and blocks."
metadata:
  {
    "openclaw":
      {
        "emoji": "📝",
        "requires": { "envVars": ["NOTION_API_KEY"] },
      },
  }
---

# Notion

Interact with Notion workspaces via the official API.

## When to use

- "Create a new page in my Notes database"
- "Update the status of that project"
- "Add a to-do item to my task list"
- "Search for pages about marketing"

## API Usage

Uses Notion API version 2025-09-03.

### Search
```bash
curl -X POST 'https://api.notion.com/v1/search' \
  -H 'Authorization: Bearer $NOTION_API_KEY' \
  -H 'Notion-Version: 2025-09-03' \
  -d '{"query": "Meeting Notes"}'
```

### Create Page
```bash
curl -X POST 'https://api.notion.com/v1/pages' \
  -H 'Authorization: Bearer $NOTION_API_KEY' \
  -H 'Notion-Version: 2025-09-03' \
  -d '{
    "parent": {"database_id": "..."},
    "properties": {
      "Name": {"title": [{"text": {"content": "New Page"}}]}
    }
  }'
```

### Update Page
```bash
curl -X PATCH 'https://api.notion.com/v1/pages/{page_id}' \
  -H 'Authorization: Bearer $NOTION_API_KEY' \
  -H 'Notion-Version: 2025-09-03' \
  -d '{"properties": {...}}'
```

### Append Blocks
```bash
curl -X PATCH 'https://api.notion.com/v1/blocks/{block_id}/children' \
  -H 'Authorization: Bearer $NOTION_API_KEY' \
  -H 'Notion-Version: 2025-09-03' \
  -d '{"children": [{"paragraph": {"rich_text": [{"text": {"content": "Hello"}}]}}]}'
```

## Environment

Requires `NOTION_API_KEY` (internal integration token).
