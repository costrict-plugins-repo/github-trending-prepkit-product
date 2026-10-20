---
name: product-discovery-synthesis
description: Use for problem framing, JTBD synthesis, evidence-quality checks, and opportunity shaping during product discovery. Use when a feature request needs reframing into a user problem or discovery evidence needs synthesis into an opportunity.
triggers:
  - "product discovery"
  - "JTBD synthesis"
  - "jobs to be done"
  - "frame user problem"
  - "discovery synthesis"
  - "opportunity shaping"
  - "empathy mapping"
---

> **Standalone Mode:** This skill is part of the prepkit-product plugin.
> - `spec/product-context.md` is optional — provide context inline or create one from the template.
> - Output paths (`research/`, `reports/`) are relative to your current working directory.
> - Facilitation routing is advisory — invoke any skill directly.


# Product Discovery Synthesis

## When To Use
- An incoming feature request needs reframing into a user problem
- The team is debating solutions before the job and pain are clear
- `spec/product-context.md` has weak or assumed discovery inputs
- Discovery evidence exists but has not been shaped into an opportunity worth mapping
- Discovery has interview evidence but opportunities feel fragmented across multiple touchpoints or phases

## Key Concepts
- **Jobs-to-be-Done (JTBD)**: users hire products to make progress in a context
- **Opportunity space**: unmet needs or frictions that exist before solution ranking
- **Switching forces**: push, pull, anxiety, and habit explain why users change
- **Outcome framing**: opportunities should connect to user progress and measurable change
- **Empathy mapping**: collaborative synthesis artifact that organises interview observations into four quadrants — Says (verbatim quotes), Thinks (internal beliefs not spoken aloud), Does (observable behaviours), and Feels (emotional states). Use it after interviews and before JTBD synthesis to ensure the Thinks and Feels dimensions — which affinity mapping alone does not prompt for — are explicitly captured. Juxtapositions across quadrants (e.g. positive Does but negative Feels) often reveal the most actionable unmet needs. See `references/empathy-mapping-synthesis.md`.
- **Customer journey mapping**: visualisation of the user experience across phases — capturing what users do, think, and feel at each stage — to surface friction points and opportunity areas across the full experience arc. ODI Job Map (eight functional steps) is the right tool for deep single-job analysis; journey mapping covers multi-touchpoint experiences, emotional peaks, and cross-channel friction that JTBD interviews alone may not surface. The opportunities layer of a journey map is a direct input to OST opportunity nodes. See `references/journey-mapping-basics.md`.
- **Design Thinking / HCD process framing**: teams with design-background practitioners often use the Empathize-Define-Ideate-Prototype-Test model (Design Thinking) or the ISO 9241-210 four-activity HCD cycle as their process reference. These are complementary framings alongside JTBD/ODI, not replacements. Empathize maps to JTBD interviewing; Define maps to empathy and journey mapping synthesis; Ideate maps to OST solution generation; Prototype/Test map to assumption-driven experimentation. JTBD and ODI remain the primary analytical frameworks in this skill; Design Thinking provides cross-disciplinary orientation for mixed teams.
- **First-principles decomposition**: when discovery is stuck, a framework produces conflicting signals, or the problem framing feels inherited rather than earned, decompose the core assumption to axiomatic truths before continuing. First-principles is a meta-tool that works alongside JTBD, HCD, RICE, and other frameworks — it clears the foundation so those frameworks produce better answers. See `references/first-principles-thinking.md`.

## Rules
- Do not move into solution space until the job, pain, and evidence are explicit
- All JTBD statements must use the canonical format: "When [situation], I want to [motivation], so I can [outcome]." Statements that name a feature instead of a motivation are solution-contaminated — reframe before recording.
- Segment users; "everyone" is never a valid segment
- Every problem claim needs evidence or an explicit hypothesis label
- If solution discussion is unavoidable, present 2-3 possible directions with one-line tradeoffs and mark the leanest option to validate next, without committing scope here — premature scope commitment during discovery locks teams into solutions before the problem is fully understood.
- Opportunities are unmet needs or recurring frictions, not feature bundles
- Opportunity ranking happens in `product-opportunity-mapping`, not here
- Frame every insight as a user outcome to change, not a feature to build — synthesis that concludes with "we should build X" instead of "users need outcome Y" has skipped the problem and jumped to a solution
- When looping on a problem framing, invoke first-principles before adding more research — the issue may be an unexamined assumption, not missing data
- Apply all output quality gates from `references/product-quality-gates.md`.
- Every discovery synthesis must surface at least 2 competing hypotheses for the user problem before converging on one. Single-hypothesis framing creates confirmation bias — force alternatives even when one hypothesis feels obvious.

