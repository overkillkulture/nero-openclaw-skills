---
name: openhue
description: Control Philips Hue lights/scenes via the OpenHue CLI.
homepage: https://www.openhue.io/cli
metadata:
  {
    "openclaw":
      {
        "emoji": "💡",
        "requires": { "bins": ["openhue"] },
        "install":
          [
            {
              "id": "brew",
              "kind": "brew",
              "formula": "openhue/tap/openhue-cli",
              "bins": ["openhue"],
              "label": "Install OpenHue CLI (brew)",
            },
          ],
      },
  }
---

# OpenHue CLI

Control Philips Hue lights and scenes from the command line.

## When to use

Use this skill when the user asks to:

- Control smart lights
- Change light colors or brightness
- Activate light scenes
- List available lights or rooms

## Setup

```bash
# Discover bridge and authenticate
openhue setup

# This will prompt you to press the button on your Hue bridge
```

## Quick start

```bash
# List all lights
openhue get lights

# Turn on a light
openhue set light "Living Room" --on

# Turn off a light
openhue set light "Bedroom" --off

# Set brightness (0-100)
openhue set light "Desk Lamp" --brightness 75

# Set color (by name or hex)
openhue set light "Accent" --color red
openhue set light "Accent" --color "#FF5500"

# List scenes
openhue get scenes

# Activate a scene
openhue set scene "Relax"
```

## Common commands

| Command | Description |
|---------|-------------|
| `openhue get lights` | List all lights |
| `openhue get rooms` | List all rooms |
| `openhue get scenes` | List all scenes |
| `openhue set light <name> --on/--off` | Toggle light |
| `openhue set light <name> --brightness <0-100>` | Set brightness |
| `openhue set scene <name>` | Activate scene |

## Environment

- Requires Philips Hue bridge on local network
- One-time authentication via bridge button press
