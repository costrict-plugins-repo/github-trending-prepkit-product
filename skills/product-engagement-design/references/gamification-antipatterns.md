# Gamification Anti-patterns

What not to do when designing gamified product features.

> **Scope note:** This document covers failure modes within gamification systems — rewards, streaks, leaderboards, and progression mechanics. Interaction-level dark patterns (hidden exits, roach-motel signup, disabled back navigation, deceptive consent flows) are distinct from gamification failures and are covered in `deceptive-design-taxonomy.md`. Both are in scope for any product that uses behavioral mechanics.

## Anti-pattern Reference Table

| Anti-pattern | Symptom | Root Cause | Fix |
|---|---|---|---|
| Over-gamification | every action gets points or badges | design enthusiasm outruns user value | keep 1-3 mechanics only |
| Hollow Achievements | trivial events get celebrated | no meaningful milestone | raise the bar |
| Motivation Crowding | intrinsic motivation falls after rewards | rewards replace autonomy | test and remove if value drops |
| Leaderboard Toxicity | most users disengage | public absolute ranking | use resets, relative views, or teams |
| Gamification Fatigue | users ignore mechanics after novelty fades | no true behavior change | refresh or remove weak mechanics |
| Streak Anxiety | guilt and stress show up | no forgiveness | add skips and freeze options |
| Trophy Hunting | users game the system | rewards detached from value | tie rewards to core outcome |
| Social Proof Fraud | users distrust claims | fake or inflated numbers | show only verified numbers |

## Ethical Checklist

- [ ] Does this serve the user's stated goal, not only our engagement metric?
- [ ] Can the user opt out of notifications or nudges?
- [ ] Are mechanics and reward conditions transparent?
- [ ] Would this still feel acceptable if fully explained?
- [ ] Does it support autonomy, competence, or relatedness?

## When To Remove A Mechanic

| Signal | Threshold | Action |
|---|---|---|
| no measurable lift | no change vs. control | remove |
| manipulative sentiment | >20% negative user response | remove immediately |
| unlock rate too low | <5% after meaningful exposure | simplify or remove |
| support complaints rise | sustained increase | investigate and likely remove |

## Leaderboard Design Rules

- require resets
- prefer opt-in participation
- show relative context, not only absolute rank
- offer team formats when individual ranking is demotivating
