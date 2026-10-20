---
name: product-facilitation
description: Use when any product skill or workflow needs structured intake, shared product-context state, or a single authority for next-step routing. Use on any product work that spans discovery, research, specification, or prioritization to ensure shared context and consistent routing.
triggers:
  - "help me prioritize features"
  - "I have a new feature idea"
  - "what should we build next"
  - "feature discovery"
  - "product strategy"
  - "help me write a PRD"
  - "product decision"
  - "which product skill should I use"
---

> **Standalone Mode:** This skill is part of the prepkit-product plugin.
> - `spec/product-context.md` is optional — provide context inline or create one from the template.
> - Output paths (`research/`, `reports/`) are relative to your current working directory.
> - Facilitation routing is advisory — invoke any skill directly.
> - `docs/product-foundation.md` is optional — the skill works without it.
> - Routing decisions are advisory in standalone mode, not authoritative.


# Product Facilitation

Use this as a process skill. Activate alongside any product domain skill or workflow.

Goal:
- drive structured questioning so product work is grounded in evidence, not intuition
- manage shared product context across discovery, research design, specification, and prioritization
- act as the sole routing authority for next-step decisions

## Routing Authority

`product-facilitation` decides the next move: `research`, `PRD`, `experiment`, `defer`, or `reject`.

Authority split:
- `product-facilitation`
  - chooses the route
  - owns backward routing when upstream thinking is missing
  - records route rationale when an artifact or shared-state update needs it
- domain skills
  - diagnose evidence quality, readiness, or tradeoff quality
  - may emit advisory next-step labels
  - do not independently choose the route
- workflows
  - define checkpoints, inputs, and artifact sequencing
  - invoke facilitation at decision points
  - do not embed competing route logic

If diagnosis and workflow expectations conflict, choose the safer backward route.

### Routing Decision Tree

1. Is the problem statement clear and evidence-backed?
   - No → route to `research` (discovery or validation)
   - Yes → continue
2. Has the opportunity been mapped and a pursue decision made?
   - No → route to `product-opportunity-mapping`
   - Yes → continue
3. Is the evidence quality `pattern` or stronger?
   - No → route to `product-validation` for cheapest next evidence move
   - Yes → continue
4. Are success metrics defined with baselines?
   - No → route to `product-metrics-analysis`
   - Yes → continue
5. Is the team ready to specify scope?
   - Yes → route to `PRD`
   - No, needs experiment → route to `experiment`
   - No, not worth pursuing → route to `reject` with rationale
   - No, not now → route to `defer` with revisit trigger

If the team wants users as co-creators rather than informants (co-design / participatory design), do not route through `research` — research frames users as subjects, not collaborators, and will produce the wrong session design. Co-design methods are outside this pack's current scope; flag the need and defer until dedicated co-design guidance is available.

## Escalation Ladder

When a user cannot answer a Required Understanding question:

**L1 — Guide**: Reframe the question with examples, analogies, or 2-3 concrete options to react to.

**L2 — First Principles**: If stuck or looping on an unexamined assumption, invoke first-principles decomposition before research. Identify the assumption, strip it to its axiomatic basis, and rebuild from there. Reference `first-principles-thinking.md` in `product-discovery-synthesis/references/`. Adopt startup mindset: there are always multiple paths — explore within existing evidence and safety constraints before committing. Do not escalate to research until the foundational framing is clear.

**L3 — Research (local only)**: Read the active skill's reference files, active-plan `research/`, active-plan `reports/`, and `docs/reference/knowledge/`. Synthesize an informed default grounded in those materials. Do not use external tools, APIs, or web searches.

**L4 — Confirm**: Present the researched default with explicit rationale. Ask the user to confirm, adjust, or reject. Write the answer as `source: model+user | settled: true`.

Every gate question and routing recommendation must be resolvable through this ladder.

## Recommended Next Contract

Every major product workflow ends with one explicit next move:
- `research`
- `PRD`
- `experiment`
- `defer`
- `reject`

Rules:
- `research` usually means `product-user-research-design` or discovery follow-through
- `experiment` is a recommendation outcome only in this slice; there is no dedicated experiment-design workflow
- When multiple routes are plausible, present 2-3 options and recommend the smallest next step with the highest expected evidence gain per delivery time — this prevents over-committing to a single path before evidence justifies it.
- the chosen next move must match the current evidence and confidence level
- `reject` requires explicit rationale: what evidence was evaluated, why the opportunity is not worth pursuing, and what would change the decision. A reject without rationale is not a valid route.
- Route decisions toward the option most likely to change user behavior, not the one that produces the most deliverables — routing by output volume leads teams to ship artifacts instead of solving problems

## Product Context Contract

`spec/product-context.md` is the shared state document for one initiative. It is initiative-bound spec state, same surface as `spec/proposal.md` and `spec/design.md`.

Rules:
1. **Read before asking** — check `spec/product-context.md` before asking any Required Understanding question
2. **Skip if settled** — do not re-ask questions where `settled: true`
3. **Write with provenance** — every answer must include `source`, `settled`, and `updated` metadata
4. **Accumulate** — downstream phases add sections, never clear upstream sections
5. **Name consumers** — only add shared-state sections that downstream skills or workflows actually read

Named consumers:
- `## Opportunity Map`
  - read by `product-prd-authoring`, `product-prioritization`, and `product-strategy-reviewer`
