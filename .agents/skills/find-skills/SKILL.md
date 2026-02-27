---
name: find-skills
description: Helps discover and install agent skills when looking for functionality that might exist as an installable skill.
---

# Find Skills

Use this skill when a user asks about extending agent capabilities,
finding tools for specific tasks, or when functionality might exist
as a community skill.

## When to Use

- User asks "how do I do X" and X might be a skill
- User asks to "find a skill for..." or "is there a skill that can..."
- User wants to extend agent capabilities
- Looking for domain-specific tooling or integrations

## How to Search

1. Check the skill registry at [skills.sh](https://skills.sh)
2. Search GitHub for repositories with `.agents/skills/` directories
3. Look for `SKILL.md` files in relevant repositories

## Installing a Skill

```bash
npx skills add <owner/repo>
```

## Tips

- Skills are user-level by default (`~/.agents/skills/`)
- Project-specific skills go in `.agents/skills/` within the repo
- Each skill must have a `SKILL.md` with `name` and `description` frontmatter
