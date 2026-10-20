# Deceptive Design Taxonomy

A working reference for identifying, classifying, and auditing deceptive interface patterns in product design. Complements `gamification-antipatterns.md` (gamification-specific failure modes) — this document covers interaction-level manipulation that applies to any product interface, not only gamified ones.

---

## Why This Matters

Deceptive design is not limited to dark-pattern-heavy consumer apps. It emerges in consent flows, trial-to-paid transitions, notification preference screens, and cancellation paths — places where product metrics and user intent diverge. Naming patterns precisely converts "this feels manipulative" into a design decision with a clear fix.

Regulatory exposure compounds the ethical argument: EU DSA Article 25, GDPR Article 25, and FTC Act Section 5 all directly address deceptive interface patterns, and enforcement actions against major platforms have established that "the UX team didn't intend it" is not a sufficient defense.

---

## Three Pattern Categories (Practitioner Synthesis)

Based on Harry Brignull's deceptive.design registry — the most widely cited classification in industry and academic literature, with 400+ documented cases and direct use in regulatory guidance. Brignull's original taxonomy uses ~12 named pattern types; the three categories below are a practitioner synthesis that groups related patterns for audit purposes.

### Trick Wording

**What it is:** Copy that misleads users about what an action does, uses double negatives, or obscures opt-in vs. opt-out logic.

**Why it works deceptively:** Users read headlines and button labels; they rarely read footnotes or full modal text. Trick wording exploits this by making the dominant reading path lead to an unintended action.

**How to identify it:**
- Does the button label match what happens after you click it?
- Does the checkbox state (checked = opted in, or checked = opted out?) require re-reading to interpret?
- Would a user who scanned the screen at normal reading speed understand what they agreed to?

**Examples:**
- "Uncheck this box to stop receiving promotional emails" (double negative opt-out)
- "Free trial — no payment required" followed by a required credit card entry field with small-print billing date
- Confirm-shaming: "No thanks, I don't want to save money" as the decline option

---

### Sneaking

**What it is:** Practices introduced after a user has already committed — added items, pre-selected upsells, hidden fees revealed at checkout, or auto-renewal terms buried in onboarding flow.

**Why it works deceptively:** Users anchor on the price or commitment they agreed to; introducing changes after that anchor point exploits sunk-cost framing and the effort already expended.

**How to identify it:**
- Is there anything in the checkout, completion, or confirmation screen that was not visible at the decision point?
- Are there pre-selected add-ons, insurance options, or higher service tiers that require active deselection?
- Does the auto-renewal or recurring charge appear at the same visual weight as the initial price?

**Examples:**
- Pre-ticked donation or charity add-on in e-commerce checkout
- "Your plan renews at $X/year" disclosed only in the order confirmation email, not in the purchase flow
- Default opt-in to data sharing or marketing during account creation, using a pre-checked checkbox

---

### Obstruction

**What it is:** Making a legitimate user action — cancellation, unsubscription, account deletion, complaint submission — deliberately difficult, time-consuming, or confusing.

**Why it works deceptively:** Friction increases abandonment. When friction is asymmetric — signup is three taps, cancellation requires a phone call — the asymmetry itself is the design intent.

**How to identify it:**
- Is the path to cancel, unsubscribe, or delete findable within the same number of steps as the path to subscribe or sign up?
- Does the flow introduce additional steps — confirmation screens, retention offers, "reason for leaving" forms — that are not present in the signup equivalent?
- Does any step require contacting support for an action a user should be able to complete independently?

**Examples:**
- Cancellation flow that routes to a phone-only support queue during limited hours
- Account deletion buried under Settings > Security > Advanced > Data > Delete Account (five levels, no search result)
- "Pause subscription" offered before "cancel" as a retention tactic with no way to reach cancel without seeing the pause offer first

---

## Interaction-Level Dark Patterns (REC-10 Scope)

These patterns occur at the individual interface element or navigation level. They do not require a gamification system to appear.

### Roach Motel

Easy to enter, no visible or intuitive exit. Common in: free trial signups, subscription flows, push notification opt-in prompts, and newsletter subscriptions.

**Audit question:** Can a user undo this action in the same number of steps it took to do it?

### Hidden Exits

Close buttons, back navigation, and cancel actions are visually suppressed (low contrast, small size, unconventional placement) so the default action is the one that benefits the product metric.

**Audit question:** Are the destructive-to-user-value actions (agree, subscribe, enable) visually equivalent in affordance to the neutral or exit actions?

### Disabled Back Navigation

Preventing the browser or OS back button from working correctly during a flow, forcing users to complete or abandon rather than revise their choice.

**Audit question:** Does every step in a multi-step flow support going back without losing previously entered data?

### Confirm Shaming

