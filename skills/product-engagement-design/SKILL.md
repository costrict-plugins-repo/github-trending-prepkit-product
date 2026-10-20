---
name: product-engagement-design
description: Use for habit loops, progression systems, gamification mechanics, behavioral nudges, freemium funnel design, activation mechanics, and PLG conversion flows that must increase product value without becoming manipulative. Use when designing retention loops, streaks, badges, or onboarding flows.
triggers:
  - "engagement design"
  - "habit loop"
  - "gamification mechanics"
  - "retention loop"
  - "onboarding flow"
  - "PLG conversion"
  - "behavioral nudge"
---

# Product Engagement Design

## When To Use
- A product concept depends on repeated behavior, retention loops, or activation momentum
- The team is proposing streaks, badges, levels, rewards, social proof, nudges, or other gamified mechanics
- A PRD includes behavior-shaping mechanics that need ethical guardrails and counter-metrics
- The question is not "should we build this feature?" but "how should the behavior loop work without harming trust?"
- The problem involves a freemium model, PLG conversion funnel, activation mechanics, onboarding-to-value flow, or in-context upsell design — load `references/plg-flow-design.md`

## Key Concepts
- **Behavior loop**: trigger -> action -> reward -> investment
- **Intrinsic vs. extrinsic motivation**: amplify existing user value before adding rewards
- **Progression design**: levels, badges, streaks, and milestones only help when they reinforce real product progress
- **Counter-metrics**: track harm signals alongside engagement lift
- **Ethical guardrails**: avoid coercion, fake urgency, exploitative loss aversion, and hollow achievements
- **Show, Don't Tell**: design the user path so value is experienced before it is pitched — apply to activation flows, freemium onboarding, and in-context upsell placement. The free experience must be genuinely valuable, not a crippled version of the paid product. See `references/plg-flow-design.md`.
- **Deceptive design taxonomy**: formal categories of manipulative interface patterns — Trick Wording (misleading copy that hides what an action does), Sneaking (practices hidden until after a commitment is made), Obstruction (making desired user actions like cancelling or unsubscribing deliberately difficult); these extend beyond gamification mechanics to interaction-level manipulation present in any product interface — WHY: without named categories, "it feels manipulative" cannot be acted on; WHAT/HOW: audit each screen against these three categories and ask whether a user could accurately describe what they agreed to before they acted
- **Regulatory exposure**: deceptive patterns increasingly violate GDPR consent and transparency rules (Articles 6–7, Planet49 ruling), EU DSA Article 25 (explicit deceptive design prohibition for all online platforms), and FTC Act Section 5 enforcement — WHY: ethical failures in engagement design carry legal risk, not only reputational risk; products launched into regulated markets without a deceptive-design review carry compliance exposure; WHAT/HOW: before launch, run the self-audit checklist in `references/deceptive-design-taxonomy.md` against every consent flow, cancellation path, and social proof claim

## Rules
- Do not use gamification to compensate for weak core product value or weak discovery
- Do not gate core product access behind rewards, streaks, or cosmetic status systems
- Prefer 1-2 primary mechanics plus at most 1 supporting mechanic
- Before selecting a mechanic, present 2-3 viable designs with expected user-value lift and delivery cost, and recommend the leanest version worth shipping first — engagement mechanics are easy to over-build and hard to simplify after launch.
- If a design uses streaks, loss aversion, scarcity, or social proof, define explicit safeguards before shipping
- Every engagement mechanic needs a success metric AND a dedicated counter-metric. The counter-metric must measure potential harm (stress, churn acceleration, support volume, trust erosion), not just the absence of success. Define both before launch — adding counter-metrics retroactively is too late.
- If the design cannot be explained clearly to users without sounding manipulative, redesign it
- Define engagement success as a user-meaningful behavior change (task completed, goal reached, habit formed), not a product metric (DAU, session length, clicks) — metrics that rise without corresponding user value are a signal of manipulation, not engagement
- Apply all output quality gates from `references/product-quality-gates.md`.
- Every engagement mechanic must pass the "user stops" test: if a user stops engaging with the mechanic, does the product still deliver core value? If stopping feels punitive (lost streaks, decayed progress, social shame), the mechanic is coercive and must be redesigned.

## Required Understanding

