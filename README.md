<div align="center">

# Aidin-Doosan Dexterous Manipulation

Public thesis progress on dexterous manipulation with a Doosan Arm and Aidin Hand.

</div>

<p align="center">
  <img src="assets/videos/video_real_pose_wide_xy.gif" alt="Aidin-Doosan manipulation rollout" width="85%">
</p>

<p align="center">
  <em>ACT policy rollout for simulated one-object pick-and-place task</em>
</p>

## Current Snapshot

This project studies imitation learning for dexterous manipulation with vision, robot state, and tactile sensing.

Current best reliable result:

- 3-camera ACT policy without tactile input
- 77 demonstrations
- 88% success on the training pose range
- 78% success on wider pose ranges

Tactile-summary policies have also been tested, but current ablations do not yet show a clear tactile benefit. Replacing tactile input with mean, zero, or noise gives similar performance in the latest comparison, suggesting that the policy is still relying mainly on vision and robot state.

## Tactile Sensor Layout

The simulated Aidin hand includes a minimal tactile layout for contact-aware manipulation:

- five fingertip tactile grids: `3 x 3` taxels per fingertip
- one palm tactile grid: `4 x 4` taxels
- total tactile dimension: `61` taxels

During rollout, tactile readings are summarized per contact region as total force, maximum taxel force, and active taxel count.

Example tactile readings during the demo collection:

```text
[EE t=0400] tactile
  baby_tip    sum=  0.822 max=  0.822 active= 1/9
  index_tip   sum= 27.585 max= 25.131 active= 2/9
  middle_tip  sum= 28.612 max= 28.612 active= 1/9
  ring_tip    sum=  0.000 max=  0.000 active= 0/9
  thumb_tip   sum=  9.288 max=  9.288 active= 1/9
  palm        sum=  0.000 max=  0.000 active= 0/16
  ```
This compact layout is intended to capture first contact, fingertip loading, and possible slip/recovery events without requiring dense full-hand tactile coverage.

## Research Question

Can tactile sensing improve the robustness of ACT-style imitation policies when contact information is needed for dexterous manipulation?

The current direction is to move beyond nominal open-loop demonstrations and collect contact-rich recovery behavior, such as slip, weak grasps, poor initial contact, and corrective actions.

## Method Direction

- Goal-conditioned ACT, where the policy receives compact object, target, or task-phase information in addition to images and robot state.
- Object-centric policy structure that separates perception, goal proposal, and low-level action generation.
- Tactile summaries and tactile-history features that encode contact onset, force changes, active taxels, and possible slip over time.
- Richer teleoperation demonstrations using Manus glove and Vive wrist tracking, especially trajectories that include contact recovery to get useful tactile feedback.
- Simulation-to-robot evaluation with controlled shifts in pose, object geometry, friction, and mass. 

## Media

```text
assets/
├── figures
├── images
└── videos
    └── video_real_pose_wide_xy.gif
