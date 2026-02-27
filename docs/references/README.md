# References

This directory holds external reference material that agents can consult:

- **llms.txt files** — Condensed documentation from external tools and libraries
  (e.g., `nixpacks-llms.txt`, `uv-llms.txt`, `design-system-reference-llms.txt`)
- **API documentation** — Snapshots of relevant API docs
- **Style guides** — External style guides or design system references
- **Standards** — Relevant RFCs, specs, or standards documents

## Naming Convention

- `<tool-name>-llms.txt` — for llms.txt format reference docs
- `<topic>-reference.md` — for markdown reference material

## Why Store References Here?

From the agent's perspective, anything it can't access in-context doesn't
exist. External documentation, wiki pages, and bookmarks are invisible to
agents. Store relevant reference material here so agents can discover and
use it during development.

See [AGENTS.md](../../AGENTS.md) → Documentation Map for how this fits
into the overall knowledge base.