- [ ] What is the evidence quality? -> Grade as: `anecdotal` (single report) / `pattern` (3+ consistent signals) / `quantified` (metric-backed) / `validated` (tested with users). If anecdotal, name what's missing before proceeding.
- [ ] Have ethical guardrails been defined as hard constraints? -> Every engagement mechanic must have explicit ethical guardrails defined BEFORE design proceeds. Guardrails are not suggestions — they are hard constraints that cannot be traded away for engagement lift.
- [ ] What user behavior are we trying to increase, and why does it create user value? -> opportunity or PRD goal
- [ ] What intrinsic motivation already exists before adding mechanics? -> discovery evidence + JTBD
- [ ] Is the product used daily, weekly, or episodically? -> usage cadence from evidence
- [ ] Which mechanic best fits the user goal: progress, habit, mastery, social proof, or reward? -> design choice
- [ ] What abuse, anxiety, or trust risk could this mechanic create? -> guardrail notes
- [ ] What counter-metrics or removal triggers will tell us the mechanic is harming users? -> PRD metrics or experiment notes

## Follow-up Patterns

| Trigger | Probe |
|---|---|
| "Let's add badges" | "What user behavior or outcome improves because of that badge?" |
| Streak proposed for low-frequency workflow | "Is this actually a habit product, or are we forcing daily behavior onto episodic use?" |
| Leaderboard idea appears | "Would the bottom 80% feel motivated, indifferent, or punished?" |
| Social proof proposed | "Are the numbers real, current, and meaningful enough to show?" |
| Reward loop feels strong but unclear | "Does this reinforce real progress, or just more clicks?" |
| Any engagement mechanic proposed | "What happens when the user stops? Does the product still deliver value, or does it punish absence? If stopping feels like a loss, the mechanic is coercive." |

## Anti-patterns

- Treating gamification as a substitute for product-market fit
- Shipping hollow achievements that celebrate trivial actions
- Using scarcity or streak loss to pressure users rather than help them
- Measuring only engagement lift and ignoring stress, churn, or trust damage
- Adding too many mechanics at once and making the feature feel like a game instead of a product
- Interaction-level dark patterns — disabled back navigation, hidden unsubscribe flows, roach-motel signup (easy in, no visible exit), low-contrast close buttons on modals — these are behavioral design failures even in products with no gamification; they appear in consent flows, trial-to-paid upsells, and notification preference screens
- Deceptive social proof — fabricated review counts, inflated user numbers, vague unverifiable claims ("millions trust us") — erodes trust when discovered and exposes the product to FTC and DSA enforcement

## Gotchas

- Do not activate this skill to compensate for weak product-market fit. Gamification applied to a product users do not want accelerates abandonment — users disengage faster once they realize the mechanics are hiding an empty core experience.
- Engagement mechanics designed for high-frequency products fail in episodic ones. Daily streaks on a product used once a month create anxiety and attrition, not habit. Match mechanic cadence to actual usage frequency before selecting any mechanic.
- Counter-metrics must be defined before launch, not added if things look bad. The team will rationalize a rising DAU or session length if no counter-metric exists to flag stress, churn acceleration, or support volume increases.
- "It doesn't sound manipulative to me" is not an acceptable safeguard. Run the deceptive design taxonomy audit against every consent flow, cancellation path, and social proof claim before ship — regulatory exposure from DSA and FTC enforcement is tied to the design output, not the intent.
- Adding multiple mechanics simultaneously makes it impossible to attribute behavior change to any single mechanic. Prefer one primary mechanic plus one supporting mechanic per release; isolate variables to generate usable signal.

## References

- `references/hook-model-canvas.md`
- `references/octalysis-core-drives.md`
- `references/behavioral-design-patterns.md`
- `references/gamification-antipatterns.md`
- `references/deceptive-design-taxonomy.md`
- `references/plg-flow-design.md`

## Chain Position

- **Prerequisites**: A PRD or product concept that includes behavior-shaping mechanics (streaks, badges, nudges, progression, PLG flows). Activated by `product-prd-authoring` when engagement mechanics are in scope.
- **Produces**: Engagement mechanic design with ethical guardrails, counter-metrics, and removal triggers. Integrated into the PRD's requirements and metrics sections.
- **Gate question**: Does every engagement mechanic have a counter-metric and an explicit ethical guardrail, and can the design be explained to users without sounding manipulative?
