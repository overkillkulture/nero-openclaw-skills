---
name: slack
description: "Send messages, react, and manage pins in Slack workspaces."
metadata:
  {
    "openclaw":
      {
        "emoji": "📨",
        "requires": { "envVars": ["SLACK_BOT_TOKEN"] },
      },
  }
---

# Slack

Interact with Slack workspaces where the bot has been installed.

## When to use

- "Send a message to #team-updates"
- "React to that with :thumbsup:"
- "Pin the important announcement"
- "Edit my last message"

## Actions

### react
Add an emoji reaction.
```json
{ "action": "react", "channel": "C123...", "timestamp": "1234567890.123456", "emoji": "thumbsup" }
```

### sendMessage
Send a message to a channel.
```json
{ "action": "sendMessage", "channel": "C123...", "text": "Hello team!" }
```

### editMessage
Edit an existing message.
```json
{ "action": "editMessage", "channel": "C123...", "ts": "1234567890.123456", "text": "Updated text" }
```

### pinMessage
Pin a message to a channel.
```json
{ "action": "pinMessage", "channel": "C123...", "timestamp": "1234567890.123456" }
```

## Environment

Requires `SLACK_BOT_TOKEN` with chat:write, reactions:write, pins:write scopes.
