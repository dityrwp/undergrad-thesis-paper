# Official Makalah

The paper is rebuilt from the final V2 thesis state. It intentionally excludes
the obsolete A12/V1 results and experiment chronology.

## Build

```bash
cd makalah
latexmk -pdf main.tex
```

Output: `main.pdf`

## Result Contract

- Primary test split: `dataset_mast_pilot/test_ungated`
- Detector metric: all-point AP with 1.0 m center matching
- Operating threshold: 0.60, selected on validation
- Task metric: unconditional `R@0.25`
- Control evaluation: offline one-shot IK replay on physically completable scenes

Primary evidence:

- `WRITING_PC_V2_RESULTS_HANDOFF_2026-06-13.md`
- `docs/evidence/BAB5_V2_IK_REPLAY_WRITER_HANDOFF_2026-06-15.md`
- `v2_fused_robustness_2026-06-12.json`
- `v2_distractor_fp_2026-06-12.json`
- `perception_ik_scene_task_replay_v2_only_2026-06-15.json`
- `makalah/ik_replay_paired_statistics.json`

The paper claims task-oriented system integration and empirical modality
characterization. It does not claim a new general-purpose fusion architecture,
real-world validation, full oriented 3D box regression, or closed-loop physical
excavation.
