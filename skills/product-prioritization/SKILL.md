---
name: product-prioritization
description: Use for scoring candidate slices once opportunity context, metric context, and tradeoff criteria are explicit. Use when prioritizing features, ranking backlog items, or applying RICE, MoSCoW, or ICE frameworks.
triggers:
  - "prioritize features"
  - "feature prioritization"
  - "RICE framework"
  - "MoSCoW prioritization"
  - "backlog prioritization"
  - "rank backlog"
---

> **Standalone Mode:** This skill is part of the prepkit-product plugin.
> - `spec/product-context.md` is optional — provide context inline or create one from the template.
> - Output paths (`research/`, `reports/`) are relative to your current working directory.
> - Facilitation routing is advisory — invoke any skill directly.


# Product Prioritization

## When To Use
- The active initiative has more candidate slices than the team can execute
- Stakeholders disagree on what to build next inside one opportunity area
- Criteria need to be made explicit before scoring starts
- Deferred items need revisit triggers instead of silent backlog drift

## Key Concepts
- **RICE / ICE / MoSCoW**: different tools for different decision contexts
- **Opportunity context**: scoring must be anchored to a pursued opportunity or an explicit exception
- **Tradeoff visibility**: ranking is structured conversation, not algorithmic truth
- **Revisit triggers**: what would cause a deferred option to be reconsidered?
- **Opportunity cost**: every item you build is something else you cannot build during the same period. When comparing candidates, name what you are giving up by choosing each option — not just what you gain. This makes the tradeoff visible and prevents the illusion that all high-scoring items can ship simultaneously.
- **Regret minimization**: when scores are close, ask which option you would regret NOT doing in 6–12 months. This surfaces irreversibility, strategic positioning, and learning value that scoring frameworks underweight.

## Rules
- Do not score until an opportunity map exists or a documented exception is explicit
- Do not score until metric context is clear enough to judge impact
- Agree on criteria definitions before scoring
- Effort must be estimated by implementers, not requesters
- When two options are close on impact, prefer the smaller slice with lower delivery time and dependency risk — faster delivery creates faster learning loops and earlier user value.
- Scores structure conversation; they do not replace judgment
- Score items by expected user-outcome improvement, not by feature scope or stakeholder enthusiasm — a small change that shifts a key user behavior outranks a large feature that ships output without measurable outcome change
- For net-new market entry decisions where marginal cost is low, activation/retention is measurable, and runway is sufficient, consider switching the primary scoring metric from revenue impact to user adoption — user-count-first scoring reflects the actual strategic lever when market penetration is the bottleneck. All four conditions must hold: (1) net-new market, (2) low marginal cost, (3) measurable activation/retention, (4) sufficient runway. When any condition is not met, default to revenue or contribution-margin impact. See `packs/product/skills/domain/product-metrics-analysis/references/growth-strategy-economics.md`.
- Apply all output quality gates from `references/product-quality-gates.md`.
- Before finalizing scores, run an honest confidence calibration: for each Impact and Reach estimate, ask "How confident am I in this number — high (data-backed), medium (informed estimate), or low (gut feel)?" Low-confidence scores must be flagged and treated as ranges, not points. Do not present low-confidence scores with false precision.

## Required Understanding

- [ ] What is the evidence quality? -> Grade as: `anecdotal` (single report) / `pattern` (3+ consistent signals) / `quantified` (metric-backed) / `validated` (tested with users). If anecdotal, name what's missing before proceeding.
- [ ] Which candidates are actually being compared? -> input set
- [ ] What opportunity map or documented exception frames this decision? -> `## Opportunity Map` or artifact note
- [ ] Which framework and criteria are agreed before scoring? -> `## Prioritization Rationale`
- [ ] What outcome metric defines impact? -> `## Success Metrics`
- [ ] What revisit triggers should be recorded for deferred or tied options? -> `## Opportunity Map` + `## Prioritization Rationale`

## Follow-up Patterns

| Trigger | Probe |
|---|---|
| Opportunity context missing | "What pursued opportunity is this ranking serving, or what is the explicit exception?" |
| Metrics are weak | "What outcome metric tells us one option matters more than another?" |
| Everything is high priority | "If you could only ship one, which one survives?" |
| Deferred list is vague | "What would have to change for this to come back?" |
| Revenue impact used as primary score in a new market | "Is market penetration the bottleneck? Check: low marginal cost + measurable activation + sufficient runway. If yes, user adoption may be a better impact proxy than revenue." |
| Two options score similarly | "In 6 months, which decision would you regret more — shipping A and not B, or shipping B and not A? Use regret minimization to break ties when scores cannot." |

## Anti-patterns

- Scoring before opportunity context exists
- Letting the framework choose the decision instead of informing it
- Treating a missing exception as permission to skip opportunity context
- Deferring work without a revisit trigger
- Scoring only for the primary persona without considering differential impact: WHY — RICE/ICE Reach and Impact scores measured against a single primary persona systematically undercount the benefit of accessibility and inclusion work, because that work often has high per-user impact for a smaller affected group; over time this makes inclusion invisible in the backlog. WHAT/HOW — before finalizing scores, run an edge-case impact check: ask whether any candidate disproportionately serves users with disabilities, low digital literacy, non-primary device access, or non-default language settings; if so, apply a separate inclusion modifier or weighted-reach adjustment rather than mutating the Impact score directly — Reach and Impact are independent dimensions in RICE/ICE, and conflating them breaks the framework's tradeoff visibility.

## Gotchas

- Do not score until an opportunity map exists. Scoring without opportunity context produces a ranked list of features, not a ranked list of user-outcome investments. The framework will appear to function but the output will be wrong.
- Effort estimates from requesters are systematically low. Effort must be estimated by the team that will implement — scoring with requester estimates produces inflated RICE scores and false confidence in fast delivery.
- Framework scores do not replace judgment. When two options score similarly, the framework cannot choose — present the scores as structured conversation material and ask the team to decide on the tiebreaker explicitly.
- Scoring only for the primary persona undercounts inclusion work. Apply an inclusion modifier before finalizing scores when any candidate disproportionately serves users with disabilities, low digital literacy, or non-default language settings.
- Revisit triggers must be recorded for every deferred option. A deferred item with no trigger will silently age in the backlog until it is either dropped without deliberation or resurrected without context.

## References

- `references/rice-ice-moscow-frameworks.md`
- `references/kano-model-patterns.md`
- `references/value-effort-matrix.md`

## Chain Position

- **Prerequisites**: An opportunity map with at least one `pursue` decision from `product-opportunity-mapping`. Metric context from `product-metrics-analysis`. Agreed scoring criteria.
- **Produces**: A ranked list of candidate slices with scores, rationale, and revisit triggers for deferred items. Written to `## Prioritization Rationale` in `spec/product-context.md`.
- **Gate question**: Are the scoring criteria agreed by the team, and is effort estimated by implementers (not requesters)?
