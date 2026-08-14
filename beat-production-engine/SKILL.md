---
name: beat-production-engine
description: Designs an original beat/instrumental from scratch using BPM, key, mood, genre, and instrumentation instructions — producing drum pattern direction, sound-selection notes, chord/bass movement, swing/groove feel, and automation guidance, output as a production brief and MIDI sketch rather than final audio. Use whenever the user wants a new beat concept, wants direction on drum programming or sound selection, wants a reference track's beat mechanics turned into an original instrumental, or needs a production starting point before arrangement. Does not generate final mixed audio — produces the creative and technical brief a producer or DAW session would execute from.
---

# Beat Production Engine

This skill designs the sonic and rhythmic blueprint of a beat — it does not render final audio (no DAW/synth engine is available here). What it produces is precise enough that a producer, or a DAW session guided by these notes, can execute it directly.

## Inputs to establish first

- **BPM range and feel** — exact tempo, or a feel description ("mid-tempo, laid back" vs. "uptempo, aggressive") that you translate to a BPM range.
- **Key/mode** — and whether the artist wants major/minor/modal color, or something more ambiguous (common in darker trap/R&B production).
- **Genre and reference points** — if a reference track was reverse-engineered by `music-reverse-engineer-transcriber`, pull its structural mechanics (never its specific melody/samples) as a starting point.
- **Mood/energy target** — one or two words that anchor every downstream choice (e.g. "nocturnal, menacing" for a 73RD ST.-style record vs. "warm, triumphant" for something else).

## Design layers

1. **Drum pattern** — kick/snare/hat pattern character: genre-appropriate placement, swing amount (straight vs. swung 16ths/triplets), where the pattern breaks or fills, hi-hat roll style if relevant. Describe in enough rhythmic detail that it could be programmed directly (e.g. "kick on 1 and the 'and' of 2, snare on 3, hats straight 16ths with a triplet roll into the hook").
2. **Bass** — movement relative to the chord progression, whether it's a sustained sub, a moving melodic bassline, or rhythmic and percussive; relationship to the kick (locked together vs. syncopated against it).
3. **Chords/harmony** — progression, voicing character (sparse and wide vs. dense and close), instrument choice (piano, pad, guitar, synth) and its emotional color.
4. **Melodic elements** — lead lines, counter-melodies, ear-candy — what they do and where they sit in the arrangement, not just "add a melody."
5. **Sound selection notes** — texture direction (e.g. "detuned analog-style saw for the lead," "vinyl-crushed drums," "clean and modern 808") — describe character, not brand-specific plugin names unless the user asks for that level of DAW-specific detail.
6. **Groove/swing consistency** — state explicitly whether the whole beat locks to one feel or shifts between sections (common device: straighter verse, more swung hook).

## Output

```
## Beat Production Brief — [song/project]

### Foundation
BPM: | Key/mode: | Genre/mood target:

### Drum pattern
[detailed rhythmic description, swing/groove notes]

### Bass
[movement, relationship to kick and chords]

### Harmony
[progression, voicing character, instrumentation]

### Melodic/lead elements
[what exists, where it sits, what it does across sections]

### Sound character notes
[texture/character direction per element]

### MIDI sketch
[if a tool is available, export a MIDI file of chords/bass/drum pattern; otherwise provide the info precise enough to program manually]
```

Feed this into the Song Blueprint's "Production" section. If `arrangement-director` is being used in the same session, hand this brief to it for the section-by-section arrangement decisions — this skill designs the palette, arrangement-director decides how it moves through the song.

## Rules

- Never reproduce a specific, recognizable beat/instrumental from a copyrighted reference — extract groove feel, instrumentation category, and structural approach only, same boundary as `music-reverse-engineer-transcriber`.
- Don't invent a "final master-ready" claim — this is a brief and MIDI sketch, not finished audio. Be explicit about that so the user doesn't think a track just got rendered.
- If BPM/key conflicts with something already locked in the Song Blueprint (e.g. by `music-reverse-engineer-transcriber` on an existing vocal), flag the conflict — don't silently pick one.
