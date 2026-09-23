# TARES 1M Jupyter Experiment Notebooks

This repository contains the **original dual-cell experimental notebooks**
used during development, adapted to the paper-level **1M update budget**.

## Notebooks

- `TARES_Supported12_3Seed_1M_DualCell.ipynb`
  - matched control / TARES experiment pipeline
  - 12 supported tasks
  - 3 training seeds
  - 1,000,000 gradient updates

- `TARES_Focused_Ablations_3Task_3Seed_1M_DualCell.ipynb`
  - focused TARES component ablations
  - AntSoccer-Arena, Scene, and Pen-Cloned
  - 3 training seeds
  - 1,000,000 gradient updates

## 1M schedule

The 300K schedule is scaled proportionally to the 1M budget:

- calibration: 100K--200K updates (10%--20%)
- auxiliary intervention: 200K--733,333 updates (20%--73.333%)
- primary-objective-only phase: 733,333--1M updates

The probe bank size and all non-time hyperparameters are unchanged.

## Evaluation

Evaluation occurs every 250K updates, so the late-window summary uses:

- 250K
- 500K
- 750K
- 1M

The final evaluation remains at 1M with the notebook's original final-episode
setting.

## Notes

The internal development method identifiers are intentionally preserved so the
1M notebooks remain directly traceable to the original experimental code.
Only budget-, schedule-, evaluation-, and stale budget-comment settings were
adapted for 1M use. Notebook outputs were cleared for a clean public release.

Run each notebook with **Run All** on a CUDA-capable machine.
