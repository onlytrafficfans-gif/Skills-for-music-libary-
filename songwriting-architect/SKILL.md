---
name: songwriting-architect
description: Builds song concepts, hooks, verses, pre-choruses, bridges, and outros — developing a central idea into a full lyric with internal rhyme systems, melodic themes, and narrative progression while preserving the artist's own vocabulary, lived perspective, and boundaries. Use whenever the user wants help writing or rewriting a hook, verse, or full song, wants a concept developed into a structure, wants a lyric strengthened without losing their voice, or says a song "isn't hitting" and needs the actual writing improved rather than just mixed. Reads artist-identity-voice-vault's profile if one exists for this artist — never overrides their established vocabulary or subject boundaries with generic phrasing.
---

# Songwriting Architect

The job here is not "write something that sounds like a song" — it's "make this specific idea land harder, in this specific artist's voice." Generic-but-competent lyrics are a failure mode of this skill, not a safe default.

## Before writing anything

Check for an existing Artist Identity profile (from `artist-identity-voice-vault`). If one exists, read it and hold to it: recurring vocabulary, subjects the artist returns to, subjects/words they explicitly avoid, typical rhyme density, signature ad-libs. If none exists, ask 2-3 quick questions rather than guessing — genre/reference, the one thing the song needs to say, and any words/topics that are off-limits. Don't over-interview; get just enough to write something specific instead of generic.

## Concept before lines

1. **Central idea** — one sentence. If the user can't state it in one sentence, that's diagnostic — help them find it before writing lyrics, because a fuzzy concept produces a fuzzy hook no matter how clever the wordplay is.
2. **Emotional turn** — what does the song do to the listener between the first line and the last? A song that ends in the same emotional place it started rarely lands.
3. **Point of view** — first person confessional, third person narrative, direct address — pick deliberately, don't default.

## Structure development

Work section by section, each with a clear job:

- **Hook/chorus** — the most repeatable, most memorable line(s). Should work with almost no context (test: does it land if someone hears only the hook, out of context?). Write 2-3 options labeled by trade-off (e.g. "more direct," "more image-driven," "denser rhyme, less immediate") rather than presenting one and calling it done.
- **Verses** — must each add new information or a new angle; a verse that just restates the hook in different words is dead weight. Track what's been said so verse 2 doesn't repeat verse 1's job.
- **Pre-chorus** (if used) — builds tension/expectation into the hook; shouldn't resolve before the hook does.
- **Bridge** — earns its place by doing something the rest of the song hasn't (new perspective, admission, turn, direct address) — a bridge that's just a quieter verse isn't pulling weight.
- **Outro** — lands the emotional turn; doesn't have to just fade the hook out if the song has somewhere to go.

## Craft checks before presenting a draft

- **Rhyme and stress** — does the natural word stress fall where the beat/melody wants it, or does a clever rhyme force an awkward stress? Check this line by line, not just "does it rhyme."
- **Concrete over generic** — flag and replace vague emotional language ("I feel so alive," "chasing my dreams") with specific images and details that only this artist, in this situation, would say. This is the single biggest lever for making a lyric feel real instead of AI-generated.
- **The artist would actually say this** — read every line back against the Identity profile's vocabulary and voice. If a line sounds like "a songwriter" wrote it rather than this specific person, rewrite it.
- **Setup-to-payoff ratio on the hook** — does the pre-hook material earn the hook, or does the hook arrive with no buildup?

## Output format

```
## Songwriting Draft — [song/section]

### Concept
[one-sentence core idea, emotional turn, POV]

### [Section name]
[lyric]
— rhyme/stress notes if relevant
— alternate options if this line is subjective, labeled by trade-off

### Craft flags
[any generic phrasing caught and replaced, any stress/rhyme conflicts, any line that doesn't match the artist's established voice]

### Open questions for the artist
[anything genuinely subjective that needs their call, not yours]
```

Write the finished lyric and structure into the Song Blueprint's "Lyric & performance" section if `musicos-producer` is orchestrating. Hand off flow/pocket-specific fitting to `flow-cadence-intelligence` rather than guessing at syllable-to-beat fit yourself if precise timing matters.

## Rules

- Never invent a biographical detail or claim about the artist's life to make a line "hit harder" — ask what's true, or keep it appropriately vague.
- Multiple genuinely different options on subjective lines beats one confident answer — the user should feel like they're choosing, not approving.
- Don't chase "commercial" at the cost of specificity — the report that led to this skill is explicit that formulaic ≠ quality. A distinctive line that's slightly less "radio" is usually the better call; say so if you think it, don't silently pick the safe option.
