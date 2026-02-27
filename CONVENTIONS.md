# Conventions

> Shared coding standards for humans and agents.
> Referenced by [AGENTS.md](AGENTS.md). Compatible with Aider (`--read CONVENTIONS.md`).

## Code Style

<!-- TODO: Define your code style preferences. Examples below. -->

- Use consistent indentation (see `.editorconfig` for settings).
- Prefer explicit over implicit — avoid magic values and hidden behavior.
- Keep functions focused — one function, one responsibility.
- Names should reveal intent: `getUserById` not `fetch`, `isActive` not `flag`.

## Naming Conventions

<!-- TODO: Customize to your stack. -->

| Element          | Convention  | Example           |
| ---------------- | ----------- | ----------------- |
| Files            | kebab-case  | `user-service.ts` |
| Classes/Types    | PascalCase  | `UserService`     |
| Functions        | camelCase   | `getUserById`     |
| Constants        | UPPER_SNAKE | `MAX_RETRIES`     |
| Database tables  | snake_case  | `user_accounts`   |
| Environment vars | UPPER_SNAKE | `DATABASE_URL`    |

## Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

**Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, `ci`, `perf`

Examples:

- `feat(auth): add OAuth2 login flow`
- `fix(api): handle null response from payment provider`
- `docs(architecture): update dependency diagram`

## Pull Requests

- Keep PRs focused — one logical change per PR.
- Title follows the same conventional commit format.
- Include a description of **what** changed and **why**.
- Reference related issues or exec plans.
- Ensure all checks pass before requesting review.

## Error Handling

<!-- TODO: Define your error handling strategy. -->

- Parse and validate data at system boundaries.
- Use typed errors — avoid bare string throws.
- Log errors with structured context (not just the message).
- Distinguish between recoverable and unrecoverable errors.

## Testing

<!-- TODO: Define your testing expectations. -->

- Write tests for all business logic.
- Name tests descriptively: `should return 404 when user not found`.
- Test behavior, not implementation.
- Keep tests independent — no shared mutable state.

## Documentation

- Update docs when changing architecture or conventions.
- Use JSDoc/docstrings for public APIs.
- Keep README, ARCHITECTURE.md, and AGENTS.md current.
- Exec plans go in `docs/exec-plans/`.
