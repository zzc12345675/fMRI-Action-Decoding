# Code

Keep the three major stages easy to navigate:

1. `01_preprocessing/` — steps 1–13, including data/run checks, preprocessing and QC
2. `02_univariate_analysis/` — steps 14–17 and other verified univariate work; its contrasts, group statistics and FWE tests belong here
3. `03_multivariate_analysis/` — steps 18–41: single-trial GLM, Searchlight, ROI decoding, RSA, and statistical tests for **each** analysis

No standalone `statistics/` folder: statistical analysis should stay with the method and results it tests.

Use actual code and verified outputs to decide script names and any subfolders needed later. Do not create unverified analyses simply to fill the structure.
