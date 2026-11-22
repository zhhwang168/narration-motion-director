# Timing, cue plans, and review

## Timing hierarchy

1. Actual narration plus manually reviewed timestamps or verified alignment.
2. Recording-derived subtitle cues checked around the relevant action.
3. ASR/forced alignment with names and terminology reviewed against the audio and script.
4. Silence detection and text-length estimates for a provisional animatic only.

Silence detection measures acoustic pauses; it does not recognize words. A status such as `word timing: measured` must not imply recognition or forced alignment when words were only distributed proportionally. If captions conflict with the audible take, inspect the recording and fix derived timing. A forced aligner also needs checking for omitted/added phrases.

Keep an audio offset explicit when trimming or inserting an introduction. Shift the affected voice-linked cues together. Do not change a timeline boundary simply to match a nominal chapter duration.

## Editable cue plan

Use a small JSON table, CSV, or equivalent native project structure. The fields below are a useful example, not a mandatory file format:

```json
{
  "fps": 30,
  "audio": "original-narration.mp4",
  "identity": {"presenter": "Henry", "channel": "Tube U"},
  "shots": [{
    "id": "outline-before-script",
    "startFrame": 2496,
    "endFrame": 2794,
    "timingSource": "reviewed narration subtitle cues",
    "spokenAnchor": "I'll also tell it what happens next",
    "headline": "Outline first. Script after review.",
    "visual": "A draft outline is reviewed, then becomes a script",
    "events": [
      {"frame": 2496, "action": "Introduce the outline-to-script workflow"},
      {"frame": 2570, "action": "Reveal OUTLINE, highlight REVIEW, then unlock SCRIPT"},
      {"frame": 2712, "action": "Hold at the review stopping point"}
    ],
    "presenter": "reserved-right",
    "sound": [],
    "finalState": "Script follows outline approval"
  }]
}
```

These example timestamps belong to one recording and must not be reused in another take. Event times and entry duration are distinct: use stable cue anchors, then choose short readable transitions around them. Keep events inside their shot; if a result needs a hold, reserve that hold before the next shot.

## High-value checks

- Follow a sample of spoken clauses into the plan: does each action actually show what the speaker explains?
- Check every new topic boundary against nearby audio. A subtitle line may end mid-sentence; a chapter may begin inside one cue.
- Inspect a short clip across a change: start state, action, outcome, hold. A correct end-frame screenshot cannot prove smooth motion.
- Check title/caption/presenter collisions with the actual font and presenter media. Typography must fit at the longest title and during partial reveals.
- Seek to shots out of order. Identical frame/time should produce identical output. Avoid cumulative state, wall-clock animation, unseeded randomness, and loading-dependent visuals.
- Verify export duration against the actual voice track, first/last audible words, and inserted offsets. Avoid silently cutting the narration's ending.
- For sound, listen to an effect-heavy interval against the voice. Check levels/clipping and overlapping effects. Do not claim audio checks from metadata alone.

## Screenshot feedback

Turn feedback into: **time or shot → visible defect → desired result → affected layer**. If the timestamp is missing, use the screenshot's text and objects to locate the scene. Ask only if multiple matches prevent a safe targeted edit.

Examples:

- `01:25 / outline`: title announces source-checking too early → keep outline-first headline until source material is actually introduced → title and shot boundary.
- `title reveal`: letters move each other's positions → reserve final text layout and animate glyphs within it → typography.
- `whole chapter`: cards alternate without a relationship to speech → replace cycle with explicit semantic events → cue plan and graphics.

Check the revised interval plus the preceding and following transition. Do not restart every layer, replace the audio, or rebuild the whole project for a small visual correction.
