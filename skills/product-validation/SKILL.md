---
name: product-validation
description: Use for evidence-quality diagnosis, validation-method selection, and advisory next-step labels before product work moves forward. Use when evidence is thin, a feature has momentum without proof, or the cheapest next evidence move must be identified.
triggers:
  - "validate product idea"
  - "evidence quality"
  - "validation method"
  - "cheapest next evidence"
  - "product experiment"
  - "build trap"
---

> **Standalone Mode:** This skill is part of the prepkit-product plugin.
> - `spec/product-context.md` is optional — provide context inline or create one from the template.
> - Output paths (`research/`, `reports/`) are relative to your current working directory.
> - Facilitation routing is advisory — invoke any skill directly.


# Product Validation

## When To Use
- The team is ready to specify or prioritize work but evidence is still thin
- `spec/product-context.md` shows `settled: false` on problem, evidence, or validation sections
- A feature request has momentum but weak proof
- The question is "what is the cheapest next evidence move?" rather than "what should we build?"

## Key Concepts
- **Problem validation**: is the user problem real, costly, and recurring?
- **Solution validation**: does a proposed response actually reduce the problem?
- **Build trap**: shipping output instead of changing behavior
- **Validation depth**: match the method to the confidence gap, not stakeholder urgency
- **Cost-of-evidence ladder**: validation methods ranked by cost and time — observation (cheapest) < data pull < survey < interview < prototype test < MVP (most expensive). Always recommend the cheapest method that can close the specific evidence gap. Do not default to interviews when a data pull would answer the question.
- **Usability testing**: WHY — distinct from problem interviews; problem interviews validate whether the problem is real, usability testing validates whether the solution is operable. A prototype that solves the right problem can still fail because users cannot figure out how to use it — this gap is invisible to interview methods. WHAT — task-based testing: give participants a concrete task, observe completion, error, and recovery without assistance. HOW — use moderated think-aloud for diagnostic sessions where you need to understand why users struggle; use unmoderated testing when you need scale or speed. Start with 5–8 participants for a homogeneous qualitative round; if testing across distinct user groups (e.g., accessibility cohorts, different language groups), recruit 4–5 per group to surface group-specific usability failures.

## Rules
- Validation diagnoses gaps; `product-facilitation` decides the route
- Emit advisory next-step labels only: `research`, `experiment`, `PRD`, `defer`, or `reject`
- When more than one advisory route is defensible, present the top 2 options and state why the recommended one is the lowest-cost path to a decision — validation should resolve uncertainty at minimum cost, not explore every possible method.
- Reuse or refine an existing `## Research Plan` before proposing a new research package
- Recommending `experiment` does not create a new experiment-design surface in this slice
- "Users asked for it" is a signal, not validation
- Apply all output quality gates from `references/product-quality-gates.md`.
- Always recommend the cheapest evidence-gathering move first. Walk the cost-of-evidence ladder from the bottom: can observation answer it? Can a data pull? Only escalate to more expensive methods when cheaper ones cannot close the gap.
- When evidence quality is already `validated` or `quantified` and the decision gap is closed, say so explicitly: "Validation is not needed for this decision." Do not recommend additional validation when evidence is sufficient — over-validation delays decisions without improving confidence.

## Required Understanding

- [ ] What is the evidence quality? -> Grade as: `anecdotal` (single report) / `pattern` (3+ consistent signals) / `quantified` (metric-backed) / `validated` (tested with users). If anecdotal, name what's missing before proceeding.
- [ ] Is the problem backed by evidence from real users? -> `## Evidence Inventory`
- [ ] Can we describe the user experience in their language? -> `## Users` + `## JTBD`
- [ ] What decision is currently blocked? -> `## Validation` or `## Research Plan`
- [ ] What is the cheapest next evidence move? -> advisory route label
- [ ] Are we measuring outcome or output? -> `## Success Metrics` + `## Validation`
- [ ] Does an active research plan already exist? -> `## Research Plan`

## Follow-up Patterns

| Trigger | Probe |
|---|---|
| Solution stated before problem | "What problem does this solve, and for whom?" |
| No evidence cited | "What would change your mind about building this?" |
| Research already planned | "What gap is still open after that research plan?" |
| Team jumps from weak evidence to PRD | "Why is the next move PRD instead of more evidence?" |
| Evidence is already strong | "The evidence quality is `validated` — validation is not needed for this decision. Proceed to the next step." |

## Anti-patterns

- Confusing validation advice with routing authority
- Proposing new research when `## Research Plan` already covers the gap
- Treating a PR/FAQ as proof instead of a thinking tool
- Recommending experiment work without saying what evidence gap it addresses
- Using problem interviews to test usability: WHY — problem interviews surface whether a pain exists and how significant it is; they do not reveal whether a specific solution UI can be operated by real users. Teams that skip usability testing and rely on positive interview sentiment miss the operability layer entirely, which shows up as post-launch support load and abandonment. WHAT/HOW — if the validation question is "can users complete this task?", route to usability testing (task-based, think-aloud), not to a problem discovery interview.

## Gotchas

- This skill diagnoses validation gaps and emits advisory labels — it does not own routing. `product-facilitation` decides the next move. Do not treat an advisory label from this skill as a route commitment.
- "Users asked for it" is signal, not validation. User requests confirm interest, not whether the problem is real, recurring, or worth solving. Treat requests as discovery inputs that require validation, not as evidence of validated demand.
- Problem interviews cannot substitute for usability testing. If the validation question is whether users can operate the solution, route to task-based usability testing — not another problem interview round.
- Do not propose a new research package when an existing `## Research Plan` already covers the evidence gap. Re-proposing generates duplicate plans and slows delivery without improving evidence quality.
- Recommending an experiment route does not create experiment design in this skill. The advisory label `experiment` means the team should design an experiment — this skill does not scope or specify it.

## References

- `references/validation-decision-tree.md`
- `references/build-trap-assessment.md`
- `references/working-backwards-prfaq-template.md`

## Chain Position

- **Prerequisites**: A problem or opportunity with some existing evidence. An `## Evidence Inventory` section in `spec/product-context.md`.
- **Produces**: Evidence-quality diagnosis, advisory next-step label (`research`, `experiment`, `PRD`, `defer`, or `reject`), and the cheapest next evidence move recommendation.
- **Gate question**: Do we know what decision is currently blocked, and is the cheapest evidence move identified?
