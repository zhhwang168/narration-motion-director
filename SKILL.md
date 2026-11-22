---
name: narration-motion-director
description: Plan and refine narration-driven tutorial and explainer animations with semantic shot timing, visible actions, readable titles, presenter placement, and sound cues. Use with an existing video renderer such as Remotion or HyperFrames when narration and graphics must tell the same story, especially when a video feels like repetitive slides.
---

# Narration Motion Director

Turn the spoken explanation into visible actions and consequences. This skill supplies direction and an editable cue plan; use the existing renderer's skill for implementation, preview, and export. A request to create a skill or answer a question does not authorize editing the user's video.

## Establish the source of truth

Inspect the current project and supplied narration, script, subtitle timing, reference clips, and identity corrections. Preserve user edits. Match the actual recording before planning cuts; a script alone may differ from the spoken take.

- Prefer reviewed timing from the actual recording. Subtitle cues support phrase timing, not necessarily individual words. Use alignment or transcription when timing is absent; mark uncertain anchors rather than inventing precise word times.
- Keep source media and source subtitles intact. Put corrections in a derived caption track and record them. Changing a displayed name does not change what the recording says.
- Read [timing-and-review.md](references/timing-and-review.md) for timing provenance, a cue-plan schema, and targeted revision checks.

## Direct the picture from the meaning

Identify the clause's action, object, and outcome. Write the visible transformation before choosing an animation preset: attach notes → open the note → mark a fact; connect a microphone → move its level → listen to the test.

For a video build, save a compact shot/cue plan inside the user's project. Anchor each shot to an actual narration cue, identify what changes, and specify the final state the viewer must understand. Planning is working material, not a new approval gate when execution is already authorized.

- Advance on semantic changes. Never select the current graphic, title, or highlight by caption index modulo a list, by a looping timer, or by an arbitrary fixed scene duration.
- A paragraph need not equal a scene. A scene may contain several actions; a new clause may simply update one existing object. Keep visual continuity where it helps understanding.
- Headlines explain the idea currently being spoken. Do not announce a later topic while the current explanation continues. Hold an accurate title across several related cues instead of replacing it on every subtitle.
- Motion must demonstrate an operation, direct attention, or reveal a result. Let key text settle and provide reading time. Continuous camera drift, repeated card entrances, and decorative motion are optional style choices, not substitutes for progress.
- Read [visual-recipes.md](references/visual-recipes.md) for semantic scene choices and a worked timing example. Use relevant recipes; do not impose a fixed number of scenes or styles.

## Work with the installed toolkit

Keep the current renderer and project format unless there is a concrete reason to change them. Do not rebuild a Remotion project in HyperFrames just to apply this skill.

- **Remotion:** read the available `remotion-best-practices` skill and the relevant references. Use frame-driven rendering and the project's fps. Map the cue plan to compositions/sequences and stable asset paths; derive frames consistently from authoritative cue times.
- **HyperFrames:** read `hyperframes`; use `hyperframes-registry` before hand-building a named effect. Map the same cue plan to its supported timeline/clip contract. Keep playback and export consistent with renderer rules.
- **Video ShotCraft:** when a named recipe is requested and available, read the actual recipe and inspect its example before adapting it. A keyword is a lookup key, not proof that the showcased effect has been reproduced. Preserve its useful motion structure while adapting content, duration, and layout.
- **3D / Motion / media:** load the relevant available skill only for a scene that needs it. Use 3D for spatial explanations or a meaningful reveal; use real footage or screen captures for actual operations when available.
- **FFmpeg:** use for media preparation, audio handling, and delivery as appropriate; keep final timing consistent with the cue plan. Follow the renderer's prescribed export workflow.

If a needed skill is unavailable, explain the specific limitation and use existing project capabilities where possible. Do not install dependencies, invoke paid generators, or upload user media solely because a reference prompt mentions them.

## Presenter, type, and sound

Reserve separate regions for narration captions, explanatory graphics, and the presenter. Inspect the finished layout with the actual presenter crop. Use shot-specific placement or temporary presenter removal when content needs the space; follow the user's preference.

For sequential titles, lay out the full phrase at its final dimensions, reserve spaces and glyph widths, and animate characters or words within those positions. Preserve the baseline, wrapping, and alignment throughout the reveal. Separate narration captions from short emphasis text; avoid three competing text layers saying the same thing.

Place sound cues on visible actions in the cue plan, not randomly on every subtitle or letter. Preserve speech intelligibility, avoid clipping, and inspect the mix. Music, synthetic sounds, and sourced effects must respect the user's scope and renderer workflow. Explain any external source or service cost before depending on it.

## Refine and deliver

For feedback, locate the time/shot, restate the observable problem, change the relevant layer, then inspect the changed interval and its adjacent cut. Preserve working caption/audio timing unless the requested change requires retiming. For global timing errors, inspect all affected boundaries.

Preview before an expensive full export where practical; follow the renderer's approval rules and existing user authorization. Inspect motion as a short clip, not only a still. Sample opening, representative middle shots, densest text, presenter overlap, final frame, and revised transitions. Report checks actually performed and uncertainties that remain; avoid claiming a full playback review from sampled frames.

Deliver requested video files, editable source, and the cue plan using the established project/output folders. Keep full exports distinct from review clips and retain the last approved version.

## Project profiles

Use the current project's identity, language, format and presenter preferences. Do not impose one creator's identity on another project. For Henry's established series, the optional [Tube U profile](references/tube-u-profile.md) preserves the fixed greeting and presentation conventions; read it only when that profile applies.

## Reference provenance

Inspired by the planning and screenshot-feedback ideas in Tested for Creators' [Cartoon Shorts Prompt Pack](https://claude.ai/artifact/ESd95hWpxpQsfR8jawt33e), identified in the project provenance records. This skill is independently written for the user's workflow; it does not redistribute those prompts. The source page's temporary-free label is not an open-source license. Do not inherit its requirements for a particular model, vertical cartoon style, continuously moving camera, heuristic word timing, or browser screen-recording export.
