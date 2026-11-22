# Narration Motion Director

A reusable Codex skill for turning narration into visible actions, timed shots and specific animation revisions.

Developed by **Henry / Tube U with Codex**, through real tutorial production. The workflow takes inspiration from credited reference material and is customized for narration-led animation. See [ATTRIBUTION.md](ATTRIBUTION.md).

## What it helps with

- Choose an action that explains the spoken idea.
- Build an editable cue plan from actual narration timing.
- Keep titles, character actions and sound cues on the same story beat.
- Turn feedback into a specific change, then inspect that interval.
- Preserve working source media, timing and project structure.

For example: the cat looks at a fish, reaches, makes contact, pulls, reacts to being noticed, then hides it. Each change has a purpose. A request such as “hold the surprised reaction before hiding the fish” becomes a checkable timing revision.

## Use it

Install this repository as a skill folder in your Codex skills directory. For a standard installation, the folder layout should be:

```text
~/.codex/skills/narration-motion-director/SKILL.md
~/.codex/skills/narration-motion-director/agents/openai.yaml
~/.codex/skills/narration-motion-director/references/...
```

You can clone it directly into that folder:

```sh
git clone https://github.com/zhhwang168/narration-motion-director.git ~/.codex/skills/narration-motion-director
```

Start a new Codex chat after installation, then try:

```text
Use $narration-motion-director with my existing HyperFrames project.
Read the narration and current project first.
Plan the visible actions and make a short playable preview.
Keep the character and drawing style unchanged.
Make the cat look at the fish before its paw moves.
Keep the fish still until the paw touches it.
```

Or use it to review a specific problem:

```text
Use $narration-motion-director to review the contact and pull at 4–6 seconds.
Explain the visible defect, change the relevant layer, and inspect the revised interval.
Preserve the existing narration timing.
```

## Requirements and scope

This is a direction skill, not a renderer, image model, voice service or video generator. Use an existing renderer and its skill, such as HyperFrames or Remotion, for preview and export. Those tools must be available separately.

The skill preserves the project's format and does not migrate renderers just to apply its guidance. It distinguishes measured recording timing from provisional estimates and does not claim that a screenshot proves smooth motion or that an audio measurement proves a listening review.

## Files

- [SKILL.md](SKILL.md): core workflow.
- [Timing and review](references/timing-and-review.md): cue-plan format, timing provenance and targeted checks.
- [Visual recipes](references/visual-recipes.md): examples of visible transformations and scene choices.
- [Optional Tube U profile](references/tube-u-profile.md): Henry's established greeting and project conventions; not imposed on other creators.
- [Example cue plan](examples/cat-and-fish-cue-plan.json): illustrative actions, not measured timestamps from your recording.

## License and attribution

The custom files in this repository are provided under the [MIT License](LICENSE). Linked reference materials and external rendering tools retain their own terms. The third-party prompt pack, private recordings and local project files are not included here.

The workflow has been used in a local HyperFrames/SVG tutorial project. Other renderer integrations are guidance, not a claim that every environment has been tested.
