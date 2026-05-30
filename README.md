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
