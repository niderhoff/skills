# Contributing to Agent Skills

Thank you for your interest in contributing! This guide will help you create and submit skills.

## Creating a New Skill

### 1. Use the Template

The `example-skill` directory provides a complete template. Copy it to create a new skill:

```bash
cp -r skills/example-skill skills/your-skill-name
cd skills/your-skill-name
```

### 2. Update SKILL.md

Edit the frontmatter in `SKILL.md`:

```yaml
---
name: your-skill-name  # Must match directory name
description: Clear description of what the skill does and when to use it
license: MIT
metadata:
  author: your-name
  version: "1.0.0"
---
```

**Name requirements:**
- 1-64 characters
- Lowercase letters, numbers, and hyphens only
- No consecutive hyphens (`--`)
- Must match the parent directory name

**Description requirements:**
- 1-1024 characters
- Clearly explain what the skill does
- Include keywords to help agents find it
- Mention when to use the skill

### 3. Write Instructions

The Markdown body should contain:

- **When to Use This Skill**: Clear criteria for activation
- **Step-by-Step Instructions**: Detailed workflow
- **Examples**: Input/output examples where helpful
- **Error Handling**: Common issues and solutions
- **References**: Links to additional documentation

Keep the main SKILL.md under 500 lines. Move detailed docs to `references/`.

### 4. Add Supporting Files (Optional)

#### scripts/
- Executable code (Python, Bash, JavaScript, etc.)
- Include clear documentation and error handling
- Make files executable: `chmod +x scripts/yourscript.py`

#### references/
- Detailed technical documentation
- API references
- Domain-specific knowledge
- Keep files focused and concise

#### assets/
- Templates (JSON, YAML, etc.)
- Images and diagrams
- Data files and schemas

### 5. Test Your Skill

Before submitting:

1. **Validate the format**:
   ```bash
   npx skills-ref validate skills/your-skill-name
   ```

2. **Test installation**:
   ```bash
   npx skills add . --skill your-skill-name
   ```

3. **Verify with an agent**: Use the skill with an AI coding assistant to ensure it works as expected

## Skill Guidelines

### Progressive Disclosure

Structure your skill to minimize context usage:

1. **Metadata** (~100 tokens): Name and description
2. **Instructions** (<5000 tokens): Main SKILL.md
3. **Resources** (as needed): Additional files

### Best Practices

- ✅ Use clear, specific descriptions with relevant keywords
- ✅ Provide step-by-step instructions
- ✅ Include practical examples
- ✅ Document error handling
- ✅ Keep files focused and organized
- ❌ Don't include large files in SKILL.md
- ❌ Don't use deeply nested references
- ❌ Don't assume specific tools are available

### Compatibility

Skills should work across multiple agents. Avoid:
- Agent-specific features
- Hardcoded paths
- Assumptions about the execution environment

If your skill requires specific tools, document them in the `compatibility` field:

```yaml
compatibility: Requires git, python3, and jq
```

## Submitting Your Skill

### 1. Create a Branch

```bash
git checkout -b add-your-skill-name
```

### 2. Commit Your Changes

```bash
git add skills/your-skill-name
git commit -m "Add your-skill-name skill"
```

### 3. Push and Create a Pull Request

```bash
git push origin add-your-skill-name
```

Then create a pull request on GitHub with:
- Clear description of what the skill does
- Examples of when to use it
- Any testing you've performed

## Questions?

- Check the [Agent Skills specification](https://agentskills.io/specification)
- Browse [example skills](https://github.com/vercel-labs/agent-skills)
- Open an issue if you need help

Thank you for contributing!
