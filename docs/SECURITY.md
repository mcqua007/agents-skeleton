# Security

> Security guidelines, authentication patterns, and threat model.

## Authentication & Authorization

<!-- TODO: Define your auth strategy.
     Example:
     - Authentication: OAuth 2.0 / JWT tokens
     - Authorization: Role-based access control (RBAC)
     - Session management: Secure, httpOnly cookies
-->

## Security Principles

1. **Defense in depth** — Multiple layers of security controls.
2. **Least privilege** — Grant minimum permissions required.
3. **Validate all input** — Parse and validate at every boundary.
4. **Encrypt in transit and at rest** — TLS for transport, encryption for storage.
5. **Fail secure** — Default to deny on errors.

## Data Protection

<!-- TODO: Define data classification and handling.
     | Classification | Examples | Handling |
     |---------------|----------|----------|
     | Public | Marketing content | No restrictions |
     | Internal | Business metrics | Access control |
     | Confidential | User PII | Encryption, audit logs |
     | Secret | API keys, credentials | Vault/KMS, never in code |
-->

## Common Vulnerabilities to Prevent

- **Injection**: Use parameterized queries, never interpolate user input.
- **XSS**: Sanitize output, use Content Security Policy.
- **CSRF**: Use anti-CSRF tokens for state-changing operations.
- **Broken Auth**: Rate-limit login, enforce strong passwords, use MFA.
- **Secrets in Code**: Never commit secrets. Use environment variables or vault.

## Secrets Management

- No secrets in source code or configuration files.
- Use environment variables or a secrets manager (e.g., Vault, AWS Secrets Manager).
- Rotate secrets regularly.
- `.env` and `.env.local` are in `.gitignore`.

## Dependency Security

- Keep dependencies updated.
- Run security audits regularly (`npm audit`, `pip audit`, etc.).
- Pin dependency versions for reproducible builds.
- Review new dependencies before adding.

## Threat Model

<!-- TODO: Document your threat model.
     - What are we protecting?
     - Who are the potential adversaries?
     - What are the attack surfaces?
     - What controls are in place?
-->
