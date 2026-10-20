# Revisit Trigger Patterns

Use revisit triggers to keep `monitor` and `defer` decisions alive without pretending they are active.

## Trigger Examples

- Metric trigger: "Revisit if checkout abandonment from shipping surprises stays above 12% for 2 consecutive months"
- Dependency trigger: "Revisit after pricing-service refactor ships"
- Research trigger: "Revisit after 5 target-user interviews confirm the same friction"
- Market trigger: "Revisit if enterprise customers mention this in 3 separate sales cycles"

## Rules

- Prefer concrete events or thresholds
- Avoid "revisit later" with no date, owner, or signal
- Record the trigger in both the opportunity map and the decision memo when relevant
