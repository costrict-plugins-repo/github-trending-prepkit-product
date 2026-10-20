---
name: product-user-interview-design
description: Use for designing qualitative research packages: interview type, participant targeting, screener, guide, synthesis plan, and completion criteria. Use when a decision is blocked by weak user evidence or the team needs to design a research study.
triggers:
  - "design user interviews"
  - "research plan"
  - "interview guide"
  - "participant screener"
  - "qualitative research design"
  - "user research study"
---

> **Standalone Mode:** This skill is part of the prepkit-product plugin.
> - `spec/product-context.md` is optional — provide context inline or create one from the template.
> - Output paths (`research/`, `reports/`) are relative to your current working directory.
> - Facilitation routing is advisory — invoke any skill directly.


# Product User Interview Design

## When To Use
- Discovery or validation says the next move is `research`
- A decision is blocked by weak user evidence
- The team knows it needs interviews but has not designed the study
- `## Research Plan` is empty, stale, or incomplete

## Key Concepts
- **Decision-driven research**: interviews exist to change a decision, not just collect quotes
- **Exploratory vs. confirmatory**: match the interview type to the confidence gap
- **Participant fit**: recruit for the problem context, not convenience — participant fit includes both problem-context fit and demographic/ability diversity; a homogeneous pool that matches the primary persona will miss exclusion patterns that only emerge when users with different abilities, ages, language backgrounds, or access constraints are included
- **Completion criteria**: define "enough learning" before interviews begin
- **Cross-market sampling**: When the product serves multiple markets, research design must account for market diversity. Include at least 2 markets in the participant mix unless the research question is market-specific. If the pack manifest declares a `teamContext` file, use its market list for sampling guidance.

## Rules
- Start with the decision to validate, not the interview script
- Choose the interview type based on the evidence gap
- Present 2-3 research design options and recommend the smallest study that can unblock the decision with credible signal — over-designed research packages delay decisions without proportionally improving evidence quality.
- Keep outputs in active-plan `research/` by default
- No default stakeholder-summary artifact belongs in `reports/`
- Reuse or refine an existing `## Research Plan` before starting over
- Design interview questions around user outcomes and behavior, not feature wishlists — asking "what would you want us to build?" produces feature requests; asking "what are you trying to accomplish and where does it break down?" produces actionable outcome gaps
- Apply all output quality gates from `references/product-quality-gates.md`.
- Cap interview studies at 8–12 participants for a homogeneous qualitative round. If testing across distinct user groups, recruit 4–5 per group. More interviews do not proportionally improve signal quality — diminishing returns set in after 8 for a single segment.

## Required Understanding

- [ ] What is the evidence quality? -> Grade as: `anecdotal` (single report) / `pattern` (3+ consistent signals) / `quantified` (metric-backed) / `validated` (tested with users). If anecdotal, name what's missing before proceeding.
- [ ] What decision will this research inform? -> Name the specific product decision that is currently blocked. If no decision is named, the research has no anchor and should not proceed.
- [ ] What decision is blocked right now? -> `## Research Plan`
- [ ] What evidence gap makes interviews the right move? -> `## Evidence Inventory` + `## Validation`
- [ ] Which users should be recruited? -> `## Users`
- [ ] Which interview type fits the goal? -> `## Research Plan`
- [ ] What will count as enough learning to stop? -> `## Research Plan`

## Follow-up Patterns

| Trigger | Probe |
|---|---|
| "We should interview users" | "What decision would change after the interviews?" |
| Wrong recruit target | "Who actually experiences this problem in the needed context?" |
| Guide is solution-led | "What would you ask if you could not mention your product?" |
| No stop condition | "How will you know you have enough signal to move on?" |

## Anti-patterns

- Running interviews with no decision attached
- Recruiting internal users, friends, or generic "customers"
- Creating a polished report before doing the evidence-gathering work
- Asking future-feature questions instead of past-behavior questions
- Recruiting a homogeneous participant pool that matches the primary persona but excludes users with disabilities, older adults, non-English speakers, or users in different socioeconomic contexts — even when the product claims to serve general audiences; these participants reveal systemic design weaknesses the primary-persona cohort will not surface

## Gotchas

- Do not activate this skill to validate an already-decided solution — interview design for confirmation bias produces data that supports the conclusion the team already reached. If the decision is made, route to usability testing instead.
- A research package without a blocking decision attached will not be acted on. Interviews requested without a named decision are discovery theater; always anchor to the decision that changes after the interviews.
- Completion criteria must be defined before recruitment begins. A study with no stop condition runs until budget or patience runs out — not until enough signal exists.
- Recruiting for convenience (internal users, colleagues, existing customers) introduces systematic bias. If the study requires participants in the problem context, recruits outside that context invalidate the evidence.
- Interview guides written around future features elicit wishlist responses, not behavioral evidence. Redesign any question containing "would you" or "do you think you would" into a past-behavior or observation-based question.

## References

- `references/interview-type-selection.md`
- `references/research-brief-template.md`
- `references/screener-and-guide-patterns.md`
- `references/synthesis-plan-and-completion-criteria.md`


## Chain Position

- **Prerequisites**: A routing decision of `research` from `product-facilitation` or `product-validation`. A named decision that the research must inform.
- **Produces**: A research package (interview type, participant screener, interview guide, synthesis plan, completion criteria) saved to active-plan `research/`.
- **Gate question**: What specific decision will change after these interviews are completed?
