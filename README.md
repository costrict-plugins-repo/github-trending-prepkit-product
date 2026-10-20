# prepkit-product

Product management skills plugin for Claude Code — discovery synthesis, user research design, opportunity mapping, PRD authoring, prioritization, metrics analysis, engagement design, and validation.

## Installation

```bash
claude --plugin-dir ./prepkit-product
```

Or install from GitHub:

```bash
# Inside Claude Code
/plugin marketplace add namht1st/prepkit-product
/plugin install prepkit-product
```

## Skills

| Skill | Description |
|-------|-------------|
| **product-discovery-synthesis** | Problem framing, JTBD synthesis, evidence-quality checks, and opportunity shaping during product discovery |
| **product-user-interview-design** | Designing qualitative research packages: interview type, participant targeting, screener, guide, synthesis plan |
| **product-opportunity-mapping** | Turning discovery evidence into pursue, monitor, or defer opportunity decisions with dependencies and revisit triggers |
| **product-prd-authoring** | Evidence-linked requirements, explicit non-goals, Given/When/Then acceptance scenarios, and engineering-ready PRDs |
| **product-prioritization** | Scoring candidate slices with RICE, MoSCoW, or ICE frameworks once opportunity and metric context are explicit |
| **product-metrics-analysis** | Outcome-based success metrics, baseline and target checks, leading indicators, and counter-metric validation |
| **product-engagement-design** | Habit loops, progression systems, gamification, behavioral nudges, freemium funnel design, and PLG conversion flows |
| **product-validation** | Evidence-quality diagnosis, validation-method selection, and advisory next-step labels before product work moves forward |
| **product-facilitation** | Structured intake, shared product-context state, and single authority for next-step routing across product workflows |

## Command

- `/prepkit-product:product-review-strategy` — Review product artifacts for evidence quality, routing fit, specification rigor, opportunity decisions, and prioritization discipline

## Agent

- **product-strategy-reviewer** — Specialized subagent for reviewing product artifacts across discovery, specification, and prioritization

## How It Works

Each skill follows a structured product methodology:

- **Evidence grading** — Every skill checks evidence quality before proceeding (A: validated, B: partial, C: assumed)
- **Quality gates** — Output is validated against product quality gates (see `references/product-quality-gates.md`)
- **Chain position** — Skills declare their position in the product workflow chain, so Claude routes between them correctly
- **Standalone operation** — Skills work independently without requiring PrepKit runtime

## License

MIT
