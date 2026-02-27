# Core Beliefs

> Agent-first operating principles that define how this project is built.
> These are foundational — they inform every design decision and convention.

## 1. Repository as Single Source of Truth

Everything an agent needs to know must be in the repository. Knowledge that
exists only in Slack threads, Google Docs, or people's heads is invisible
to agents and will be lost. Encode decisions, context, and rationale as
versioned markdown artifacts.

## 2. Map, Not Manual

Agent instruction files should be tables of contents, not encyclopedias.
Use progressive disclosure: start with a concise entry point, link to
deeper docs. Too much guidance becomes non-guidance.

## 3. Enforce Invariants, Not Implementations

Define strict architectural boundaries and validate them mechanically
(linters, structural tests, CI checks). Within those boundaries, allow
freedom in how solutions are expressed.

## 4. Parse, Don't Validate

All external data must be validated at the system boundary. Use typed
schemas and parsers — never trust unvalidated input shapes.

## 5. Agents Replicate Patterns

Agents will copy patterns they find in the codebase — good and bad.
Invest in golden patterns early. Clean up deviations continuously,
not in painful bursts.

## 6. Corrections Are Cheap, Waiting Is Expensive

In a high-throughput agent workflow, it's often better to ship and
iterate than to block on perfect review. Fix forward when safe.

## 7. Make It Legible

Optimize for agent legibility: clear naming, explicit dependencies,
documented invariants. Anything the agent can't access in-context
effectively doesn't exist.

<!-- Add or modify beliefs as the team's understanding evolves.
     These should be stable principles, not tactical rules. -->
