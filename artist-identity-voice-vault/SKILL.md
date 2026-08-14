---
name: artist-identity-voice-vault
description: Learns and preserves an artist's recurring vocabulary, subjects, rhyme density, delivery style, vocal range, preferred song structures, and ad-libs as a durable creative-identity profile, and manages the Voice Vault — a chain-of-custody archive of approved voice recordings, consent scope, and provenance for any voice model or generated vocal. Use whenever the user wants to build or update an artist's style profile, wants a new lyric/vocal choice checked against "does this sound like me," wants to store or organize voice recordings for future use, or asks about consent/permissions/tracking for AI-generated vocals. This skill supports multiple artist profiles (Bombay, other Bombay Studios artists, AI singers) — always confirm which profile is in scope before writing.
---

# Artist Identity & Voice Vault

Two responsibilities live here, kept in separate but linked records: **Identity** (creative fingerprint) and **Vault** (physical voice asset custody + consent). Never merge them into one blob — Identity gets read by songwriting/flow work constantly; Vault gets touched rarely and needs stricter access discipline.

## Multi-artist support

Before writing anything, confirm which artist/profile this session is for. Maintain one profile file per artist (e.g. `identity-bombay.md`, `identity-[artist-name].md`). Never blend two artists' vocabulary or voice data into one profile, and never let a generated vocal for Artist A get filed under Artist B's Vault, even accidentally.

## Identity Profile — what to capture and maintain

```
# Artist Identity — [name]

## Vocabulary & subject matter
- Recurring words/phrases used often:
- Subjects/themes returned to:
- Words or topics the artist avoids or refuses:

## Delivery
- Typical rhyme density (sparse / moderate / dense — with examples):
- Signature ad-libs:
- Preferred pocket/flow characteristics (link to flow-cadence-intelligence output if analyzed):

## Structure preferences
- Typical song structures used:
- Typical hook style:

## Vocal
- Comfortable vocal range (link to Vault for source recordings):
- Registers used (chest/head/falsetto/spoken):

## Visual/brand themes (if relevant to this artist's broader identity)
- [only include if the artist explicitly wants creative-identity notes to extend beyond audio]

## Last updated / source material reviewed
```

Build this incrementally — don't fabricate traits from a single song. State confidence ("observed across 4 tracks" vs. "only one data point so far") and update as more material comes in.

**Use case**: when songwriting or lyric work happens elsewhere in the pipeline, this profile is the check against generic-sounding AI output — "does this actually sound like this artist, or could it be anyone."

## Voice Vault — what to store per voice source

```
# Voice Vault — [artist/voice name]

## Source recordings
- [filename]: [date, register (low/mid/high/falsetto), style (soft/aggressive/melodic/conversational), spoken or sung, recording chain/mic if known]

## Fingerprint / hash
- [cryptographic hash or fingerprint per source file, for provenance verification later]

## Consent & scope
- Approved uses: [e.g. "any Bombay Studios release," "MEKONG project only," "internal demos only — not for public release"]
- Prohibited uses: [explicit — e.g. "not for cloning by third parties," "not for use outside Bombay Studios"]
- Consent given by: [artist name] on [date]
- Revocation / kill switch status: [active / revoked — if revoked, note date and that any downstream model must stop generating]

## Voice model versions (if a model exists)
- [version]: trained [date], source recordings used: [list], evaluated against real takes: [pass/fail/notes]

## Usage log
- [date] — [song/project] — [real take / generated take] — [which voice version if generated]
```

## Hard rules — these are not optional

- **Every entry into the usage log must state whether the take is a real human performance or a generated/synthesized one.** Never let the archive become ambiguous about what's real. This matters legally and creatively — don't skip it because it's tedious.
- **Never generate or reference a voice model without an explicit consent scope on file for that voice.** If asked to work with a voice that has no Vault entry or unclear consent, stop and ask rather than assuming permission.
- **Respect the kill switch.** If a voice's status is revoked, refuse to reference or generate from it and say why, even if the user forgot they revoked it — that's the point of the log.
- **This skill does not itself train or run a voice model** (that's the not-yet-built Voice Model Builder) — it stores the data and consent that a future model-training step would need, and it audits/logs whatever generation happens elsewhere.
- Don't let Identity work leak into Vault or vice versa when writing to the Song Blueprint — Identity informs creative choices; Vault informs what's legally/consensually usable.
