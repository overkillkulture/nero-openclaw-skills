---
name: discord
description: "Interact with Discord communities: send messages, react, create threads/channels, and set bot presence."
metadata:
  {
    "openclaw":
      {
        "emoji": "💬",
        "requires": { "envVars": ["DISCORD_BOT_TOKEN"] },
      },
  }
---

# Discord

Use the Discord bot integration to interact with servers where the bot has been added.

## When to use

- "Send a message to #general"
- "React to that message with 👍"
- "Create a poll in the announcements channel"
- "Start a thread about this topic"

## Actions

### react
Add an emoji reaction to a message.
```json
{ "action": "react", "channelId": "...", "messageId": "...", "emoji": "👍" }
```

### sendMessage
Send a message to a channel.
```json
{ "action": "sendMessage", "channelId": "...", "content": "Hello!" }
```

### poll
Create a poll with options.
```json
{ "action": "poll", "channelId": "...", "question": "Which?", "options": ["A", "B"] }
```

### threadCreate
Create a thread from a message.
```json
{ "action": "threadCreate", "channelId": "...", "messageId": "...", "name": "Discussion" }
```

### channelCreate
Create a new text channel.
```json
{ "action": "channelCreate", "guildId": "...", "name": "new-channel" }
```

### setPresence
Set the bot's presence/status.
```json
{ "action": "setPresence", "status": "online", "activity": { "name": "Building", "type": "PLAYING" } }
```

## Environment

Requires `DISCORD_BOT_TOKEN` with appropriate permissions.
