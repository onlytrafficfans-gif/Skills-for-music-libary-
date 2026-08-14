---
name: flow-cadence-intelligence
description: Analyzes a rap or vocal performance for syllable count, rhyme placement and density, stresses, breath points, pickup notes, pocket/timing relative to the beat, swing, triplets, and melodic phrasing — mapping a vocal performance bar by bar. Use whenever the user wants their flow analyzed, wants to know if their cadence is landing in the pocket, wants help matching a new verse's flow to an existing one, or wants a bar-by-bar breakdown of rhyme scheme and rhythm. Distinct from music-reverse-engineer-transcriber, which handles chords/key/structure — this skill is specifically about how the vocal performance rides the beat.
---

# Flow & Cadence Intelligence

This skill answers "does this flow work" and "why" — with bar-level specificity, not vague praise or criticism.

## What to measure per bar

For each bar (or line, if the material isn't strictly bar-aligned):

1. **Syllable count** — total, and where they cluster (front-loaded, back-loaded, evenly spaced).
2. **Rhyme scheme** — end rhymes, internal rhymes, multisyllabic rhymes, near-rhymes/slant rhymes. Map which words rhyme with which across the bar and across the section — build an actual rhyme map, not just "it rhymes."
3. **Stress pattern** — where the emphasized syllables fall relative to the beat (on-beat, off-beat, syncopated).
4. **Pocket/timing** — is the delivery locked to the grid, deliberately behind/ahead (dragging or rushing), or does it drift unintentionally? Distinguish intentional pocket choices from timing that's just off.
5. **Breath points** — where the performer breathes, and whether that breath lands in a musically sensible gap or cuts into a phrase awkwardly.
6. **Swing/triplet feel** — straight 8ths/16ths vs. triplet or swung subdivisions, and whether it's consistent or shifts intentionally between sections.

## Comparative mode

When the user wants a new verse to match an existing flow (common in "finish this song" jobs), don't just describe the reference flow in prose — produce a literal syllable/stress template the new bars can be checked against:

```
Bar 1: ba-BA-ba-ba-BA-ba (6 syllables, stress on 2 and 5)
Bar 2: ...
```

Then check the new lyrics against that template line by line and flag where syllable count or stress pattern breaks the established pattern — but note that intentional variation (a deliberate pocket shift for emphasis) isn't automatically a flaw. Ask if the mismatch is intentional before "fixing" it.

## Output

```
## Flow & Cadence Report — [song/section]

### Bar-by-bar map
[bar : syllables : stress pattern : rhyme tags]

### Rhyme scheme summary
[end rhymes, internal rhymes, multisyllabic chains, density trend across the section]

### Pocket notes
[on-grid vs. intentional push/pull, breath placement quality]

### Flags
[any spot where timing seems unintentionally off, or a breath cuts a phrase awkwardly]
```

If this is running inside a `musicos-producer` session, write the summary into the Song Blueprint's "Lyric & performance" → flow/cadence notes field.

## Rules

- Never flatten a deliberate rhythmic choice into "correct" — ask before "fixing" anything that could be stylistic (this is especially important for artists with a distinctive pocket, which the Artist Identity profile should note if one exists).
- Be specific with bar numbers and word-level examples, not general vibes ("the flow feels good here" is not useful output).
