# fMRI-Action-Decoding

fMRI action-decoding analysis repository.

## Code structure

- [01_preprocessing](code/01_preprocessing/) — Data checks, SPM12 preprocessing, motion and image quality control
- [02_univariate_analysis](code/02_univariate_analysis/) — Conventional condition-level GLM, contrasts, group analysis, statistical inference
- [03_multivariate_analysis](code/03_multivariate_analysis/) — Trial-wise beta estimation, Searchlight, ROI decoding, RSA, and their statistical tests

Other directories: `env/` (software environment), `results/` (approved figures, tables and QC summaries), `docs/` (workflow and code inventory).

See [the 42-step workflow index](docs/analysis_workflow.md).

> This repository currently contains a structure and documentation only; analysis scripts and outputs must be checked against their real run logs before being uploaded. Raw participant imaging data must not be posted without permission.
