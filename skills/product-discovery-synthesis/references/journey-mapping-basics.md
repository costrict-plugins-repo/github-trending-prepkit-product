# Journey Mapping Basics

Reference: NNGroup — "Customer Journey Mapping 101"; NNGroup — "Service Blueprints"

## Why Journey Mapping Exists

The Opportunity Solution Tree requires opportunity inputs — unmet needs and friction points in user language. JTBD interviews and ODI Job Map analysis generate strong single-job inputs, but they have a structural blind spot: they focus on one job's functional steps, not on the full experience arc across multiple touchpoints, channels, and sessions.

Journey mapping surfaces the friction that is only visible at the arc level:
- Multi-step friction that accumulates across sessions (no single interview moment captures it)
- Channel handoff failures (the user's mental model breaks when moving between web, mobile, and support)
- Emotional low points that are disproportionate to functional severity (a brief wait that causes high anxiety; a minor error message that erodes trust)
- Opportunity areas that fall *between* the product's current feature boundaries — the product does not know about them because it does not touch that phase

Without a prior-stage mapping tool, opportunity identification relies on interview recall, which systematically underweights systemic friction. Journey maps make that friction visible and create a team alignment artefact.

---

## Five Essential Elements

| Element | What it is | What good looks like |
|---|---|---|
| **Actor** | The specific user type this map represents | One persona or segment per map; not "all users" |
| **Scenario + expectations** | The goal the actor is trying to achieve and their starting assumptions | Written in user language; includes what they expect to happen, not what actually does |
| **Phases** | High-level stages of the experience from the user's perspective | Named for what the user is doing ("deciding", "setting up", "asking for help"), not for what the product does ("onboarding", "activation") |
| **Actions / mindsets / emotions** | Per phase: what the user does, what they think, and how they feel | Grounded in research observations, not assumed; emotions are the most frequently skipped — do not skip them |
| **Opportunities** | Friction points, unmet needs, and moments of delight mapped to specific phases | Phrased as user needs, not product solutions; these are the direct inputs for OST opportunity nodes |

---

## When To Use vs. ODI Job Map

| Use journey mapping when... | Use ODI Job Map when... |
|---|---|
| Discovery involves multiple touchpoints, channels, or sessions | The team needs deep functional analysis of one specific job |
| Friction may be distributed across phases, not concentrated in one step | The team needs 100+ desired outcomes ranked by importance/satisfaction |
| Stakeholder alignment across teams (product, design, support, marketing) is needed | The question is "which job steps are most underserved?" |
| The experience arc includes non-product moments (before first use, post-cancel, onboarding handoffs) | The question is "how do we prioritise innovation investment in this job?" |

ODI Job Map walks one functional job's universal eight steps (define, locate, prepare, confirm, execute, monitor, modify, conclude). Journey mapping walks the lived experience arc, which typically spans multiple functional jobs and includes the emotional dimension. They are complementary: use ODI for depth within a job; use journey mapping for breadth across the experience.

---

## How To Build

1. **Define the actor and scenario first.** One actor per map. Write the scenario as: "Actor is trying to [goal] in [context], expecting [starting assumption]." This anchors every subsequent step.

2. **Name phases from the user's perspective.** Typically four to eight phases. Name them for what the user is doing or experiencing — not for what the product does. "Realising something is wrong" is a user phase; "error state" is a product phase.

3. **Map actions, mindsets, and emotions per phase.** For each phase, answer three questions:
   - What does the user *do*? (observable actions, channels used, alternatives tried)
   - What does the user *think/feel*? (beliefs, concerns, level of confidence)
   - How does the user *feel emotionally*? (frustration, anxiety, relief, confusion)
   Draw an emotion curve across phases — high points and low points become immediately visible.

4. **Identify high-friction moments.** Moments where the emotion curve drops sharply, where the user resorts to a workaround, or where expectations clash with reality are the highest-value opportunity candidates.

5. **Extract opportunity labels.** For each high-friction moment, write one opportunity in user language: "Struggle to [understand / find / recover / complete] when [context]." These are the direct inputs for OST opportunity nodes.

---

## How It Feeds OST

```
Journey map opportunities layer
  → OST opportunity nodes (unmet needs, friction points in user language)
    → OST solutions (specific capabilities to address each opportunity)
      → OST experiments (assumptions to test)
```

A journey map opportunity should pass the same filter as any OST opportunity: phrased as a user need, not a product feature. "Difficulty confirming a booking change across channels" passes. "Add cross-channel notifications" does not — that is already a solution.

---

## Anti-patterns

| Anti-pattern | Why it fails | Fix |
|---|---|---|
| Mapping the product workflow instead of the user experience | Produces a features inventory, not insight into friction | Reframe each phase by asking "what is the user trying to do here?" not "what does the product do here?" |
| Skipping the emotions layer | Misses the severity signal — minor functional friction can be catastrophic emotionally | Always draw the emotion curve; treat empty Feels cells as a gap to fill before synthesis |
| Building the map without research grounding | Produces a team assumption map, not a user experience map | Each observation cell should reference at least one interview quote or observation |
| Using the map as a one-time artefact | Stale maps actively mislead — teams cite them as evidence when they are no longer current | Treat the map as a living document; update it when research reveals contradictions |
| One map for all user types | Different actors have different experience arcs; a combined map papers over the differences | One actor per map; build separate maps for segments with meaningfully different journeys |
