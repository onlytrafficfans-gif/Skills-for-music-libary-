---
name: audio-intake-stem-manager
description: Imports and triages audio files, stems, and MIDI before any other music-production work happens — detects format, sample rate, bit depth, clipping, silence, phase issues, corrupted files, and missing stems, then organizes everything into vocals/drums/bass/instruments/effects/references. Use this FIRST whenever the user uploads or references any audio file, WAV, MP3, stem pack, or MIDI for a music production task, before reverse-engineering, mixing, or mastering. Called by musicos-producer as the first step of Analyze, Finish, Transform, and Rebuild modes.
---

# Audio Intake & Stem Manager

Every downstream music decision (key detection, mix balance, mastering targets) is only as good as the input. This skill's job is to catch problems before they silently corrupt later analysis.

## What to check on intake

For every audio file provided:

1. **Format & technical spec** — container (WAV/MP3/AIFF/video-extracted audio), sample rate, bit depth, channel count (mono/stereo).
2. **Integrity** — clipping (true peak over 0 dBFS), digital silence at start/end, dropouts, corrupted headers, mismatched sample rates across a stem set.
3. **Phase** — check stereo files for phase cancellation when summed to mono; flag if content disappears or thins dramatically.
4. **Noise floor** — hum (50/60Hz and harmonics), hiss, room tone level, obvious mic bleed between stems.
5. **Completeness** — if this is a stem set, identify what's present (vocals/drums/bass/instruments/FX) and what's conspicuously missing for the apparent genre.

Use available audio tooling (ffmpeg/ffprobe in the sandbox, or a code-execution environment with librosa/soundfile) to get real numbers rather than guessing from filenames. If you can't get real measurements (e.g. only a description was given, no actual file), say so plainly instead of inventing plausible-sounding specs.

## Output: Intake Report

```
## Intake Report — [filename(s)]

### Files received
- [filename]: [format, sample rate, bit depth, channels, duration]

### Issues found
- [severity: blocker / warning / note] — [description] — [recommended fix or "proceed with caveat"]

### Stem organization
- Vocals: [file(s) or "not provided"]
- Drums: [file(s) or "not provided"]
- Bass: [file(s) or "not provided"]
- Instruments: [file(s) or "not provided"]
- FX/Ad-libs: [file(s) or "not provided"]
- Reference track(s): [file(s), noted as reference-only]

### Recommendation
[proceed to reverse-engineer / needs stem separation first / needs re-export from source — blocking issue]
```

Write this into the Song Blueprint's Identity/Reference section if one exists for this session (see `musicos-producer`), or present standalone if this skill is being run outside the orchestrator.

## Rules

- A **blocker** (corrupted file, unusable clipping on the only vocal take, mismatched/unusable sample rates) stops the pipeline — tell the user before any other specialist runs, don't quietly work around it.
- A **warning** (mild clipping, some noise floor, minor phase issue) gets logged and passed through — later specialists (mix/master) should be told about it so they can compensate.
- If stems weren't provided and the job needs them (e.g. user wants to remix or isolate the vocal), say stem separation is needed and that quality may be imperfect — don't promise clean isolation from a mixed master.
- Never silently re-encode or resample a file without telling the user what changed and why.
