---
name: vocal-producer
description: Directs a vocal performance before any processing happens — defining tone, emotion, pitch approach, diction, intensity, register, breath strategy, doubles, harmonies, ad-libs, pickup notes, and punch-in points, and producing a concrete recording/performance plan. Use whenever the user is about to record or re-record a vocal and wants direction on how to perform it, wants a take evaluated for performance quality (not just pitch/timing accuracy), or is deciding between takes based on emotional delivery. Distinct from vocal-mix-engineer, which handles editing/tuning/processing after the performance exists — this skill's job is entirely pre-processing and performance-focused.
---

# Vocal Producer

The most important decisions in a vocal happen before a single plugin is touched. This skill exists to make those decisions deliberately instead of by default, and to evaluate performances on emotional truth first, technical accuracy second.

## Performance planning — before recording

Establish, and state explicitly:

1. **Emotional target** — what should the listener feel on this specific line/section? Not "good" — specific: vulnerable, defiant, exhausted, triumphant, detached. Different sections of the same song usually need different emotional targets (verse ≠ hook, often).
2. **Tone and intensity** — chest voice vs. head voice vs. mixed, spoken-word intensity vs. full-throated, whispered vs. belted. Match to the emotional target, not to habit.
3. **Diction** — how much consonant clarity/enunciation serves this specific line — sometimes deliberately loose/slurred delivery is more honest than crisp diction, especially in verses carrying vulnerable content.
4. **Register and range** — where in the artist's comfortable range this section sits, referencing the Artist Identity profile if available; flag if a written melody pushes outside their comfortable range and suggest an alternative rather than forcing a strained take.
5. **Breath strategy** — where breaths should land musically (before this reveals too much or interrupts a phrase, they should be placed intentionally); note where a performer should breathe *quietly* vs. where an audible breath actually serves the performance.
6. **Doubles, harmonies, ad-libs** — decide deliberately which lines get doubled (usually hooks, key emotional lines), what harmony intervals serve the emotional color (unison for intensity, thirds/fifths for lift, dissonant intervals for tension), and where ad-libs add character vs. clutter.
7. **Pickup notes and punch-in points** — where a performer needs a pickup note/cue before a phrase to nail the entrance, and where clean punch-in points exist for re-takes without disrupting flow.

## Evaluating takes

When comparing multiple takes, evaluate on:

- **Emotional truth first** — does this take actually deliver the emotional target, even if it has minor pitch/timing imperfections? A technically cleaner take that doesn't convince emotionally is usually the wrong choice.
- **Technical accuracy second** — pitch, timing, breath control — these matter, but `vocal-mix-engineer` can correct minor technical issues without damaging performance; it generally cannot fix a performance that doesn't emotionally land.
- **Comping guidance** — if the best performance is spread across multiple takes, identify which phrases from which takes to combine, and flag if a comp risks creating an inconsistent emotional arc across the line.

## Output

```
## Vocal Performance Plan — [song/section]

### Emotional target by section
[section : target emotion/intensity : tone/register notes]

### Recording plan
[breath strategy, pickup notes, punch-in points, doubles/harmonies/ad-lib decisions]

### Take evaluation (if takes already exist)
[take : emotional read : technical notes : recommendation]

### Comp guidance
[if combining takes: which phrases from which take, and continuity flags]
```

Hand off to `vocal-mix-engineer` for actual editing/tuning/processing once the performance plan or take selection is settled — this skill should never itself apply corrective processing. Write the finalized performance plan into the Song Blueprint's "Lyric & performance" → vocal range and performance plan field.

## Rules

- Never recommend heavy pitch correction as a substitute for a better take — that's a `vocal-mix-engineer` decision made after this skill has done its job, and even then the source material said to preserve natural pitch movement by default.
- Don't evaluate a take purely on technical cleanliness — an imperfect take that's emotionally convincing beats a perfect take that isn't, and this skill should say so directly when that's the case, even if it's not what the user expects to hear.
- If a written melody or key doesn't fit the artist's actual comfortable range, say so and suggest an adjustment rather than directing them toward a strained performance.
