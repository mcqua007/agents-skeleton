# Skeleton Agents

A **language-agnostic skeleton repository** optimized for AI coding agent
workflows. Clone it, customize the TODOs, and start building with any
agent tool — they all work out of the box.

## What Is This?

This repository provides a ready-made structure for working with AI coding
agents following best practices from OpenAI, Anthropic, GitHub, Google,
Vercel, and Cursor. It implements:

- **`AGENTS.md` as universal entry point** — a ~80-line table of contents
  (not an encyclopedia) that points agents to deeper docs. Inspired by
  [OpenAI's Harness Engineering](https://openai.com/index/harness-engineering/)
  approach.
- **Structured `docs/` knowledge base** — design docs, execution plans,
  product specs, quality scores, security guidelines, and reference material.
  All versioned, all in-repo.
- **Multi-tool agent configs** — native configuration for 6 major agent
  tools with symlinks to avoid drift.
- **Agent Skills** — Vercel/Codex-compatible `.agents/skills/` directory
  for reusable agent capabilities. Look at Vercel's [skills.sh](htps://skills.sh) for skills you can add. Note, if using Claude Code the skills CLI will setup symlinks to `.agents/skills`.

## Supported Agent Tools

| Tool                 | Config Location                                            | How It Reads Instructions                                       |
| -------------------- | ---------------------------------------------------------- | --------------------------------------------------------------- |
| **OpenAI Codex CLI** | `.codex/config.toml`                                       | Reads `AGENTS.md` natively                                      |
| **Claude Code**      | `.claude/settings.json`, `.claude/rules/`                  | Reads `CLAUDE.md` → symlink to `AGENTS.md`                      |
| **GitHub Copilot**   | `.github/copilot-instructions.md`, `.github/instructions/` | Reads `AGENTS.md` + `.github/copilot-instructions.md` → symlink |
| **Cursor**           | `.cursor/rules/*.mdc`                                      | Reads `AGENTS.md` + `.cursor/rules/`                            |
| **Windsurf**         | `.windsurf/rules/*.md`                                     | Reads `.windsurf/rules/`                                        |
| **Gemini CLI**       | `.gemini/settings.json`                                    | Reads `GEMINI.md` → symlink to `AGENTS.md`                      |

## Symlink Strategy

`AGENTS.md` is the single source of truth. Other tools that expect their
own named file get a symlink:

```
AGENTS.md                              ← Canonical (Codex, Copilot, Cursor)
CLAUDE.md → AGENTS.md                  ← Claude Code
GEMINI.md → AGENTS.md                  ← Gemini CLI
.github/copilot-instructions.md → ../AGENTS.md  ← GitHub Copilot (belt-and-suspenders)
```

## Repository Structure

```
├── AGENTS.md                    # Universal agent entry point (~80 lines)
├── ARCHITECTURE.md              # System codemap (matklad convention)
├── CONVENTIONS.md               # Code style, naming, commit standards
├── CLAUDE.md → AGENTS.md       # Symlink for Claude Code
├── GEMINI.md → AGENTS.md       # Symlink for Gemini CLI
├── README.md                    # This file
│
├── .agents/                     # Agent skills (Vercel/Codex ecosystem)
│   ├── README.md
│   └── skills/
│       └── find-skills/
│           └── SKILL.md
│
├── .claude/                     # Claude Code config
│   ├── settings.json
│   └── rules/
│       ├── code-style.md
│       ├── testing.md
│       └── documentation.md
│
├── .codex/                      # Codex CLI config
│   └── config.toml
│
├── .cursor/                     # Cursor config
│   └── rules/
│       ├── general.mdc
│       └── example-scoped.mdc
│
├── .gemini/                     # Gemini CLI config
│   └── settings.json
│
├── .github/                     # GitHub / Copilot config
│   ├── copilot-instructions.md → ../AGENTS.md
│   └── instructions/
│       └── example.instructions.md
│
├── .windsurf/                   # Windsurf config
│   └── rules/
│       └── general.md
│
├── docs/                        # Knowledge base (OpenAI structure)
│   ├── DESIGN.md                # UI/UX design conventions
│   ├── FRONTEND.md              # Frontend-specific guidance
│   ├── PLANS.md                 # Roadmap and priorities
│   ├── PRODUCT_SENSE.md         # Product principles and domain context
│   ├── QUALITY_SCORE.md         # Quality grades by domain/layer
│   ├── RELIABILITY.md           # SLOs, error handling, monitoring
│   ├── SECURITY.md              # Security guidelines and threat model
│   ├── design-docs/
│   │   ├── index.md             # Design doc catalogue
│   │   └── core-beliefs.md      # Agent-first operating principles
│   ├── exec-plans/
│   │   ├── active/              # In-progress execution plans
│   │   ├── completed/           # Finished execution plans
│   │   ├── TEMPLATE.md          # Exec plan template
│   │   └── tech-debt-tracker.md # Known tech debt
│   ├── generated/
│   │   └── db-schema.md         # Auto-generated schema docs
│   ├── product-specs/
│   │   └── index.md             # Spec catalogue
│   └── references/
│       └── README.md            # External reference docs (llms.txt, etc.)
│
├── .editorconfig                # Universal editor settings
├── .gitattributes               # Line ending normalization
└── .gitignore                   # OS, IDE, dependency, build ignores
```

## Getting Started

### 1. Clone or Use as Template

```bash
# Clone
git clone https://github.com/mcqua007/agents-skeleton.git my-project
cd my-project

# Or use GitHub's "Use this template" button
```

### 2. Customize AGENTS.md

Edit `AGENTS.md` to describe your project. Fill in:

- Project overview (what does it do?)
- Build/test/lint/format commands
- Any project-specific agent behavior rules

The symlinks (`CLAUDE.md`, `GEMINI.md`, `.github/copilot-instructions.md`)
will automatically pick up your changes.

### 3. Fill In Architecture

Edit `ARCHITECTURE.md` with your system's codemap, dependency directions,
and architectural invariants.

### 4. Customize Tool-Specific Rules (Only When Needed)

Tool-specific rule directories already point to the shared docs. You only
need to add files here for **tool-specific overrides** like scoped rules:

- `.claude/rules/` — Claude Code (`paths:` frontmatter for file scoping, `@` imports)
- `.cursor/rules/` — Cursor (`globs:` frontmatter for file scoping)
- `.windsurf/rules/` — Windsurf (12,000 char limit per file)
- `.github/instructions/` — Copilot (`applyTo:` frontmatter for file scoping)

All general conventions belong in `CONVENTIONS.md` — not duplicated per tool.

### 5. Start Building

```bash
# Verify symlinks work
ls -la CLAUDE.md GEMINI.md .github/copilot-instructions.md

# Start your agent tool of choice and begin working
```

## Philosophy

This skeleton follows the principles from
[OpenAI's Harness Engineering](https://openai.com/index/harness-engineering/):

1. **AGENTS.md is a map, not a manual** — ~80 lines that point to deeper docs.
   Too much guidance becomes non-guidance.
2. **Repository knowledge is the system of record** — if it's not in the repo,
   it doesn't exist for the agent.
3. **Progressive disclosure** — agents start with AGENTS.md and navigate to
   what they need. Don't overwhelm up front.
4. **Enforce invariants, not implementations** — define boundaries mechanically,
   allow freedom within them.
5. **Keep docs alive** — use exec plans, tech debt tracking, and quality scores
   as living documents, not write-once artifacts.

## DRY Across Agent Tools

A core design principle of this skeleton is **Don't Repeat Yourself** across
agent tool configurations. Every agent tool has its own config directory and
format, but the actual knowledge lives in **shared canonical files**:

| Canonical File    | What It Contains                                    |
| ----------------- | --------------------------------------------------- |
| `AGENTS.md`       | Project orientation, doc map, agent behavior rules  |
| `CONVENTIONS.md`  | Code style, naming, testing, commits, documentation |
| `ARCHITECTURE.md` | Codemap, invariants, dependency directions          |
| `.editorconfig`   | Indent style, line endings, charset                 |

**Tool-specific config files are pointers, not copies.** Each tool's rules
directory (`.claude/rules/`, `.cursor/rules/`, `.windsurf/rules/`, etc.)
contains files that reference the shared docs rather than duplicating them.

```
                    ┌─────────────────────┐
                    │     AGENTS.md       │  ← Single source of truth
                    │   CONVENTIONS.md    │     for agent instructions
                    │  ARCHITECTURE.md    │
                    └────────┬────────────┘
                             │
          ┌──────────────────┼──────────────────┐
          │                  │                   │
    ┌─────▼─────┐    ┌──────▼──────┐    ┌───────▼──────┐
    │ .claude/   │    │ .cursor/    │    │ .windsurf/   │  ...
    │ rules/     │    │ rules/      │    │ rules/       │
    │ (pointers) │    │ (pointers)  │    │ (pointers)   │
    └────────────┘    └─────────────┘    └──────────────┘
```

**Why this matters:**

- **Edit once, apply everywhere.** Change a convention in `CONVENTIONS.md`
  and every agent tool picks it up.
- **No drift.** Tool-specific copies inevitably diverge. Pointers can't.
- **Symlinks for instruction files.** `CLAUDE.md`, `GEMINI.md`, and
  `.github/copilot-instructions.md` are all symlinks to `AGENTS.md`.
- **Tool configs are for tool-specific settings only.** Frontmatter syntax
  (`paths:`, `globs:`, `applyTo:`), approval policies, model selection —
  things that genuinely differ per tool.

When you clone this skeleton: edit the shared files, and every agent tool
automatically gets the same instructions.

## References

- [OpenAI: Harness Engineering](https://openai.com/index/harness-engineering/) — Agent-first development at scale
- [OpenAI: Codex Exec Plans](https://cookbook.openai.com/articles/codex_exec_plans) — Execution plan methodology
- [ARCHITECTURE.md convention](https://matklad.github.io/2021/02/06/ARCHITECTURE.md.html) — Codemap for new contributors
- [agents.md](https://agents.md/) — Universal AGENTS.md standard
- [Agent Skills](https://skills.sh) — Skill registry and ecosystem
- [Conventional Commits](https://www.conventionalcommits.org/) — Commit message standard

## License

[MIT](LICENSE)
