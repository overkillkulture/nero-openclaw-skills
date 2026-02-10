---
name: coding-agent
description: Run Codex CLI, Claude Code, OpenCode, or Pi Coding Agent via background process for programmatic control.
metadata:
  {
    "openclaw": { "emoji": "🧩", "requires": { "anyBins": ["claude", "codex", "opencode", "pi"] } },
  }
---

# Coding Agent (bash-first)

Use **bash** (with optional background mode) for all coding agent work.

## PTY Mode Required!

Coding agents (Codex, Claude Code, Pi) are **interactive terminal applications** that need a pseudo-terminal (PTY) to work correctly.

**Always use `pty:true`** when running coding agents:

```bash
# Correct - with PTY
bash pty:true command:"codex exec 'Your prompt'"

# Wrong - no PTY, agent may break
bash command:"codex exec 'Your prompt'"
```

## Quick Start: One-Shot Tasks

```bash
# Quick chat (Codex needs a git repo!)
SCRATCH=$(mktemp -d) && cd $SCRATCH && git init && codex exec "Your prompt here"

# Or in a real project - with PTY!
bash pty:true workdir:~/Projects/myproject command:"codex exec 'Add error handling'"
```

## The Pattern: workdir + background + pty

For longer tasks, use background mode with PTY:

```bash
# Start agent in target directory (with PTY!)
bash pty:true workdir:~/project background:true command:"codex exec --full-auto 'Build a snake game'"
# Returns sessionId for tracking

# Monitor progress
process action:log sessionId:XXX

# Check if done
process action:poll sessionId:XXX

# Send input (if agent asks a question)
process action:write sessionId:XXX data:"y"

# Kill if needed
process action:kill sessionId:XXX
```

## Codex CLI

**Model:** `gpt-5.2-codex` is the default

### Flags

| Flag | Effect |
|------|--------|
| `exec "prompt"` | One-shot execution, exits when done |
| `--full-auto` | Sandboxed but auto-approves in workspace |
| `--yolo` | NO sandbox, NO approvals (fastest, most dangerous) |

### Building/Creating

```bash
# Quick one-shot (auto-approves)
bash pty:true workdir:~/project command:"codex exec --full-auto 'Build a dark mode toggle'"

# Background for longer work
bash pty:true workdir:~/project background:true command:"codex --yolo 'Refactor the auth module'"
```

## Claude Code

```bash
bash pty:true workdir:~/project command:"claude 'Your task'"
bash pty:true workdir:~/project background:true command:"claude 'Your task'"
```

## Pi Coding Agent

```bash
# Install: npm install -g @mariozechner/pi-coding-agent
bash pty:true workdir:~/project command:"pi 'Your task'"
bash pty:true command:"pi -p 'Summarize src/'"
```

## Rules

1. **Always use pty:true** - coding agents need a terminal!
2. **Respect tool choice** - if user asks for Codex, use Codex
3. **Be patient** - don't kill sessions because they're "slow"
4. **Monitor with process:log** - check progress without interfering
5. **--full-auto for building** - auto-approves changes
6. **Parallel is OK** - run many Codex processes at once for batch work
