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

## Current Focus

- Demonstration collection
- Imitation learning for manipulation
- Tactile-aware policy experiments
- Simulation and robot-side validation

## Next Steps

- Add Manus glove and Vive tracker teleoperation for richer demonstration data.
- Collect recovery demonstrations where tactile/contact changes the action.
- Expand pose randomization and add object yaw variation.
- Move toward goal-conditioned ACT with object/bin/phase information.
- Compare vision-only, goal-conditioned, tactile-summary, and tactile-history policies.
- Evaluate under harder shifts such as object pose, friction, mass, and eventually unseen objects.

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
