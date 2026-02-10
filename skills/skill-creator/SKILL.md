---
name: skill-creator
description: "Meta-skill for creating new OpenClaw skills with proper structure and documentation."
metadata:
  {
    "openclaw":
      {
        "emoji": "🛠️",
        "level": "MASTER",
      },
  }
---

# Skill Creator

The meta-skill for creating new skills. Use this when you need to add a new capability to the system.

## Skill Anatomy

Every skill lives in `skills/<name>/` with this structure:

```
skills/<name>/
├── SKILL.md          # REQUIRED: Main documentation
├── scripts/          # Optional: Execution scripts
├── references/       # Optional: Reference docs
└── assets/           # Optional: Images, data files
```

## SKILL.md Format

```markdown
---
name: my-skill
description: "Short description of what this skill does."
metadata:
  {
    "openclaw":
      {
        "emoji": "🔧",
        "requires": { "bins": ["some-cli"], "envVars": ["API_KEY"] },
        "install": [
          { "id": "brew", "kind": "brew", "formula": "some-cli" }
        ],
      },
  }
---

# Skill Name

Description of the skill and when to use it.

## When to use

- "Trigger phrase one"
- "Trigger phrase two"

## Quick start

\`\`\`bash
some-command --flag value
\`\`\`

## Configuration

Details about setup and environment variables.
```

## Naming Rules

- Use lowercase kebab-case: `my-skill` not `MySkill`
- Be specific: `github-issues` not `github`
- Avoid generic names: `code-analyzer` not `analyzer`

## Core Principles

1. **Concise**: Skills should do one thing well
2. **Degrees of Freedom**: Support common variations
3. **Progressive Disclosure**: Simple first, complex when needed
4. **Self-Documenting**: SKILL.md should be enough to use it

## Creation Process

1. Identify the capability needed
2. Check if similar skill exists
3. Create folder structure
4. Write SKILL.md with examples
5. Add scripts if needed
6. Test with real usage
7. Document edge cases

## Waldorf Level Assignment

| Level | Criteria |
|-------|----------|
| APPRENTICE | Simple operations, learning tool |
| JOURNEYMAN | Moderate complexity, requires some expertise |
| MASTER | Advanced operations, teaches other skills |
