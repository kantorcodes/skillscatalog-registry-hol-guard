# SkillsCatalog Registry

The official community registry for AI agent skills. Skills are reusable capabilities that AI agents can discover, install, and execute.

## What are Skills?

A **skill** is a self-contained capability defined by a `SKILL.md` file. Skills enable AI agents to:

- Search catalogs and discover tools
- Generate documents (PDFs, spreadsheets, presentations)
- Interact with APIs and services
- Automate workflows

Each skill contains:
- `SKILL.md` - Human and agent-readable instructions
- `scripts/` - Executable code (typically Python)
- `MANIFEST.json` - Integrity and metadata (auto-generated)

## Quick Start

### Browse Skills

Explore available skills in the [`skills/`](./skills) directory:

| Skill | Description |
|-------|-------------|
| [skill-search](./skills/skill-search) | Search the catalog for skills |
| [skill-create](./skills/skill-create) | Create new skills from templates |
| [skill-installer](./skills/skill-installer) | Install skills to your agent |
| [skill-publisher](./skills/skill-publisher) | Publish skills to the catalog |
| [skill-validator](./skills/skill-validator) | Validate skill structure |
| [skill-manifest-generator](./skills/skill-manifest-generator) | Generate MANIFEST.json |
| [skill-safety-scanner](./skills/skill-safety-scanner) | Security scan skills |

### Install a Skill

Skills can be installed via the catalog API or directly from this repository:

```bash
# Using skill-installer (recommended)
python3 skill-installer/scripts/install_skill.py skill-search

# Or clone directly
git clone https://github.com/SkillsCatalog/registry.git
```

### Use a Skill

Once installed, reference the skill in your agent:

```
Search the catalog for PDF tools
```

The agent reads `SKILL.md` and executes the appropriate scripts.

## Skill Structure

```
my-skill/
├── SKILL.md           # Required - Skill definition
├── MANIFEST.json      # Auto-generated - Integrity verification
└── scripts/
    └── main.py        # Executable code
```

### SKILL.md Format

```markdown
---
name: my-skill
description: What this skill does
version: 1.0.0
license: MIT
author: "@your-handle"
tags:
  - category
  - keywords
---

## Instructions

How to use this skill...

## Examples

Example interactions...

## Dependencies

- Python 3.9+
- Required packages
```

## Contributing

We welcome community contributions! See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

### Quick Contribution Steps

1. Fork this repository
2. Create your skill in `skills/your-skill-name/`
3. Add `SKILL.md` and scripts
4. Generate `MANIFEST.json` using `skill-manifest-generator`
5. Submit a pull request

## Resources

- **Catalog**: [skillscatalog.ai](https://skillscatalog.ai)
- **Documentation**: [skillscatalog.ai/docs](https://skillscatalog.ai/docs)
- **MANIFEST Schema**: [schemas/manifest.v1.json](./schemas/manifest.v1.json)
- **Templates**: [templates/](./templates)

## License

Skills in this repository are individually licensed (see each skill's `SKILL.md`).

The registry infrastructure (schemas, templates, documentation) is licensed under [MIT](./LICENSE).
