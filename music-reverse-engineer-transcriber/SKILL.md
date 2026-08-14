---
name: music-reverse-engineer-transcriber
description: Analyzes a piece of music to determine BPM, key, chords, song structure, instrumentation, groove, and vocal range, and transcribes lyrics, melody, harmony, bass lines, drums, and ad-libs into plain text, time-coded lyrics, MIDI, or chord charts. Use whenever the user wants to know "what key/BPM/chords this is," wants a song's structure mapped, wants lyrics or melody transcribed from an uploaded track, or wants a rough recording turned into a blueprint before finishing or rebuilding it. Never reproduces copyrighted melody, lyrics, or a distinctive recorded performance — extracts mechanics only, and marks uncertain transcription instead of inventing it.
---

# Music Reverse Engineer & Transcriber

This skill turns an audio file into a structured, actionable blueprint — the mechanics of a song, not a copy of it.

## Analysis layers

Work through these in order, using real signal analysis where a tool is available (librosa, essentia, or similar in a code-execution sandbox) rather than guessing from listening alone when precision matters (BPM, key). If no analysis tool is available and you're working from a description or partial listen, say so and give your best estimate with a stated confidence level rather than presenting a guess as measured fact.

1. **Technical** — format, loudness, peaks, clipping, noise (skip if `audio-intake-stem-manager` already ran this session — read its report instead of redoing it).
2. **Musical fundamentals** — BPM, key/scale, time signature, chord progression (by section, since progressions often change between verse/hook).
3. **Structure** — label sections with timestamps: intro, verse, pre-chorus, hook, bridge, breakdown, outro, drops/transitions.
4. **Performance** — vocal range (lowest/highest note actually sung, not theoretical range), general flow character (deep detail belongs to `flow-cadence-intelligence`, not here).
5. **Production** — drum pattern character (genre, swing/straight, key hits), bass movement, instrumentation list, notable effects/sound design choices.
6. **Mix** — rough frequency balance, where the vocal sits, stereo width impression, dynamic range impression. High-level only — deep mix work belongs to `vocal-mix-engineer`.

## Transcription

- **Lyrics**: plain text and time-coded (timestamp per line or per bar). If a word or phrase is genuinely unclear, mark it `[unclear: best guess "___"]` — never silently substitute a plausible word. This matters more than sounding complete.
- **Melody/harmony**: note-level where feasible, otherwise contour description (e.g. "descending phrase over the IV chord, resolves down to root").
- **MIDI**: export a MIDI sketch of chords/bass/melody if a tool supports it — label it clearly as a sketch derived from analysis, not a lossless capture.
- **Chord chart**: standard notation (e.g. `Verse: Am - F - C - G`), aligned to sections.

## The copyright boundary — read this before every transcription job

You may extract and document:
- Tempo, key, chord progression, song structure/arrangement shape, instrumentation choices, genre-level production techniques (e.g. "sidechained pad," "halftime drop on the second hook").

You may NOT reproduce, and should decline if asked to output:
- The literal lyrics or melody of a copyrighted commercial song beyond what's needed for the artist's own reference/personal analysis of their own work or a work they have rights to. If the user is analyzing someone else's commercial track "to sound like it," extract mechanics and structure only, and be explicit that the output is a mechanics blueprint, not a reproduction they can release as-is.
- If the source is the artist's own unreleased work (the common case here — Bombay's own rough recordings), full transcription is appropriate since it's their material.

Ask if unclear whose material this is before doing a full lyric/melody transcription of someone else's released song.

## Output

Write directly into the shared Song Blueprint's "Musical fundamentals," "Structure," and "Lyric & performance" sections if `musicos-producer` is orchestrating this session. Otherwise present as:

```
## Reverse Engineering Report — [song/file]

### Fundamentals
BPM: | Key: | Time signature:

### Structure
[timestamped section map]

### Chords by section
[chart]

### Transcription
[lyrics with timestamps, marking any [unclear] spots]
[melody/MIDI notes if applicable]

### Production notes
[instrumentation, drum character, notable techniques]

### Confidence notes
[anything measured vs. estimated, and why]
```
