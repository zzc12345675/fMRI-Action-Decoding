# Code organization / 代码目录

Files are grouped by **what the analysis does**, not by programming language. Keep original scripts intact until inputs, outputs and run logs are checked.

| Folder | Steps in [analysis index](../docs/analysis_workflow.md) | Intended code |
|---|---|---|
| `00_data_audit/` | 1–4 | DICOM→NIfTI, scan/run mapping, trial counts, acquisition parameters |
| `01_preprocessing/` | 5–10 | Slice timing, realignment, coregistration, segmentation, normalization, smoothing |
| `02_quality_control/` | 11–13 | Overlay checks, FD, spike detection and QC summaries |
| `03_univariate_glm/` | 14–17 and other **verified** univariate analyses | First-level model, contrasts, second-level, FWE |
| `04_trialwise_glm/` | 18–24 | HRF/design, nuisance regressors, diagnostics, beta labeling, feature tables |
| `05_searchlight/` | 25–31 | Masks, pilot, searchlight SVM, space matching, group permutations |
| `06_roi_decoding/` | 32–36 | Anatomical ROI masks, within/cross-format decoding, statistics, sample matching |
| `07_rsa/` | 37–41 | Mean patterns, RDMs, within/cross-format comparisons, trial matching |
| `08_statistics/` | Cross-cutting | Shared or group-level statistics not already kept with an analysis |
| `09_visualization/` | Cross-cutting | Scripts producing publication plots and tables |
| `10_utils/` | Cross-cutting | Reusable checked helpers |

The shared `08_statistics/` folder is **not** a substitute for specifying each analysis's correct permutation design and multiple-comparison family.

**Naming rule:** Only place a script in a folder once its actual function is understood. Do not infer successful execution from the existence of a script.
