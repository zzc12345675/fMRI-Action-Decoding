# fMRI-Action-Decoding

Repository framework for documenting and organizing an fMRI action-decoding study.

**Current status:** The repository contains a directory scaffold and workflow documentation. Analysis scripts, data, and results have **not** been verified or uploaded as part of this restructuring.

## Start here

- [Code directory guide](code/README.md)
- [42-step analysis index](docs/analysis_workflow.md)
- [Code audit spreadsheet template](docs/code_inventory_template.csv)
- [Environment notes](env/README.md)

## Analysis branches

1. Data conversion and run/event checks
2. Preprocessing and quality control
3. Conventional **univariate GLM** (first-level, contrasts, group-level, multiple comparisons)
4. **Single-trial GLM** for trial-wise beta estimates
5. Searchlight decoding
6. Anatomically defined ROI decoding
7. RSA
8. Statistical tests, figure and table generation

**Do not treat folders as evidence that an analysis has been performed.** All script names, parameters, outputs, and numerical results must be checked against actual code and run logs before publication.

## Important branch distinction

Conventional univariate GLM and trial-wise MVPA use different image branches. The analysis notes identify smoothed, normalized images for the conventional GLM and unsmoothed subject-space images for MVPA. Verify exact image prefixes and file paths against the actual scripts before filling in reproducibility instructions.

Raw participant imaging data and potentially identifying metadata are not included here; sharing is subject to data authorization.