## Required Understanding

- [ ] What is the evidence quality? -> Grade as: `anecdotal` (single report) / `pattern` (3+ consistent signals) / `quantified` (metric-backed) / `validated` (tested with users). If anecdotal, name what's missing before proceeding.
- [ ] Does this framing hold across markets? -> If the product operates in multiple markets, check whether the problem, JTBD, and opportunity framing are consistent across all served markets. Note market-specific variations.
- [ ] Who is the user? -> `## Users`
- [ ] What triggered attention on this problem? -> `## Problem`
- [ ] What progress is the user trying to make? -> `## JTBD`
- [ ] What do they do today instead? -> `## Current Alternative`
- [ ] Which pain or friction repeats often enough to matter? -> `## Problem` + `## Evidence Inventory`
- [ ] What evidence exists, and what remains hypothetical? -> `## Evidence Inventory` + `## Validation`
- [ ] Which unmet need is worth mapping as an opportunity? -> input to `## Opportunity Map`

## Follow-up Patterns

| Trigger | Probe |
|---|---|
| Feature request stated as need | "What problem does that solve, and for whom?" |
| "Everyone needs this" | "Who would be upset enough to stop if we never built it?" |
| No data cited | "How do we know this is real instead of assumed?" |
| One quote treated as a pattern | "What makes you think this repeats across the segment?" |
| Framework outputs conflict or team is stuck | "What assumption are we not questioning? Decompose to first principles before adding more research." |

## Anti-patterns

- Accepting feature requests as problem statements
- Skipping emotional or social context of the job
- Treating all users as one segment when the switching forces differ
- Writing opportunity language that is really a feature shortlist
- Moving directly from interview notes to JTBD statements without an explicit empathy-synthesis step — affinity mapping groups themes but does not prompt for the Thinks and Feels dimensions; skipping empathy mapping causes the emotional job context to be lost before it reaches the JTBD statement

## Gotchas

- Do not use this skill for roadmap planning or feature scoping — discovery synthesis is upstream of those activities. Stop when an evidenced opportunity is ready to hand off to `product-opportunity-mapping`.
- JTBD synthesis requires behavioral evidence, not survey preferences. A list of feature requests from a survey is not a jobs-to-be-done synthesis — it is unprocessed input.
- Opportunity framing is frequently contaminated by solution language. If the opportunity statement names a specific interface or technology, it is likely a feature dressed up as an opportunity — reframe to the user outcome that would change.
- First-principles decomposition is a debugging tool, not a replacement for evidence gathering. Use it when a framework produces conflicting signals or framing feels inherited, not as a substitute for interviews.
- Empathy mapping requires both problem-context and diverse participant inputs. Synthesis from a homogeneous participant pool will miss the Thinks and Feels dimensions of underrepresented user groups.

## References

- `references/jtbd-framework.md`
- `references/opportunity-solution-tree.md`
- `references/outcome-driven-innovation.md`
- `references/user-research-patterns.md`
- `references/empathy-mapping-synthesis.md`
- `references/journey-mapping-basics.md`
- `references/first-principles-thinking.md`


## Chain Position

- **Prerequisites**: A feature request, user problem, or discovery evidence that needs framing. Evidence from interviews, support tickets, or behavioral data.
- **Produces**: JTBD statements, opportunity framing, evidence inventory, and an evidenced opportunity ready for `product-opportunity-mapping`.
- **Gate question**: Is the user problem backed by evidence (not just assumed), and can we articulate the job in the user's language?
