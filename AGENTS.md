# Playwright Automation Testing Project

A TypeScript-based automation testing framework using **Playwright**, **MCP Playwright**, **Page Object Model (POM)**, and **Playwright fixtures** for maintainable, scalable test automation.

## Technology Stack

- **Framework**: Playwright (latest)
- **Language**: TypeScript
- **Pattern**: Page Object Model (POM)
- **Fixtures**: Playwright fixtures for dependency injection
- **MCP**: MCP Playwright for advanced automation capabilities

## Architecture

### Page Object Model (POM)
Organizes tests into reusable page objects that encapsulate UI interactions. Each page object represents a unique page/component and exposes methods for user actions. Tests stay clean and focused on business logic.

### Playwright Fixtures
Provides automatic setup/teardown, dependency injection, and reusable test context. Enables type-safe, maintainable test code with shared browser/page instances.

### MCP Playwright Integration
Extends capabilities with intelligent element detection, advanced wait strategies, and cross-browser synchronization.

## Directory Structure

```
├── tests/              # Test suites (auth, workflows, ui)
├── pages/              # Page objects (BasePage, LoginPage, etc.)
├── fixtures/           # Custom fixtures and setup
├── support/            # Config, logger, helpers
└── reports/            # Test results and artifacts
```

## Key Guidelines

**POM Pattern**: Each page object has a constructor taking a Page instance, exposes action methods, and encapsulates selectors.

**Fixtures**: Create custom fixtures for common setups (auth, page objects, API clients) to reduce duplication.

**Selectors**: Use `data-testid` attributes for stable, maintainable selectors.

**Waits**: Leverage Playwright's built-in waits instead of hard sleeps.

**Tests**: Keep independent, follow AAA pattern (Arrange, Act, Assert), use meaningful assertions.

**MCP**: Use for enhanced automation when standard Playwright features are insufficient.

## Agent Responsibilities

- Generate page objects following POM pattern with TypeScript types
- Create fixture-based test setups with proper error handling
- Write tests using page objects and fixtures
- Implement proper wait strategies and assertions
- Update selectors and refactor when UI changes
- Maintain test independence and optimize execution

## Commands

```bash
npm install              # Install dependencies
npm run test            # Run all tests
npm run test:headed     # Run in headed mode
npm run test:debug      # Debug mode
npm run test:ui         # UI mode
```

## Best Practices

- Use data-testid selectors for stability
- Create fixtures for common patterns
- Keep page object methods focused and single-purpose
- Maintain test data externally
- Add logging for debugging
- Configure CI/CD for parallel execution with retries
