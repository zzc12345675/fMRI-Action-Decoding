# 01 Preprocessing

Steps **5–10**: slice timing (33 slices in the notes), realignment, coregistration, segmentation, spatial normalization, and smoothing.

Keep image-branch choices explicit:
- Conventional GLM: normalized and smoothed image branch (per supplied analysis notes)
- Trial-wise MVPA: unsmoothed subject-space functional image branch (per supplied analysis notes)

Do not silently substitute one branch for another. Record actual SPM batch configuration, input prefixes, output prefixes, reference slice, reference image and processing order from the real scripts.
