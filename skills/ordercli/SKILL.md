---
name: ordercli
description: Foodora-only CLI for checking past orders and active order status (Deliveroo WIP).
homepage: https://ordercli.sh
metadata:
  {
    "openclaw":
      {
        "emoji": "🛵",
        "requires": { "bins": ["ordercli"] },
        "install":
          [
            {
              "id": "brew",
              "kind": "brew",
              "formula": "ordercli/tap/ordercli",
              "bins": ["ordercli"],
              "label": "Install ordercli (brew)",
            },
          ],
      },
  }
---

# OrderCLI

Check food delivery orders from the command line.

## When to use

Use this skill when the user asks to:

- Check food delivery order status
- View past orders
- Track active deliveries
- Get order history

## Supported platforms

- ✅ Foodora (fully supported)
- 🚧 Deliveroo (work in progress)

## Setup

```bash
# Login to Foodora
ordercli login foodora

# This opens browser for authentication
```

## Quick start

```bash
# Check active order status
ordercli status

# View past orders
ordercli history

# View specific order details
ordercli order <order-id>

# Watch active order (live updates)
ordercli watch
```

## Common commands

| Command | Description |
|---------|-------------|
| `ordercli status` | Check current/active order |
| `ordercli history` | List past orders |
| `ordercli order <id>` | View order details |
| `ordercli watch` | Live track active delivery |
| `ordercli login <platform>` | Authenticate with platform |

## Output

- Order status with ETA
- Delivery driver location (when available)
- Order items and total
- Restaurant information
