# Empathy Mapping for Synthesis

Reference: NNGroup — "Empathy Mapping: The First Step in Design Thinking"

## Why This Step Exists

The synthesis path — interviews → affinity mapping → JTBD — correctly extracts functional themes but does not systematically prompt for the emotional and latent belief dimensions of a job. Affinity mapping groups what users *said*; it does not require the team to ask what users *believe internally* or how they *feel* during the experience. The result is JTBD statements that are functionally accurate but emotionally thin — and thin emotional framing produces solutions that solve the functional job without resonating with the user's underlying motivation.

Empathy mapping adds a structured forcing function before JTBD synthesis that ensures all four signal types are captured and inspected together.

---

## The Four Quadrants

| Quadrant | What it captures | Source material |
|---|---|---|
| **Says** | Verbatim quotes from interviews or observation | Direct quotes from interview recordings or transcripts — never paraphrase |
| **Thinks** | Internal beliefs, assumptions, or mental models — often not spoken aloud | Researcher inference from probing questions ("what were you worried about?") and reading between the lines. Label each item as inference and link it to the supporting Says quote or observation that grounds it |
| **Does** | Observable behaviours, actions taken, workarounds in use | Behavioural descriptions from the timeline interview, usage logs, direct observation |
| **Feels** | Emotional states — frustration, anxiety, confidence, relief | Tone-of-voice signals, facial expressions (if in person), explicit statements about feeling |

One observation per item. Says must be strictly verbatim — preserve exact user language. Thinks is explicitly researcher inference, not verbatim — each Thinks item must point back to a supporting Says quote or behavioral observation to prevent inference from becoming fake evidence.

---

## When To Use

**After:** user interviews (all participant notes should be the input)
**Before:** affinity mapping and JTBD synthesis
**Skip when:** the team has strong, recent empathy maps for the segment already built — do not rebuild for each synthesis cycle; update when new signal contradicts existing quadrants

If emotional signal is thin after interviews (e.g. short answers, task-focused protocol that did not probe feelings), empathy mapping is especially important — it makes the gap visible rather than hiding it in the JTBD output.

---

## How To Build

1. **One map per participant** first. Transfer each participant's observations into the four quadrants using sticky notes or a shared digital board. One observation per item.
2. **Look for quadrant imbalance.** If Says and Does are dense but Thinks and Feels are sparse, the interviews lacked emotional probing. Flag this before synthesis continues — sparse Thinks/Feels means the emotional job is estimated, not evidenced.
3. **Find juxtapositions.** The most useful observations are cross-quadrant contradictions:
   - Positive Does + negative Feels = unmet need (user works around the problem but resents it)
   - Confident Says + anxious Thinks = hidden barrier (user says the right thing but does not believe it)
   - Frequent Does + absent Feels = habituated pain (user has normalised the friction)
4. **Aggregate per segment.** After individual maps are built, produce one aggregate map per user segment. Aggregate by frequency — only carry observations forward that appear across multiple participants. Individual outliers should be noted separately.

---

## Integration with Affinity Mapping

Empathy mapping and affinity mapping are complementary, not competing:

- **Empathy mapping** ensures all four signal types (Says/Thinks/Does/Feels) are represented per observation before grouping begins
- **Affinity mapping** then groups observations across participants into themes

Run empathy mapping first (per participant), then feed the populated quadrant items into the affinity mapping session. Name affinity clusters after the quadrant type is clear — "frustration cluster" rather than just "slow load time cluster."

---

## How It Feeds JTBD

After empathy mapping, JTBD synthesis becomes more precise:

- **Feels/Thinks** → emotional and social job context ("when I [context], I want to [progress], so I feel [emotional outcome]")
- **Does** → the functional job and the current alternative
- **Says** → verbatim evidence for the JTBD statement's language

A JTBD statement that cannot be grounded in at least one Thinks or Feels observation is a functional job hypothesis, not a validated job. Label it as such.

---

## Common Mistakes

| Mistake | Why it fails | Fix |
|---|---|---|
| Building one aggregate map directly | Hides participant-level variation; outliers are lost | Build per-participant maps first; aggregate second |
| Paraphrasing Says quadrant | Loses the user's exact framing; introduces researcher interpretation | Quote verbatim; summarise only in the aggregate |
| Treating Thinks as a copy of Says | Thinks captures what is *not* said — inferences from context and probing | Go back to the interview transcript; look for hedges, contradictions, and omissions |
| Skipping Feels entirely | Produces a functional map only; emotional job is absent from JTBD synthesis | If Feels is empty, acknowledge the gap explicitly and plan a follow-up probe |
| Stopping at one round | Empathy maps go stale as the problem evolves | Rebuild or update after each major research cycle |
