# Behavioral Design Patterns

Practical mechanics for habit-forming product features. Use only when they reinforce user value.

## Pattern Decision Table

| Pattern | Mechanism | Use When | Avoid When | Example |
|---|---|---|---|---|
| Streaks | consistency + loss aversion | daily or near-daily usage | episodic or low-frequency workflows | learning habit |
| Endowed Progress | visible partial completion | onboarding and setup | progress feels fake | profile completion |
| Goal Gradient | extra motivation near completion | milestones and course completion | goal is unrealistically far | loyalty program |
| Social Proof | evidence others succeeded | adoption and trust | numbers are weak or unverifiable | review counts |
| Variable Rewards | uneven payoff timing | retention and discovery | predictability is the value | discovery feeds |
| Loss Aversion | protect existing progress | streak rescue, saved progress | tone becomes punishing | streak protection |
| Zeigarnik Effect | tension from incomplete work | setup checklists, task lists | tasks are trivial | setup progress |
| Default Effect | reduce decision friction | safe defaults and configuration | user choice is the core value | recommended settings |

## Streak Forgiveness Design

| User Tenure | Forgiveness Allowance |
|---|---|
| Days 1-7 | no forgiveness while habit forms |
| Days 8-30 | 1 free skip per month |
| Days 31+ | 2 free skips per month |
| Any point | freeze option to pause without penalty |

## Ethical Guardrail

For each pattern, ask: does this primarily serve the user's goal or only our metric?

| Answer | Action |
|---|---|
| user goal first | ship |
| both user and product | ship with monitoring |
| product metric only | redesign or remove |
| harms user goal | do not ship |

> **Regulatory extension:** The "user goal first → ship" test covers intent. A companion test covers form: *does the user know what they are doing and why?* Patterns that pass the intent test can still create regulatory exposure if the interface obscures what the user agreed to. Consent flows, auto-renewal mechanics, and notification opt-ins that use behavioral patterns should also be reviewed against the self-audit checklist in `deceptive-design-taxonomy.md` before launch.

## Combination Rules

- keep at most 3 active behavioral mechanics in one feature
- do not combine streaks, loss aversion, and heavy social comparison by default
- social proof requires real numbers
- defaults require clear visibility and easy reversal
