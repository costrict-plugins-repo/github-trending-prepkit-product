---
name: product-prd-authoring
description: Use for evidence-linked requirements, explicit non-goals, Given/When/Then acceptance scenarios, and engineering-ready PRDs. Use when writing a PRD, product requirements document, or feature specification.
triggers:
  - "write PRD"
  - "product requirements"
  - "product spec"
  - "feature specification"
  - "requirements document"
  - "acceptance criteria"
---

> **Standalone Mode:** This skill is part of the prepkit-product plugin.
> - `spec/product-context.md` is optional — provide context inline or create one from the template.
> - Output paths (`research/`, `reports/`) are relative to your current working directory.
> - Facilitation routing is advisory — invoke any skill directly.


# Product PRD Authoring

## When To Use
- Discovery is settled and the team is ready to define an execution-ready slice
- Engineering needs a handoff doc with traceable requirements
- Scope or non-goals are unclear
- Acceptance scenarios are too vague to test
- The design includes retention loops, nudges, rewards, streaks, or other engagement mechanics

## Key Concepts
- **Traceability**: every requirement ties back to evidence or an explicit hypothesis
- **Independent vs. foundational value**: some requirements deliver direct user value; others only enable it
- **Given/When/Then**: behavior-focused acceptance scenarios
- **Non-goals**: explicit exclusions that hold scope steady

## Rules
- Do not start a PRD until discovery and validation are settled
- Read `## Opportunity Map` before writing scope, dependencies, or non-goals
- Every major requirement must be tagged as evidence-backed or hypothesis-backed
- Requirements that are only foundational must be labeled explicitly
- Before locking scope, present at least 2 delivery options and recommend the smallest slice that can move the success metric, with everything else recorded as a non-goal — scope locks without option comparison are how teams ship more than the problem requires.
- Scope must include explicit non-goals
- ALL acceptance criteria MUST use Given/When/Then format when behavior is specified. No exceptions. Vague acceptance criteria like "the page loads fast" are not testable — rewrite as "Given [context], When [action], Then [observable outcome]."
- If the slice includes habit loops, gamification, or behavioral nudges, activate `product-engagement-design` and record safeguards plus counter-metrics in the PRD
- If the slice involves freemium, activation, onboarding-to-value, wow moment design, or in-context upsell mechanics, activate `product-engagement-design` to load PLG flow design patterns before specifying requirements
- Accessibility requirements must be made explicit: either included in scope with acceptance criteria, or recorded as a deliberate non-goal with a revisit trigger — silence is not a valid disposition
- Frame every requirement around the user outcome it must produce, not the feature it describes — a PRD that specifies features without naming the behavior change it expects cannot be validated after launch
- Apply Show, Don't Tell across all user-facing requirements: for each feature, ask "can the user experience this value directly, or are we asking them to imagine it from a description?" If the answer is "imagine," redesign the interaction to demonstrate. See `first-principles-thinking.md` in `product-discovery-synthesis/references/`.
- Apply all output quality gates from `references/product-quality-gates.md`.
- Every PRD must include at least 3 explicit non-goals. Non-goals with fewer than 3 items indicate insufficient scope discipline — force the team to name what they are deliberately not building, not just what they are building.
- Every PRD must include a kill criterion: the specific condition under which the initiative should be stopped, rolled back, or deprioritized. Format: "Kill if [metric/signal] reaches [threshold] within [timeframe]." A PRD without a kill criterion has no exit strategy.
- Every major requirement must be traced back to a JTBD statement. Requirements not linked to a job are features without a problem — they should be challenged or moved to non-goals. Use the format: "Supports JTBD: When [situation], I want to [motivation], so I can [outcome]."

## Required Understanding

- [ ] What is the evidence quality? -> Grade as: `anecdotal` (single report) / `pattern` (3+ consistent signals) / `quantified` (metric-backed) / `validated` (tested with users). If anecdotal, name what's missing before proceeding.
- [ ] Is the pursued opportunity clear, or is a documented exception recorded? -> `## Opportunity Map` or artifact note
- [ ] What is in scope and explicitly not in scope? -> `## Scope`
- [ ] What measurable outcome defines success? -> `## Success Metrics`
- [ ] What must exist before this can ship? -> `## Dependencies`
- [ ] Which requirements are evidence-backed versus hypothesis-backed? -> PRD traceability table or notes
- [ ] Who might this design exclude? -> WHY: without a conscious decision point, accessibility and inclusion work defaults to out-of-scope; the cost to retrofit is higher than the cost to specify upfront. WHAT/HOW: ask this question before scope is locked; for each user-facing requirement, note whether it was evaluated for exclusion risk; if accessibility requirements are consciously deferred, record that as an explicit non-goal with a revisit trigger — not as silence.

## Follow-up Patterns

| Trigger | Probe |
|---|---|
| Vague scope | "What is explicitly out of scope for this release?" |
| No opportunity anchor | "Which pursued opportunity is this slice serving?" |
| Requirement has no source | "What evidence or hypothesis justifies this requirement?" |
| Acceptance criteria are broad | "How would QA verify this in Given/When/Then form?" |

## Anti-patterns

- Starting specification before the opportunity or evidence is clear
- Turning hypotheses into facts by dropping the label in the PRD
- Leaving foundational-only work unlabeled and implying direct user value
- Writing non-goals so vaguely they cannot block scope creep

## Gotchas

- Do not start a PRD when discovery is still unsettled. A PRD written on top of weak evidence locks implementation scope to an unvalidated problem — the most expensive mistake in product work.
- Foundational requirements must be labeled explicitly. An unlabeled foundational requirement implies direct user value it does not deliver, distorting success metrics and post-launch assessment.
- Non-goals written without specificity do not hold scope. "We are not building X" is only effective when X is named with enough detail that both engineering and stakeholders can recognize scope creep when it appears.
- Accessibility disposition must be explicit. Silence is not a valid choice — either include accessibility acceptance criteria or record it as a deliberate non-goal with a revisit trigger.
- Engagement mechanics require `product-engagement-design` activation and counter-metrics before the PRD is locked. A PRD that specifies streaks, nudges, or progression without safeguards will ship manipulative mechanics by default.

## References

- `references/prd-structure-checklist.md`
- `references/user-story-patterns.md`
- `references/acceptance-criteria-patterns.md`
- `references/given-when-then-acceptance-scenarios.md`
- `../product-engagement-design/SKILL.md`

## Chain Position

- **Prerequisites**: Settled discovery (from `product-discovery-synthesis`), a pursued opportunity (from `product-opportunity-mapping`), and metric context (from `product-metrics-analysis`). Evidence quality must be `pattern` or stronger.
- **Produces**: An execution-ready PRD with traceable requirements, Given/When/Then acceptance criteria, explicit non-goals, and success metrics. Handed off to engineering.
- **Gate question**: Is every requirement traced to evidence or an explicit hypothesis, and are non-goals specific enough to block scope creep?
