---
name: mastering-quality-control
description: Produces final loudness, tonal balance, dynamics, stereo control, sequencing, and fades, and generates format-specific masters (streaming, video, instrumental, clean, a cappella/performance, high-resolution). Also runs critical listening QA — checks clipping, distortion, phase, mono compatibility, excessive sibilance, muddy lows, harsh highs, vocal masking, bad edits, and artifacts, and evaluates translation across headphones, phone speakers, car systems, and club systems. Use as the final step before a track is considered release-ready, or whenever the user wants a mastered track checked for technical or perceptual problems before shipping.
---

# Mastering & Quality Control

The last gate before a track goes out. Two jobs: produce the master(s), and independently verify nothing is broken — even a master you just made yourself.

## Mastering

1. **Loudness** — target appropriate to the platform (streaming platforms typically normalize around -14 LUFS integrated; note that this varies by platform and changes over time, so state your target explicitly and flag that the user should verify current platform specs rather than treating any number as permanently fixed).
2. **Tonal balance** — final EQ pass across the full mix, checking against reference tracks in the genre if provided.
3. **Dynamics** — appropriate compression/limiting for the target loudness without crushing the performance's dynamic range into lifelessness.
4. **Stereo control** — final width/mono-compatibility check.
5. **Sequencing & fades** — if this is part of a multi-track project, spacing and transition handling; clean fade-ins/outs with no clicks.

## Required delivery versions

Unless the user says otherwise, ask which of these are needed rather than assuming all are required (some are extra work the user may not want yet):

- Streaming master (standard loudness target)
- Video/sync master (may need different loudness handling)
- Instrumental version (vocal removed/never included)
- Clean version (if explicit content needs an edited version)
- Full-quality/high-resolution archive master (uncompressed, for the artist's own archive — this is the version everything else derives from)

## Quality Control checklist — run this independently, even on your own master

```
[ ] Clipping / inter-sample peaks
[ ] Distortion (intentional vs. unintentional — flag anything that sounds like an error)
[ ] Phase issues (mono sum check)
[ ] Mono compatibility (does anything disappear or thin out badly in mono)
[ ] Excessive sibilance
[ ] Muddy low end
[ ] Harsh/fatiguing high end
[ ] Vocal masking (is the vocal legible against the instrumental at every section)
[ ] Edit artifacts (clicks, pops, bad crossfades, breath cut-offs)
[ ] Translation check — how does this likely hold up on: headphones / phone speaker / car system / club system (reason about frequency response differences, don't just say "sounds fine")
```

Any failed item is a **blocker** — do not present a track as release-ready with an open QA failure. State it plainly.

## Output

```
## Master & QA Report — [song]

### Deliverables produced
[list with format/loudness spec per file]

### QA results
[checklist with pass/fail/flag per item]

### Blockers
[anything that must be fixed before release — be direct, don't soften a real problem]

### Release-ready?
[yes / no — if no, what's blocking]
```

Write final deliverables into the Song Blueprint's "Approved deliverables" section only after QA passes — never mark something approved with an open blocker, even if the user is in a hurry.

## Rules

- Loudness targets and platform specs change — if precision matters for a specific release, tell the user to verify current platform requirements rather than treating your stated number as guaranteed current.
- Don't rubber-stamp your own or another skill's mastering work — QA is meant to be adversarial to the mix/master, not a formality.
