---
applyTo: "**/*.test.*,**/*.spec.*"
---

# Test File Instructions

When writing or modifying test files:

- Follow the testing conventions in `CONVENTIONS.md`.
- Use descriptive test names: `should [behavior] when [condition]`.
- Ensure tests are independent and can run in any order.
- Prefer testing public behavior over internal implementation.
- Run the full test suite to catch regressions.
