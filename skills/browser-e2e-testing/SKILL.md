---
name: browser-e2e-testing
description: Build, review, and maintain end-to-end browser tests for web applications. Use when adding browser coverage for a feature, auditing routes and user journeys, or diagnosing failing or flaky browser tests.
license: MIT
---

# Browser end-to-end testing

## Inspect the application

- Match the scope to the request. For a feature change, trace the affected routes and journeys. For a suite audit, inventory the app's routes, roles, and major workflows.
- Read project instructions, routing and page code, navigation, test configuration, fixtures, existing tests, and documented local and CI commands. Use source to identify routes that navigation can miss, including authenticated routes, direct links, and dynamic routes. Use seeded records for concrete route parameters.
- When practical, explore the running app in a local or test environment with appropriate test accounts and data. Record which behaviors you could verify and which you inferred from source.

## Map and prioritize coverage

- Map each in-scope route or journey to the role, starting state, expected outcome, and existing specs that actually assert it. Keep a route-to-test table for a suite audit. A short list is enough for a focused change.
- Track page smoke checks, such as rendering a heading, separately from journey tests that complete a user action and verify its result. Record uncovered or unverified behavior and prioritize essential journeys, consequential state changes, validation errors, and empty states. Include role-specific behavior when it affects the journey.

## Write resilient tests

- Use the project's existing browser framework and conventions for setup, fixtures, and assertions. If there is no framework, choose one that fits the project's stack and CI when setup is in scope.
- Prefer roles with accessible names, form labels, and stable visible text. Scope ambiguous matches to a meaningful region or data item. Use an intentional, stable test ID when the UI has no suitable user-facing locator. Avoid generated IDs, styling classes, position-based selectors, and chains tied to DOM nesting.
- Assert observable outcomes that establish the expected behavior. For a saved change, verify it persists after reopening when persistence matters. For validation, verify the visible error and the relevant unchanged state. Wait for specific UI states or events with the runner's waiting and retrying assertions. Avoid fixed sleeps.
- Give each test independent browser state and deterministic data. Seed preconditions through existing fixtures or test APIs, isolate records across parallel workers, and arrange cleanup or use disposable state. Exercise the behavior under test through the browser. Use test services or controlled substitutes for external effects such as payments and emails, and report those boundaries.

## Maintain existing coverage

- Add or update coverage for new pages and changed behaviors. Before editing assertions for a failure, reproduce it with the project's targeted command when possible. Examine the first failing step, traces or screenshots, fixture state, and the expected product behavior.
- Classify the failure from evidence. Preserve the assertion for an app regression and report or fix the app within scope. Update the assertion when an intentional behavior change is established. Fix locator, timing, data, or environment problems at their source. If the cause remains uncertain, report it as unresolved.
- Retire a test only when its behavior is obsolete or equivalent coverage exists. Document what was removed and why, and point to the replacement coverage when applicable.

## Verify and report

Run the relevant checks with the project's documented commands. Start with the affected specs and widen the run when a shared fixture, configuration, or journey changes. Report the behaviors covered, edits made, commands and results, remaining gaps, and any checks you could not run. Distinguish a browser run from source review and call out external services replaced during testing.
