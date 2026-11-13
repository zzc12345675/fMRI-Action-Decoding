# 05 Searchlight

Steps **25–31**: gray-matter search centers versus valid GLM voxels, small-sphere pilot, train-only StandardScaler, run-wise linear SVM, 6 mm moving searchlight, group-space common coverage, block-aware permutation and max-statistic correction.

**GLM `mask.nii` is not inherently a gray-matter mask.** Document masks independently.

Notes refer to a common tested searchlight region of **5,064 centers**; verify subject-to-group transforms and coverage thresholds against the actual logs before publishing results. The precise block permutation rule is not established by the supplied summary.
