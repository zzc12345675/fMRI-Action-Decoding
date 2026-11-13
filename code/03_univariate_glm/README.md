# 03 Conventional univariate GLM

Steps **14–17**, plus other univariate analyses **only after verification**.

This branch must remain separate from single-trial GLM and MVPA. Known analysis descriptions mention:
- Condition-level first-level GLM for action responses
- An `All_actions > baseline` contrast
- Group one-sample t-test across 18 participants
- Correction for testing many voxels (FWE)

These are workflow descriptions, **not a claim that matching scripts or results have been uploaded**.

Subfolders:
- `01_first_level/`: task design, regressors, first-level estimates
- `02_contrasts/`: contrast definitions and first-level con images
- `03_group_level/`: second-level model and participant-level inputs
- `04_inference_fwe/`: thresholds, FWE settings, resulting statistical tables/figures
- `05_additional_verified/`: additional univariate work after inspecting the actual code

Never copy unverified contrasts or thresholds from a different class project or reference paper.
