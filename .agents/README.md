# Agent Skills

This directory follows the [Agent Skills](https://skills.sh) convention,
compatible with **Codex CLI**, **Claude Code**, **Cursor**, **Copilot**,
**Gemini CLI**, **Windsurf**, **Cline**, **Roo Code**, and other agent tools.

## Structure

```
.agents/skills/
└── <skill-name>/
    ├── SKILL.md          # Required — skill instructions (with YAML frontmatter)
    ├── scripts/          # Optional — helper scripts
    ├── references/       # Optional — reference documentation
    └── assets/           # Optional — supporting files
```

## SKILL.md Format

```markdown
---
name: my-skill
description: Short description of what this skill does
---

# My Skill

Instructions for the agent on how and when to use this skill.
```

## Installing Community Skills

```bash
# Install a skill from a GitHub repository
npx skills add <owner/repo>

# Skills are installed to ~/.agents/skills/ (user-level)
# Project-level skills live in .agents/skills/ (this directory)
```

## Skill Discovery

Agents scan for skills in this order:

1. **Project**: `.agents/skills/` (from CWD up to repo root)
2. **User**: `~/.agents/skills/`
3. **System**: `/etc/codex/skills/` (Codex CLI only)
4. **Built-in**: Bundled with the agent tool

## Learn More

- [skills.sh](https://skills.sh) — Skill registry and discovery
- [Agent Skills specification](https://agentskills.io/) — Standard format