Using the decline option in a modal or prompt to shame or guilt the user for not converting. A form of Trick Wording but specific to binary choice dialogs.

**Audit question:** Is the decline action phrased neutrally, or does it imply the user is making a negative judgment about themselves?

### Bait and Switch

Advertising one outcome and delivering another — for example, a "free" feature that requires payment revealed after the user has invested effort in setup.

---

## Regulatory Context

### EU General Data Protection Regulation (GDPR) — Consent and Transparency Obligations

GDPR consent rules (Articles 6–7, Recital 32) and the CJEU Planet49 ruling require that consent interfaces present consent and refusal with equal visual prominence. Pre-ticked consent checkboxes are explicitly invalid. Consent obtained through Trick Wording or Sneaking patterns does not constitute valid GDPR consent. GDPR Article 25 (privacy by design) separately requires that data protection is built into processing activities by default — it reinforces but is not the primary source for consent-interface requirements. The EDPB's 2022 deceptive design guidelines further detail how dark patterns in consent flows violate GDPR.

**Practical implication:** Every consent flow — cookie banners, marketing opt-ins, data sharing permissions — must pass a "could a user clearly explain what they agreed to?" test before launch.

### EU Digital Services Act (DSA) — Article 25

Effective from February 17, 2024 for all online intermediary services operating in the EU. The regulation explicitly prohibits "dark patterns" that manipulate users into making unintended choices or that obscure how to exercise rights. The DSA names specific examples: interface design that makes opting out harder than opting in, and UI elements that obscure the nature of advertising. For Very Large Online Platforms (VLOPs/VLOSEs — 45M+ EU monthly active users), enforcement is directly supervised by the European Commission; for other platforms, national Digital Services Coordinators enforce. Note: DSA Article 25(2) excludes practices already covered by GDPR or the Unfair Commercial Practices Directive.

**Practical implication:** Obstruction patterns in unsubscribe and data deletion flows are a specific DSA target. All online platforms in the EU — not only large ones — must provide "simple and user-friendly" means to exercise rights.

### FTC Act — Section 5 (Unfair or Deceptive Acts or Practices)

The US Federal Trade Commission has used Section 5 to take enforcement action against deceptive dark patterns, including: auto-enrollment into paid subscriptions without adequate disclosure, negative-option marketing (the user does nothing = they are enrolled), and difficult cancellation flows. Enforcement has resulted in nine-figure settlements for major consumer platforms.

**Practical implication:** Any negative-option, auto-renewal, or trial-to-paid mechanic must have affirmative informed consent and a cancellation path that is at least as prominent as the enrollment path.

---

## Self-Audit Checklist

Use this checklist during PRD review, design review, and launch readiness checks. Apply it to every screen that guides a user toward a commitment — signup, consent, payment, subscription, notification opt-in, or data sharing.

**Transparency**
- [ ] Can a user who scanned this screen (not read every word) correctly describe what they are agreeing to?
- [ ] Are all material charges, renewals, and data uses visible at the decision point, not only in confirmation emails?
- [ ] Are opt-in and opt-out choices equally visually prominent?

**Reversibility**
- [ ] Can the user undo this action in the same or fewer steps than it took to do it?
- [ ] Does the cancellation or unsubscribe path require contacting support for any step a user should be able to complete independently?
- [ ] Does back navigation work correctly throughout the flow?

**Honest Framing**
- [ ] Are button labels and copy accurate about what happens after the user acts?
- [ ] Does the decline option use neutral language (not confirm-shaming)?
- [ ] Are social proof claims (user counts, reviews, ratings) based on verified, current, accurately described data?

**Regulatory**
- [ ] For products operating in the EU: has this flow been reviewed against GDPR consent requirements and DSA Article 25?
- [ ] For products with auto-renewal or negative-option mechanics: has the FTC negative-option compliance test been applied?

---

## Connection to Existing Ethics Guardrail

The ethical guardrail in `behavioral-design-patterns.md` asks: *does this primarily serve the user's goal or only our metric?*

The deceptive design question is its companion at the interaction level: *does the user know what they are doing, and why?*

A product passes both tests when:
1. The mechanic advances a user goal (behavioral design test)
2. The user can accurately describe what they agreed to before they acted (deceptive design test)

Failing either test is a launch blocker, not a post-launch optimization.

---

## Distinction From Gamification Anti-patterns

`gamification-antipatterns.md` covers failure modes in reward systems, progression mechanics, streaks, and social comparison — failures within a gamified engagement system.

This document covers failure modes at the interface and interaction level: how information is presented, how choices are framed, how exits are designed. These failures apply to products with no gamification at all. Both documents are in scope for any product that uses behavioral mechanics or guides users toward commitments.
