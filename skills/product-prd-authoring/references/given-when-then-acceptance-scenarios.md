# Given, When, Then Acceptance Scenarios

Use this file when a PRD needs explicit behavior scenarios.

## Structure

```text
Given [starting state]
When [user or system action]
Then [observable outcome]
```

## Coverage Checklist

- Does the scenario describe observable behavior instead of implementation details?
- Does it include a boundary or failure case when risk is meaningful?
- Is the expected result specific enough that QA can verify pass/fail?

## When To Use

- user-visible behavior
- permission or validation boundaries
- error handling
- state transitions

For richer happy-path, negative-path, and boundary examples, also read `acceptance-criteria-patterns.md`.
