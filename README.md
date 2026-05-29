<div align="center">

# Aidin-Doosan Dexterous Manipulation

Public thesis progress on dexterous manipulation with a Doosan arm and Aidin hand.

</div>

<p align="center">
  <img src="assets/videos/video_real_pose_wide_xy.gif" alt="Aidin-Doosan manipulation rollout" width="85%">
</p>

<p align="center">
  <em>ACT inference rollout trained from mostly open-loop scripted demonstrations.</em>
</p>

## Current Snapshot

- Best saved one-object simulation result: 100% success across train, wide-XY, and very-wide-XY evaluations.
- Strong vision/qpos baseline: 88% success on the train pose distribution and 78% on wider pose tests.
- Tactile-summary observations coincide with the best saved result, but ablations with mean/zero/noise tactile are also strong. This means tactile is not yet proven to be the causal reason for success.
- Current takeaway: tactile should become more useful with contact-rich recovery demonstrations, wider object/physics randomization, and policies that must react to slip or poor contact.

Loss curves exist for the saved runs, but exact best validation-loss values are not yet logged in a clean public format.

## Overview

This repository shares selected public progress from my thesis work on robot manipulation with a dexterous hand. The private development repository contains the code, datasets, experiment scripts, and implementation notes.

## Research Themes

- Learning dexterous pick-and-place behavior from demonstration data.
- Studying when tactile observations provide useful information beyond vision and robot state.
- Improving generalization across object pose, contact conditions, and task variation.
- Using simulation as a controlled testbed before broader robot-side data collection.

## Possible Directions

- Goal-conditioned policies that receive compact object, target, or task-phase information instead of inferring the entire task from pixels alone.
- Object-centric policy interfaces that separate perception, goal proposal, and low-level action generation.
- Richer teleoperation data using hand and wrist tracking, especially demonstrations that include contact recovery rather than only nominal open-loop motion.
- Tactile-history representations that capture contact onset, force changes, and possible slip over time.
- Teacher-student style training where privileged simulation information helps generate supervision, while the deployed policy uses only available robot observations.
- Evaluation under wider pose randomization and physical shifts such as friction, mass, and object geometry changes.

## Media

Photos, rollout videos, and learning curves will be added here as the project develops.

```text
assets/
├── figures
├── images
└── videos
    └── video_real_pose_wide_xy.gif
```

## Notes

This repository does not include source code, private notes, raw datasets, checkpoints, or calibration files.
