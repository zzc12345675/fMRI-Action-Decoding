# 42-step fMRI analysis index

This is an **index of the workflow described by the researcher**, not proof that corresponding scripts, output files, parameter values, or QC records are available. Audit each item against code and run logs.

| Step | Operation | Intended location |
|---:|---|---|
| 1 | Convert scanner data to NIfTI | `code/01_preprocessing/` |
| 2 | Verify acquisition versus analysis run mapping | `code/01_preprocessing/` |
| 3 | Verify scan and trial counts | `code/01_preprocessing/` |
| 4 | Read TR, slice count and acquisition settings | `code/01_preprocessing/` |
| 5 | Slice timing correction | `code/01_preprocessing/` |
| 6 | Realignment and six motion parameters | `code/01_preprocessing/` |
| 7 | T1-functional coregistration | `code/01_preprocessing/` |
| 8 | T1 segmentation and deformation fields | `code/01_preprocessing/` |
| 9 | Spatial normalization | `code/01_preprocessing/` |
| 10 | Smoothing of conventional GLM branch | `code/01_preprocessing/` |
| 11 | Inspect image registration and spatial overlap | `code/01_preprocessing/` |
| 12 | Compute framewise displacement (FD) | `code/01_preprocessing/` |
| 13 | Flag FD > 0.5 mm and construct spike regressors | `code/01_preprocessing/`, `code/03_multivariate_analysis/` |
| 14 | Specify condition-level univariate GLM | `code/02_univariate_analysis/` |
| 15 | Define `All_actions > baseline` contrast | `code/02_univariate_analysis/` |
| 16 | Conduct 18-participant group one-sample t-test | `code/02_univariate_analysis/` |
| 17 | Apply/record FWE-corrected inference | `code/02_univariate_analysis/` |
| 18 | Specify individual-trial regressors | `code/03_multivariate_analysis/` |
| 19 | Model delayed BOLD response with HRF | `code/03_multivariate_analysis/` |
| 20 | Add motion, spike, run-level nuisance regressors | `code/03_multivariate_analysis/` |
| 21 | Set high-pass filtering and AR(1) | `code/03_multivariate_analysis/` |
| 22 | Inspect design rank and VIF | `code/03_multivariate_analysis/` |
| 23 | Match beta files to trial labels | `code/03_multivariate_analysis/` |
| 24 | Form trial × voxel feature matrices | `code/03_multivariate_analysis/` |
| 25 | Specify searchlight center/voxel masks separately | `code/03_multivariate_analysis/` |
| 26 | Run pilot spherical ROI decoding | `code/03_multivariate_analysis/` |
| 27 | Fit StandardScaler on training fold only | `code/03_multivariate_analysis/` |
| 28 | Train/test linear SVM across runs | `code/03_multivariate_analysis/` |
| 29 | Run 6 mm moving searchlight | `code/03_multivariate_analysis/` |
| 30 | Transform and align subject maps in common space | `code/03_multivariate_analysis/` |
| 31 | Implement documented block-aware permutations and correction | `code/03_multivariate_analysis/` |
| 32 | Define four ROIs using anatomical atlas | `code/03_multivariate_analysis/` |
| 33 | Decode within natural and point-light formats | `code/03_multivariate_analysis/` |
| 34 | Decode natural→point-light and reverse | `code/03_multivariate_analysis/` |
| 35 | Test 16 ROI-task comparisons with correction | `code/03_multivariate_analysis/` |
| 36 | Match training sample counts across formats | `code/03_multivariate_analysis/` |
| 37 | Compute run-wise, ROI-wise average action patterns | `code/03_multivariate_analysis/` |
| 38 | Create four-action RDMs (six distinct pairs) | `code/03_multivariate_analysis/` |
| 39 | Compare RDMs between runs of same format | `code/03_multivariate_analysis/` |
| 40 | Compare format-average RDMs using Spearman | `code/03_multivariate_analysis/` |
| 41 | Match trial counts using repeated complete-block sampling | `code/03_multivariate_analysis/` |
| 42 | Integrate MVPA, RSA, univariate results and limitations | `docs/`, `results/` |

## Critical distinctions

- Original experiment run numbering and analysis run numbering must be explicitly mapped; do not silently rename or reorder event labels.
- Conventional GLM and trial-wise GLM are different models. The latter supplies classification samples.
- Recorded no-spike GLM rank/VIF checks must not be relabeled as spike-inclusive checks.
- GM center mask ≠ GLM valid-voxel mask.
- Anatomical ROIs must not be described as chosen from searchlight significance.
- Cross-format decoding evidence does not require cross-format RDM ranks to be stable.
- More univariate analyses may exist. Add their actual scripts and corresponding index rows **only when verified**.

## Code audit status

All entries: **Pending script-by-script verification**. This page intentionally contains no unsupported file paths, results or p-values.
