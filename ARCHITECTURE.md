# Architecture

> Bird's-eye view of the system. Keep this short — every contributor
> (human and agent) must read it. See the
> [matklad convention](https://matklad.github.io/2021/02/06/ARCHITECTURE.md.html).

## Problem Overview

<!-- TODO: Describe the problem this system solves in 2-3 sentences. -->

## Codemap

<!-- TODO: List the top-level modules/directories and their responsibilities.
     Name important files and types — don't link them (links rot; use symbol search).
     Example:

     ### `src/api/`
     HTTP API layer. Handles request routing, validation, and serialization.
     Key types: `Router`, `ApiError`, `RequestContext`.

     ### `src/domain/`
     Core business logic. No framework dependencies.
     Key types: `Order`, `User`, `PaymentService`.

     ### `src/infra/`
     Infrastructure adapters (database, external APIs, message queues).
     Implements interfaces defined in `src/domain/`.
-->

## Dependency Directions

<!-- TODO: Define the allowed dependency flow between layers.
     Example:

     ```
     Types → Config → Repository → Service → Runtime → UI
     ```

     Cross-cutting concerns (auth, logging, telemetry) enter through
     a single explicit interface: Providers.
-->

## Architectural Invariants

<!-- TODO: List rules that must ALWAYS hold. Especially "absence of something" rules.
     These are the constraints that keep the system coherent.
     Example:

     - Domain logic MUST NOT import from infrastructure or UI layers.
     - All external data MUST be validated at the boundary (parse, don't validate).
     - No direct database queries outside the repository layer.
     - Feature flags are the only mechanism for conditional behavior in production.
-->

## Cross-Cutting Concerns

<!-- TODO: Document how these are handled:
     - Authentication & authorization
     - Logging & observability
     - Error handling
     - Configuration management
     - Testing strategy
-->

## Key Technical Decisions

<!-- TODO: Record significant choices and their rationale.
     Example:

     | Decision | Choice | Rationale |
     |----------|--------|-----------|
     | Database | PostgreSQL | ACID compliance, JSON support, mature ecosystem |
     | API style | REST + JSON | Team familiarity, tooling support |
-->
