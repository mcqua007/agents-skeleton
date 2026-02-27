# Frontend Guidelines

> Frontend-specific architecture, patterns, and tooling guidance.

<!-- TODO: Customize for your framework (React, Vue, Svelte, etc.) -->

## Architecture

<!-- TODO: Define frontend architecture.
     Example:
     - Component structure (pages, layouts, shared components)
     - State management approach
     - Data fetching patterns
     - Routing conventions
-->

## Component Conventions

- One primary export per component file.
- Co-locate styles, tests, and stories with components.
- Extract reusable logic into hooks/composables/utilities.
- Props interfaces must be explicitly typed.

## Performance

- Lazy-load routes and heavy components.
- Optimize images and assets.
- Monitor and budget bundle size.
- Avoid unnecessary re-renders.

## Accessibility

- All interactive elements must have accessible labels.
- Support keyboard navigation.
- Test with screen readers.
- Maintain sufficient color contrast ratios.

## Testing

- Component tests for interactive behavior.
- Visual regression tests for critical UI.
- E2E tests for key user journeys.