- `## Research Plan`
  - read by `product-user-research-design`, `product-discovery`, `product-validation`, and `product-strategy-reviewer`

## Provenance Fields

Two provenance fields plus a timestamp per section:

| Field | Values | Meaning |
|---|---|---|
| `source` | `user` / `model` / `model+user` | Who provided the answer |
| `settled` | `true` / `false` | Can downstream skills skip this question? |
| `updated` | date | When this section was last written |

Scaffolded sections use `source: —` until first populated.

Rules:
- `source: user` -> `settled: true`
- `source: model` -> `settled: false`
- `source: model+user` -> `settled: true`
- incomplete content -> `settled: false` regardless of source

## Template

Scaffold `spec/product-context.md` from `references/product-context-template.md`.

## Artifact Ownership

- `product-discovery` owns working discovery artifacts in active-plan `research/`:
  - `research/discovery-brief.md`
  - `research/evidence-summary.md`
  - `research/validation-brief.md`
- `product-user-research-design` owns research-design package files in active-plan `research/`
- interview-design does not create a default stakeholder-summary artifact in `reports/`
- `product-opportunity-mapping` owns:
  - `research/opportunity-map.md`
  - `reports/opportunity-decision.md`
- `product-discovery` may invoke or reuse those workflows, but must not overwrite their owned artifact paths

## Product Foundation Gate

Before starting any product workflow, check for `docs/product-foundation.md`.

- **If found**: read it. Use settled sections as known context — do not re-ask what is already captured. Seed `spec/product-context.md` `## Users` from the foundation personas.
- **If missing**: scaffold from `references/product-foundation-template.md` and collect the foundation with the user before proceeding. Walk through sections in order: Product Overview, Target Customers, Market Context, Competitive Landscape, then Strategic Priorities. Business Model may be deferred if the product is pre-revenue. Apply the escalation ladder (L1-L4) for each section. Save to `docs/product-foundation.md`.
- **If partially filled**: collect only unsettled sections. Do not re-ask settled sections.

The foundation lives at `docs/product-foundation.md` — repo-level, not inside any plan directory. It is product-wide and persistent: it survives plan archives and is shared across all initiatives. Downstream initiative work in `spec/product-context.md` inherits from it but does not overwrite it.

If the pack manifest declares a `teamContext` file, load it for market-aware routing context. Use the market and metric context when routing decisions that affect user experience across multiple markets.

## Working Rules

- Before routing, assess the evidence quality backing the current request: `anecdotal` (single report) / `pattern` (3+ consistent signals) / `quantified` (metric-backed) / `validated` (tested with users). If anecdotal, flag what's missing before committing to a route.
- Read `docs/product-foundation.md` (if it exists) and `spec/product-context.md` before asking any Required Understanding question. Skip questions where `settled: true`.
- Every route decision must be recorded with rationale when it triggers an artifact or shared-state update.
- When diagnosis and workflow expectations conflict, choose the safer backward route — return to the upstream step rather than proceeding with incomplete evidence.
- Domain skills diagnose; this skill routes. Do not let domain skills independently commit to a route.
- Every major workflow ends with one explicit next-move label: `research`, `PRD`, `experiment`, `defer`, or `reject`. Ambiguous endings are not valid.
- When multiple routes are plausible, present 2-3 options and recommend the one with the highest expected evidence gain per delivery time.
- All output quality gates in `references/product-quality-gates.md` apply to facilitation outputs and to every domain skill output routed through this skill.

## Gotchas

- Do not use this skill as a discovery skill. Product facilitation routes and orchestrates; it does not conduct interviews, synthesize evidence, or draft requirements. Activate the appropriate domain skill for that work.
- Routing authority means this skill decides the next move — domain skills emit advisory labels only. If a domain skill's advisory label conflicts with the facilitation route, the facilitation route wins.
- The escalation ladder must be followed in order. Do not jump to L3 research when a L1 guide or L2 first-principles reset could unblock the user without external research.
- Co-design and participatory design are outside this skill's routing scope. If the team wants users as co-creators rather than informants, flag the need and defer — routing through the research path will produce the wrong session design.
- "Urgent" is not a routing input. Before escalating priority, ask: "Is this actually urgent (time-bound external constraint), or is it just loud (strong stakeholder opinion without time pressure)?" Route based on evidence quality and decision readiness, not volume.
- The product context contract (`spec/product-context.md`) is accumulative — downstream phases add sections and never clear upstream ones. Do not reset settled sections when a later phase creates new ambiguity about an earlier answer.

## Section Ownership By Workflow

| Workflow | Sections Written |
|---|---|
| `product-discovery` | Users, Problem, Current Alternative, JTBD, Evidence Inventory, Validation |
| `product-user-research-design` | Research Plan |
| `product-opportunity-mapping` | Opportunity Map |
| `product-prd-authoring` | Scope, Success Metrics, Dependencies |
| `product-prioritization` | Prioritization Rationale |

## Chain Position

- **Prerequisites**: A product question, feature request, or initiative that needs routing. Optionally, `docs/product-foundation.md` and `spec/product-context.md` for existing context.
- **Produces**: A routing decision (`research`, `PRD`, `experiment`, `defer`, or `reject`) with rationale. Updated `spec/product-context.md` sections.
- **Gate question**: Is the evidence quality sufficient to commit to this route, or should we gather more evidence first?
