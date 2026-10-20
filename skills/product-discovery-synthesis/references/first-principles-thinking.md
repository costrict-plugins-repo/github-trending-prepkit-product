# First-Principles Thinking

## When To Use
- Team stuck, looping, making unexamined assumptions
- A framework (JTBD, RICE, etc.) is producing conflicting signals
- First-principles is the meta-tool you reach for *alongside* existing frameworks, not instead of them
- Use when the problem framing feels inherited rather than earned

## Method
1. Identify the claim or decision under debate
2. Strip away assumptions — what are we taking for granted?
3. Trace to axiomatic truths — what do we actually know from evidence?
4. Rebuild from those truths
5. Then re-apply your existing framework (JTBD, HCD, RICE, etc.) with the clarified foundation

## Combining With Existing Frameworks
How first-principles enhances each:
- JTBD: question whether the assumed job is real or inherited from a competitor's framing
- HCD/Empathy mapping: question whether empathy data reflects axioms or conventions
- RICE: question whether the impact assumption is grounded in evidence or consensus
- Metrics (HEART, AARRR): question whether the metric measures the real outcome or a proxy nobody verified
- OST: question whether the opportunity is real or an artifact of the current solution space

The frameworks provide structure; first-principles provides the foundation check. Always hand back to a framework after decomposition.

## Show, Don't Tell — Cross-Cutting Design Principle

This principle applies across almost every feature on the system, not just PLG or freemium flows:

- **Core axiom**: users trust what they experience more than what they're told. Demonstrated value always outweighs described value.
- **Onboarding**: show the product working on the user's real task, don't explain features in a tour
- **Feature discovery**: let users encounter value naturally in their workflow, don't tooltip-spam or feature-announce
- **Error states**: show what went wrong, what data was affected, and how to fix it — don't just say "something went wrong"
- **Settings and configuration**: show a live preview of what changes, don't describe what a toggle does in text
- **Upgrade and upsell paths**: let users hit a natural boundary, then show what the premium experience adds — don't pitch upgrades before users need them
- **Reporting and analytics**: show the insight in context, don't make users interpret raw numbers
- **Help and support**: show the solution working step-by-step, don't link to documentation walls

**When applying Show, Don't Tell to any feature**: ask "can the user experience this value directly, or are we asking them to imagine it from a description?" If the answer is "imagine," redesign the interaction to demonstrate.

For PLG-specific application of this principle, see `packs/product/skills/domain/product-engagement-design/references/plg-flow-design.md`.

## Startup Mindset
- 1 problem has n solutions, 1 solution has m implementations — anyone who says there's only one way is wrong
- No formula — slow burn or no burn is fine, as long as you're building equity
- Think-act-do-react like a startup regardless of org size
- **Bounded experimentation**: explore multiple paths, try fast, iterate — but within existing evidence-first posture, compliance requirements, observability expectations, and rollback constraints
- Not a license to skip safety; a license to explore more paths within safety
- Even with limited money, invest in what builds long-term brand recognition and equity

## Worked Examples

### Example 1: "Why does this feature need to be free?"
Framework in use: RICE scoring showed high reach for a free tier
First-principles check: What is the axiomatic truth here?
- Axiom: our marginal cost per user is near-zero (digital content)
- Axiom: users cannot evaluate quality without experiencing it
- Rebuilding: free access is not a pricing strategy — it's a demonstration strategy. The cost is negligible; the value is letting users prove quality to themselves.
Combined answer: RICE score is valid, but the framing changes from "free tier to reach more people" to "free access as the primary value demonstration mechanism" — which changes what you optimize in the free experience.

### Example 2: "Why do users need to onboard in under 5 minutes?"
Framework in use: UX benchmarking against competitor onboarding flows
First-principles check: Is 5 minutes an axiom or a convention?
- Axiom: users will abandon any experience where perceived effort exceeds perceived value
- Not an axiom: "5 minutes" — this is an industry average, not a truth about our users
- Rebuilding: the real question is "what is the minimum path to the first wow moment?" For our product, that might be 2 minutes or 15 minutes depending on the content.
Combined answer: Keep the UX benchmarking for competitive context, but design the onboarding around time-to-wow-moment, not an arbitrary time budget.

### Example 3: "Why do we need DAU as our primary metric?"
Framework in use: HEART framework selected Engagement (DAU) as primary
First-principles check: Is daily active usage actually the value driver?
- Axiom: our product delivers value through practice sessions that improve test scores
- Not an axiom: "daily usage drives outcomes" — spaced repetition research shows optimal intervals are NOT daily for all content types
- Rebuilding: the real metric is "sessions completed at optimal spacing" not "daily opens"
Combined answer: HEART framework is correct to measure engagement, but the engagement metric should be "practice sessions at recommended intervals" not raw DAU.

## Failure Modes
- **Stopping too early** — declaring something an axiom when it's still an assumption (e.g., "users want X" without evidence)
- **Treating conventions as axioms** — "everyone does it this way" is not a first principle
- **Analysis paralysis** — decomposing endlessly without rebuilding and acting
- **Abandoning frameworks entirely** — first-principles without structure is just brainstorming; always hand back to a framework
- **Using startup mindset to justify skipping evidence** — "move fast" does not mean "skip research"; it means "research faster and iterate"
- **Conflating correlation with causation** — observed patterns are not axioms
