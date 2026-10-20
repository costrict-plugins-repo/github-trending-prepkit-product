---
name: product-opportunity-mapping
description: Use for turning discovery evidence into pursue, monitor, or defer opportunity decisions with dependencies and revisit triggers. Use when the team has evidence but hasn't chosen which opportunity to pursue.
triggers:
  - "opportunity map"
  - "opportunity mapping"
  - "pursue monitor defer"
  - "prioritize opportunities"
  - "opportunity decision"
  - "revisit trigger"
---

> **Standalone Mode:** This skill is part of the prepkit-product plugin.
> - `spec/product-context.md` is optional — provide context inline or create one from the template.
> - Output paths (`research/`, `reports/`) are relative to your current working directory.
> - Facilitation routing is advisory — invoke any skill directly.


# Product Opportunity Mapping

## When To Use
- Discovery has evidence but the team has not chosen which opportunity to pursue
- Multiple unmet needs or frictions compete for attention
- The team is slipping from user opportunities into feature lists
- A defer or monitor decision needs explicit revisit triggers

## Key Concepts
- **Outside-in opportunity framing**: start from customer friction, not planned features
- **Pursue / monitor / defer**: three decision states with different commitment levels
- **Capability fit**: what the team can realistically support right now
- **Revisit triggers**: the evidence or dependency change that should reopen a decision

## Rules
- Opportunity statements must stay in customer language
- "Do nothing" or "not now" is a valid outcome
- When several opportunities are viable, recommend the one with the highest expected user-outcome gain per current delivery effort and defer the rest with explicit revisit triggers — chasing many opportunities simultaneously dilutes impact and extends delivery.
- This workflow owns `research/opportunity-map.md` and `reports/opportunity-decision.md`
- Discovery may invoke this skill, but does not own its artifact paths
- Rank opportunities by expected user-outcome change, not by solution complexity or feature count — an opportunity that changes one critical user behavior outweighs three that ship features without measurable impact
- Apply all output quality gates from `references/product-quality-gates.md`.
- Every `defer` decision must include an explicit revisit trigger in the format: "Revisit when [specific condition or evidence change]." A defer without a trigger is a silent discard — the item will never return to consideration.
- Before finalizing pursue decisions, check for cannibalization: would pursuing this opportunity reduce the value of an existing product or another pursued opportunity? If yes, quantify the overlap and factor it into the decision.

## Required Understanding

- [ ] What is the evidence quality? -> Grade as: `anecdotal` (single report) / `pattern` (3+ consistent signals) / `quantified` (metric-backed) / `validated` (tested with users). If anecdotal, name what's missing before proceeding.
- [ ] What dependencies exist between opportunities? -> Map dependencies: which opportunities enable others, which compete for the same resources, and which would be blocked if another is pursued first.
- [ ] Which unmet need or friction is evidenced? -> discovery inputs
- [ ] What user outcome would improve if we pursue it? -> `## Opportunity Map`
- [ ] What dependencies or capability constraints matter? -> `## Opportunity Map`
- [ ] Which items are `pursue`, `monitor`, or `defer`? -> `## Opportunity Map`
- [ ] What revisit trigger should reopen a deferred item? -> `## Opportunity Map`

## Follow-up Patterns

| Trigger | Probe |
|---|---|
| Opportunity described as a feature | "What user struggle exists before the feature exists?" |
| Everything becomes pursue-now | "Which one still matters most if only one ships?" |
| Defer with no trigger | "What change would make us reconsider this?" |
| Dependency hidden inside effort | "Is this blocked by capability, timing, or weak evidence?" |
| Multiple opportunities target same users | "Could pursuing this opportunity cannibalize an existing product or another pursued opportunity? Name the overlap and quantify the risk." |

## Anti-patterns

- Converting a solution shortlist into fake opportunities
- Treating monitor and defer as the same state
- Deferring work without a trigger to revisit it
- Letting discovery and opportunity mapping create two artifacts for the same decision

## Gotchas

- Do not use this skill to rank features against each other — opportunity mapping operates on unmet user needs, not solution candidates. A map filled with feature names instead of user friction points has skipped the framing step.
- "Monitor" and "defer" are not the same state. Monitor means you are actively watching for a signal that would justify pursuing; defer means you are explicitly not watching and need an explicit revisit trigger to reopen the item.
- An opportunity with no revisit trigger will silently decay in the backlog. Every deferred item must record what change would cause it to be reconsidered.
- Capability fit is a constraint, not a filter. Do not discard high-value opportunities because they are difficult today — record the capability gap as a dependency, not a disqualification.
- This skill owns its own artifact paths (`research/opportunity-map.md`, `reports/opportunity-decision.md`). Do not let discovery synthesis overwrite these paths.

## References

- `references/opportunity-shaping-patterns.md`
- `references/pursue-monitor-defer-framework.md`
- `references/revisit-trigger-patterns.md`

## Chain Position

- **Prerequisites**: Evidenced discovery outputs — JTBD statements, evidence inventory, and validated user problems from `product-discovery-synthesis`.
- **Produces**: An opportunity map with pursue/monitor/defer decisions, dependency notes, and revisit triggers. Saved to `research/opportunity-map.md` and `reports/opportunity-decision.md`.
- **Gate question**: Are the opportunities framed as user needs (not features), and does each decision have a revisit trigger or rationale?
