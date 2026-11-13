# 42-step fMRI analysis index

This is an **index of the workflow described by the researcher**, not proof that corresponding scripts, output files, parameter values, or QC records are available. Audit each item against code and run logs.

| Step | Operation | Intended location |
|---:|---|---|
| 1 | Convert scanner data to NIfTI | `code/00_data_audit/` |
| 2 | Verify acquisition versus analysis run mapping | `code/00_data_audit/` |
| 3 | Verify scan and trial counts | `code/00_data_audit/` |
| 4 | Read TR, slice count and acquisition settings | `code/00_data_audit/` |
| 5 | Slice timing correction | `code/01_preprocessing/` |
| 6 | Realignment and six motion parameters | `code/01_preprocessing/` |
| 7 | T1-functional coregistration | `code/01_preprocessing/` |
| 8 | T1 segmentation and deformation fields | `code/01_preprocessing/` |
| 9 | Spatial normalization | `code/01_preprocessing/` |
| 10 | Smoothing of conventional GLM branch | `code/01_preprocessing/` |
| 11 | Inspect image registration and spatial overlap | `code/02_quality_control/` |
| 12 | Compute framewise displacement (FD) | `code/02_quality_control/` |
| 13 | Flag FD > 0.5 mm and construct spike regressors | `code/02_quality_control/`, `code/04_trialwise_glm/` |
| 14 | Specify condition-level univariate GLM | `code/03_univariate_glm/01_first_level/` |
| 15 | Define `All_actions > baseline` contrast | `code/03_univariate_glm/02_contrasts/` |
| 16 | Conduct 18-participant group one-sample t-test | `code/03_univariate_glm/03_group_level/` |
| 17 | Apply/record FWE-corrected inference | `code/03_univariate_glm/04_inference_fwe/` |
| 18 | Specify individual-trial regressors | `code/04_trialwise_glm/` |
| 19 | Model delayed BOLD response with HRF | `code/04_trialwise_glm/` |
| 20 | Add motion, spike, run-level nuisance regressors | `code/04_trialwise_glm/` |
| 21 | Set high-pass filtering and AR(1) | `code/04_trialwise_glm/` |
| 22 | Inspect design rank and VIF | `code/04_trialwise_glm/` |
| 23 | Match beta files to trial labels | `code/04_trialwise_glm/` |
| 24 | Form trial × voxel feature matrices | `code/04_trialwise_glm/` |
| 25 | Specify searchlight center/voxel masks separately | `code/05_searchlight/` |
| 26 | Run pilot spherical ROI decoding | `code/05_searchlight/` |
| 27 | Fit StandardScaler on training fold only | `code/05_searchlight/` |
| 28 | Train/test linear SVM across runs | `code/05_searchlight/` |
| 29 | Run 6 mm moving searchlight | `code/05_searchlight/` |
| 30 | Transform and align subject maps in common space | `code/05_searchlight/` |
| 31 | Implement documented block-aware permutations and correction | `code/05_searchlight/` |
| 32 | Define four ROIs using anatomical atlas | `code/06_roi_decoding/` |
| 33 | Decode within natural and point-light formats | `code/06_roi_decoding/` |
| 34 | Decode natural→point-light and reverse | `code/06_roi_decoding/` |
| 35 | Test 16 ROI-task comparisons with correction | `code/06_roi_decoding/` |
| 36 | Match training sample counts across formats | `code/06_roi_decoding/` |
| 37 | Compute run-wise, ROI-wise average action patterns | `code/07_rsa/` |
| 38 | Create four-action RDMs (six distinct pairs) | `code/07_rsa/` |
| 39 | Compare RDMs between runs of same format | `code/07_rsa/` |
| 40 | Compare format-average RDMs using Spearman | `code/07_rsa/` |
| 41 | Match trial counts using repeated complete-block sampling | `code/07_rsa/` |
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
