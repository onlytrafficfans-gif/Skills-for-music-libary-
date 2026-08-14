---
name: arrangement-director
description: Turns a loop, beat, or set of song elements into a complete record — directing intros, drops, transitions, breakdowns, bridges, drum changes, tension and release, vocal space, and the energy curve across the full track timeline. Use whenever the user has a beat or verse/hook loop and needs it turned into a full song structure, wants help with transitions or a section that feels stuck/repetitive, or wants the overall energy curve of a track evaluated and improved. Distinct from beat-production-engine (which designs the sonic palette) and music-reverse-engineer-transcriber (which analyzes existing structure) — this skill decides how the song moves through time.
---

# Arrangement Director

A great loop and a great song are different things. This skill's entire job is what happens *between* the good parts — the transitions, the moments of contrast, the points where energy builds or drops — because that's what separates a demo from a record.

## The energy curve — map it explicitly

Before making section-by-section decisions, sketch the intended energy curve across the whole timeline (low → high, with the actual arc, not just "it should build"). A song that's at 8/10 energy for its entire runtime is exhausting; a song that never rises above 4/10 is boring. Name the shape: where's the lowest point, where's the peak, does it peak once or multiple times, does the ending resolve down or stay elevated.

## Section-by-section direction

For each section, decide and state:

1. **What enters and what drops out** — arrangement density is a primary energy tool. Going from "everything playing" to "just vocal and one instrument" is often a stronger effect than adding more layers.
2. **Drum pattern changes** — does the drum pattern stay identical throughout, or does it evolve (half-time switch, added percussion, a fill that signals a section change)? Static drums across a whole song is a common cause of a track feeling flat.
3. **Transition mechanics** — how does one section physically move into the next: a fill, a riser/sweep, a vocal ad-lib, a full stop, a filtered buildup? Specify the actual mechanism, not just "smooth transition."
4. **Vocal space** — where does the arrangement pull back to let the vocal breathe, and where does it fill space during instrumental moments? Vocal-heavy sections often need the *least* instrumental movement, not the most.
5. **Tension and release** — identify where the song is deliberately withholding (a section that feels like it's building to something) and confirm the payoff actually delivers when it arrives — a buildup with no payoff is a common structural flaw.

## Common structural problems to check for

- **The hook doesn't feel different enough from the verse** — if the arrangement doesn't change meaningfully going into the hook, the hook won't land no matter how good the writing is.
- **Second verse/hook fatigue** — an identical repeat of an earlier section with zero variation reads as lazy, not consistent. Suggest a specific variation (drum change, added layer, vocal ad-lib, filtered intro) even if small.
- **No real ending** — a fade-out by default is often a missed opportunity; consider whether the song has an actual outro idea.
- **Bridge that doesn't justify itself** — see `songwriting-architect`'s bridge criteria; arrangement should reinforce that the bridge is doing something different (instrumentation drop, key/feel shift, space).

## Output

```
## Arrangement Direction — [song]

### Energy curve
[described shape across the full timeline, peak location(s), lowest point]

### Section-by-section plan
[section : what's in/out : drum treatment : transition into next section : vocal space notes]

### Structural flags
[repetition without variation, missing payoff, weak transitions, hook not differentiated enough]

### Transition details
[specific mechanism per transition point]
```

Write into the Song Blueprint's "Structure" and "Production" sections. If working from a beat brief from `beat-production-engine`, reference its palette rather than re-describing sounds — this skill's job is movement through time, not sound design.

## Rules

- Don't recommend "add more" as a default fix for a flat section — pulling elements out is at least as often the right call, and it's the one people reach for less.
- Every transition recommendation should name a concrete mechanism, not just say "make it flow better."
- If the song's existing structure (from a reverse-engineered reference or an already-recorded vocal) constrains what's possible, work within that rather than proposing a structure that would require re-recording — flag it if a structural fix genuinely does require that.
