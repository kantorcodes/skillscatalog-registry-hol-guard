# Contributing to SkillsCatalog Registry

Thank you for your interest in contributing skills to the community registry!

## Ways to Contribute

### 1. Submit a New Skill

Create skills that help AI agents accomplish tasks. Good candidates:

- Tools for document creation/manipulation
- API integrations
- Data processing utilities
- Workflow automation
- Developer tools

### 2. Improve Existing Skills

- Fix bugs
- Add features
- Improve documentation
- Add examples

### 3. Report Issues

Found a problem? [Open an issue](https://github.com/SkillsCatalog/registry/issues).

## Skill Submission Guidelines

### Requirements

1. **SKILL.md** - Every skill must have a properly formatted SKILL.md
2. **MANIFEST.json** - Generate using `skill-manifest-generator`
3. **License** - Must include a license (MIT recommended)
4. **No secrets** - Never commit API keys, credentials, or tokens

### SKILL.md Structure

```markdown
---
name: your-skill-name
description: Clear, concise description
version: 1.0.0
license: MIT
author: "@your-github-handle"
tags:
  - relevant
  - tags
---

## Instructions

Clear instructions for how an AI agent should use this skill.

## Examples

At least 2-3 example interactions showing input and expected output.

## Dependencies

List all required:
- Python version
- pip packages
- System dependencies
```

### Naming Conventions

- Use lowercase with hyphens: `my-skill-name`
- Be descriptive: `pdf-merger` not `merger`
- Avoid generic names: `awesome-tool` is not acceptable

### Code Standards

- **Python**: Follow PEP 8, include type hints
- **Error handling**: Graceful failures with clear messages
- **No hardcoded paths**: Use environment variables or config
- **Documentation**: Docstrings for public functions

## Submission Process

### Step 1: Fork and Clone

```bash
git clone https://github.com/YOUR-USERNAME/registry.git
cd registry
```

### Step 2: Create Your Skill

```bash
mkdir -p skills/my-skill/scripts
```

Create `skills/my-skill/SKILL.md` with your skill definition.

### Step 3: Generate MANIFEST.json

```bash
cd skills/skill-manifest-generator
python3 scripts/generate_manifest.py ../my-skill
```

### Step 4: Validate

```bash
cd skills/skill-validator
python3 scripts/validate_skill.py ../my-skill
```

### Step 5: Submit Pull Request

1. Commit your changes
2. Push to your fork
3. Open a pull request against `main`
4. Fill out the PR template

## Review Process

1. **Automated checks** - MANIFEST validation, structure verification
2. **Safety scan** - Optional, for elevated trust tier
3. **Maintainer review** - Manual review of code and documentation

### Review Criteria

- Does the skill serve a clear purpose?
- Is the documentation clear and complete?
- Does the code follow best practices?
- Are there security concerns?

## Safety and Security

### Required

- No malicious code
- No data exfiltration
- No unauthorized network access
- Respect rate limits on external APIs

### Recommended

- Minimal permissions
- Input validation
- Output sanitization
- Clear error messages

## Trust Tiers

Skills can achieve different trust levels:

| Tier | Badge | Requirements |
|------|-------|--------------|
| Community | - | Basic validation passes |
| Verified | Verified | Safety scan passes |
| Official | Official | Maintained by SkillsCatalog team |

## Getting Help

- **Discord**: [Join our community](https://discord.gg/skillscatalog)
- **Discussions**: [GitHub Discussions](https://github.com/SkillsCatalog/registry/discussions)
- **Email**: skills@skillscatalog.ai

## Code of Conduct

Be respectful, constructive, and helpful. We're all here to build useful tools for the AI community.
