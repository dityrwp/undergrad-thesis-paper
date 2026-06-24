# Official Makalah

The paper is rebuilt from the final thesis state. 

## Result contract

- Primary test split: held-out `test_ungated`, 150 frames.
- Detection metric: all-point AP, 1.0 m center-matching radius.
- Operating threshold: 0.60 (selected on validation, not on the test split).
- Task metric: unconditional `R@0.25` (missed objects penalized, not just mismatched ones).
- Control evaluation: offline inverse-kinematics replay on kinematically eligible scenes,
  plus one representative perception-conditioned Gazebo execution.

Headline numbers: the fused model reaches 0.913 all-point mAP, 0.050 m mATE, 0.084 m P90
ATE, and 0.841 R@0.25. Relative to a LiDAR-only model trained on identical data, fusion
raises mAP from 0.871 to 0.913 and R@0.25 from 0.796 to 0.841, while clean metric
localization is essentially unchanged — fusion's contribution is target coverage and
rejection of target-like distractors, not raw localization precision. In IK replay, fused
perception supplies a usable rubble–bin pair in 75.7% of eligible scenes (56/74) versus
67.6% (50/74) for LiDAR-only.

The paper claims task-oriented system integration and an empirical characterization of
modality roles. It does not claim a new general-purpose fusion architecture, real-world
validation, full oriented 3D box regression, or closed-loop physical excavation.

## Build

```bash
latexmk -pdf main.tex
```

Output: `main.pdf`. Figures live in `figures/`; references in `references.bib`
(IEEEtran style, `IEEEtran.cls` vendored alongside).

