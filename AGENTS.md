# AGENTS.md

> This file is the universal entry point for all AI coding agents.
> It serves as a **table of contents** — not an encyclopedia.
> Keep it under ~100 lines. Point to deeper docs for detail.

## Project Overview

<!-- TODO: Replace with your project description (2-3 sentences) -->

This repository uses an agent-first development workflow. All coding agents
should treat this file as their starting map and navigate to specific docs
as needed for deeper context.

## Quick Reference

```bash
# Build
# TODO: Add build command

# Test
# TODO: Add test command

# Lint
# TODO: Add lint command

# Format
# TODO: Add format command
```

## Architecture

See [ARCHITECTURE.md](ARCHITECTURE.md) for the full codemap, module layout,
dependency directions, and architectural invariants.

## Documentation Map

All deep knowledge lives in `docs/`. Navigate by topic:

| Document                                       | Purpose                                           |
| ---------------------------------------------- | ------------------------------------------------- |
| [docs/DESIGN.md](docs/DESIGN.md)               | UI/UX design conventions and patterns             |
| [docs/FRONTEND.md](docs/FRONTEND.md)           | Frontend-specific guidance and component patterns |
| [docs/PLANS.md](docs/PLANS.md)                 | Current priorities and high-level roadmap         |
| [docs/PRODUCT_SENSE.md](docs/PRODUCT_SENSE.md) | Product principles, user empathy, domain context  |
| [docs/QUALITY_SCORE.md](docs/QUALITY_SCORE.md) | Quality grades by domain and architectural layer  |
| [docs/RELIABILITY.md](docs/RELIABILITY.md)     | Reliability requirements, SLOs, error handling    |
| [docs/SECURITY.md](docs/SECURITY.md)           | Security guidelines, auth patterns, threat model  |

### Deeper Resources

| Directory                                          | Purpose                                        |
| -------------------------------------------------- | ---------------------------------------------- |
| [docs/design-docs/](docs/design-docs/index.md)     | Design documents with verification status      |
| [docs/exec-plans/](docs/exec-plans/)               | Execution plans (active, completed, tech debt) |
| [docs/product-specs/](docs/product-specs/index.md) | Product specifications and requirements        |
| [docs/references/](docs/references/)               | External reference docs, llms.txt files        |
| [docs/generated/](docs/generated/)                 | Auto-generated documentation (schemas, etc.)   |

## Conventions

See [CONVENTIONS.md](CONVENTIONS.md) for coding style, naming, commit messages,
and PR conventions.

## Agent Behavior Expectations

1. **Read before writing.** Navigate to the relevant doc before making changes.
2. **Run validation.** Always run tests and linting before submitting changes.
3. **Update docs.** If your change affects architecture or conventions, update
   the relevant doc file — not this file.
4. **Use exec plans.** For complex multi-step work, create or update an
   execution plan in `docs/exec-plans/active/`.
5. **Progressive disclosure.** Don't try to load everything at once. Start here,
   follow pointers to what you need.
6. **Keep it in the repo.** Knowledge that isn't in the repository doesn't exist
   for agents. Encode decisions, context, and rationale as markdown.

## File Structure Orientation

```
├── AGENTS.md              ← You are here
├── ARCHITECTURE.md        ← Codemap and invariants
├── CONVENTIONS.md         ← Code style and standards
├── docs/                  ← Deep knowledge base
├── .agents/skills/        ← Agent skills (Vercel/Codex ecosystem)
└── src/                   ← Application source (TODO)
```
