# 04 Trial-wise GLM

Steps **18–24**: separate trial regressors and HRF, motion/spike/run nuisance regressors, high-pass/AR(1), rank/VIF diagnostics, mapping beta maps to labels, and constructing trial × voxel feature matrices.

The provided notes describe **384 action beta maps per participant**. Record which model version (spike versus no-spike) was used to generate *each* diagnostic. In particular, do not attribute rank/VIF checks from a no-spike model to a spike-inclusive model without re-running them.

Document how `trial_labels.csv` aligns with beta image order.
