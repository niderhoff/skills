# Agent Skills Repository

A collection of agent skills for extending AI coding assistant capabilities.

## Installation

Install skills from this repository using the [skills CLI](https://github.com/vercel-labs/skills):

```bash
# List available skills
npx skills add <your-username>/skills --list

# Install a specific skill
npx skills add <your-username>/skills --skill example-skill

# Install all skills
npx skills add <your-username>/skills --all
```

## Available Skills

- **readeck** - Interact with Readeck API to save bookmarks and extract web content

## Creating Your Own Skills

Each skill is a directory containing a `SKILL.md` file with YAML frontmatter:

```yaml
---
name: my-skill
description: What this skill does and when to use it
---
```

See the [Agent Skills specification](https://agentskills.io/specification) for details.

## License

MIT
