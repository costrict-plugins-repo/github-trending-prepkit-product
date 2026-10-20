---
name: product-metrics-analysis
description: Use for outcome-based success metrics, baseline and target checks, leading indicators, and counter-metric validation across product work. Use when defining success metrics, building a metric tree, or reviewing KPIs.
triggers:
  - "product metrics"
  - "success metrics"
  - "north star metric"
  - "metric tree"
  - "leading indicators"
  - "counter metrics"
  - "KPI definition"
---

# Product Metrics Analysis

## When To Use
- `## Success Metrics` is empty, vague, or output-based
- A metric has no baseline, target, leading indicator, or counter-metric
- Product work needs a clearer outcome model before validation, PRD, or prioritization
- A metric tree is needed to connect user behavior to team-owned actions
- When analyzing growth strategy, market entry KPIs, or freemium economics — load `references/growth-strategy-economics.md`

## Key Concepts
- **North Star Metric**: best single expression of value delivered
- **Metric tree**: decomposes a top-level metric into controllable leaves
- **Leading / lagging indicators**: leading metrics move earlier and help decision-making sooner
- **Counter-metrics**: protect against harmful local optimization
- **HEART framework**: WHY — business metrics alone (North Star, AARRR, retention) can be gamed by coercive mechanics that produce numbers without genuine user value; HEART adds a UX quality layer that exposes this. WHAT — five categories: Happiness (attitudinal satisfaction), Engagement (interaction depth), Adoption (new user uptake), Retention (continued use), Task success (completion rate, error rate). HOW — apply the Goals-Signals-Metrics (GSM) process: state the goal per category, identify observable signals, then define trackable metrics. Combine with North Star and counter-metrics so teams can see both business outcomes and whether users are achieving real value.

## Rules
- Every primary success metric needs a baseline BEFORE a target. Do not set a target without first establishing the current baseline — a target without a baseline cannot be evaluated as ambitious or realistic. Sequence: measure baseline → analyze baseline → set target.
- Every initiative needs at least one leading indicator and one counter-metric
- When several measurement approaches are possible, present 2-3 options and recommend the smallest metric set that can still change a product decision — tracking metrics nobody acts on wastes instrumentation effort and dilutes team focus.
- Impact must be defined as behavior change, not feature shipment
- Use distributions instead of averages when tail performance matters
- Before defaulting to revenue as the primary KPI, check whether the market stage warrants a user-acquisition-first framing. Conditions: net-new market + low marginal cost + measurable activation/retention + sufficient runway. If conditions are not met, default to revenue or contribution-margin framing. See `references/growth-strategy-economics.md`.
- Apply all output quality gates from `references/product-quality-gates.md`.
- Every primary metric must have a decision trigger: "If [metric] drops below [threshold] for [duration], we will [action]." Decision triggers prevent teams from watching metrics decline without acting. Define triggers before launch, not after.
- If the pack manifest declares a `teamContext` file, use its North Star metric hierarchy as the default. Prioritize metrics that connect to product depth over mere presence.

## Required Understanding

- [ ] What is the evidence quality? -> Grade as: `anecdotal` (single report) / `pattern` (3+ consistent signals) / `quantified` (metric-backed) / `validated` (tested with users). If anecdotal, name what's missing before proceeding.
- [ ] What behavior change do we expect? -> `## Success Metrics`
- [ ] How will we measure it? -> measurement plan
- [ ] What is the current baseline number? -> `## Success Metrics`
- [ ] What is the numeric target? -> `## Success Metrics`
- [ ] Which leading indicators should move first? -> `## Success Metrics`
- [ ] Which counter-metric protects against a bad local optimum? -> `## Success Metrics`

## Follow-up Patterns

| Trigger | Probe |
|---|---|
| Vanity metric presented as success | "Does this number going up mean users get more value?" |
| No leading indicator | "What should move before the main outcome changes?" |
| No counter-metric | "What could get worse if we optimize this aggressively?" |
| Target without rationale | "Why is this number meaningful instead of aspirational?" |

## Anti-patterns

- Measuring output instead of user behavior change
- Setting targets without baselines
- Treating one top-line metric as enough when no leading indicators exist
- Ignoring counter-metrics until after harm appears

## Gotchas

- Do not define metrics before a baseline exists. A target without a baseline cannot be evaluated as ambitious or realistic, and post-launch measurement becomes meaningless.
- Output metrics are not success metrics. "We shipped the feature" is an output. A success metric must name a user behavior that changes — not a team action that completes.
- Averages hide tail performance. When the outcome depends on a small percentage of high-value users or when harm appears in distribution extremes, use cohorts or percentiles, not averages.
- Counter-metrics must be defined before launch. Adding counter-metrics after a metric starts rising is too late — the team will rationalize the rise rather than interrogate it.
- Revenue as the primary KPI in net-new markets produces premature optimization. When market penetration is the strategic bottleneck, user adoption is a better primary metric. Defaulting to revenue framing before checking market stage conditions leads to underinvestment in activation and retention.

## References

- `references/north-star-metric-patterns.md`
- `references/aarrr-pirate-metrics.md`
- `references/metric-tree-construction.md`
- `references/cohort-retention-patterns.md`
- `references/ux-measurement-frameworks.md`
- `references/growth-strategy-economics.md`


## Chain Position

- **Prerequisites**: An initiative with a defined problem and user segment. Ideally, an opportunity map or PRD draft that needs success metrics.
- **Produces**: A metric model with North Star, leading indicators, counter-metrics, baselines, and targets. Written to `## Success Metrics` in `spec/product-context.md`.
- **Gate question**: Does every primary metric have a baseline, a target, and at least one counter-metric?
