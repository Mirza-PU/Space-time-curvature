Data-Driven Discovery of Minimal Intrinsic Curvature Dependencies in Spacetime Geometry

This repository contains the datasets, machine-learning code, analysis scripts, and visualization resources associated with the study:

«Data-Driven Discovery of Minimal Intrinsic Curvature Dependencies in Spacetime Geometry»

The project investigates whether a compact subset of physically meaningful intrinsic geometric descriptors can preserve the information required to distinguish different spacetime geometries.

Overview

The study starts with 42 candidate geometric and physical descriptors constructed from curvature invariants, electromagnetic quantities, rotation-related terms, cosmological quantities, and their transformations/couplings.

A systematic machine-learning workflow based on XGBoost feature importance and sequential feature reduction is used to investigate descriptor redundancy and identify a compact representation.

The analysis considers eight spacetime families:

1. Minkowski
2. Schwarzschild
3. Kerr
4. Reissner–Nordström
5. Kerr–Newman
6. de Sitter
7. Anti-de Sitter
8. FLRW

The dataset contains 2,000,000 synthetic samples, with 250,000 samples generated for each spacetime family.

Main Finding

Starting from 42 candidate descriptors, the analysis identified the following eight-feature representation:

abs_K
R
r2_R
Parity2
Rotation2
EM2
log_R
Cosmological

Using these eight descriptors, the final XGBoost classifier achieved:

Metric| Result
Test Accuracy| 0.999175
Macro-F1| 0.999175
Precision| 0.999176
Recall| 0.999175

Multi-Seed Robustness

To examine sensitivity to random data splitting, the final eight-feature representation was evaluated across 10 random seeds:

42, 52, 62, 72, 82,
92, 102, 112, 122, 132

The resulting test performance was:

Metric| Mean ± SD
Accuracy| 0.999189 ± 0.000062
Macro-F1| 0.999189 ± 0.000062
Precision| 0.999190 ± 0.000062
Recall| 0.999189 ± 0.000062

Test accuracy ranged from:

0.999095 – 0.999285

with a 95% confidence interval for the mean accuracy of approximately:

[0.999150, 0.999228]

Important Scientific Scope

The eight descriptors identified here should not be interpreted as a universal or mathematically complete set of spacetime invariants.

Rather, the result represents an empirical minimal representation within the investigated descriptor space and the eight selected spacetime families.

The study therefore focuses on:

- descriptor redundancy,
- data-driven feature reduction,
- intrinsic geometric representation,
- classification consistency,
- robustness across random splits.

It does not attempt to replace Einstein's field equations or perform numerical relativity simulations.

The spacetime samples are constructed from established analytical spacetime geometries and their associated geometric quantities.

Methodology

The main workflow is:

Analytical Spacetime Families
          ↓
Synthetic Dataset Generation
          ↓
42 Candidate Descriptors
          ↓
Train / Validation / Test Splits
          ↓
XGBoost Feature Importance
          ↓
Sequential Top-K Feature Analysis
          ↓
Minimal 8-Feature Representation
          ↓
Independent Test Evaluation
          ↓
10-Seed Robustness Analysis
          ↓
Geometric Visualization

Dataset

Dataset size

Total samples:       2,000,000
Number of classes:   8
Samples per class:   250,000
Number of features:  42
Noise level:         0.005

Standard split

Training:    1,600,000
Validation:    200,000
Testing:      200,000

The target class is not included among the 42 input descriptors.

Physical parameters are retained separately for scientific analysis and interpretation.

42 Candidate Features

The original descriptor space contains:

R
Ricci2
Kretschmann
Weyl2
Weyl4
r2_R
r4_Ricci2
r4_K
r4_Weyl2
r8_Weyl4
abs_R
abs_Ricci2
abs_K
abs_Weyl2
abs_Weyl4
log_R
log_Ricci2
log_K
log_Weyl2
log_Weyl4
EM_Field
EM2
EM4
Charge_Spin
Charge_Spin2
Rotation
Rotation2
Rotation_Curvature
Mass_Charge
Mass_Spin
Cosmological
Cosmological2
Expansion
Expansion2
Expansion_Curvature
Parity1
Parity2
Parity3
Curvature_Charge
Curvature_Rotation
Curvature_Cosmological
Ricci_Weyl_Coupling

Repository Structure

A recommended repository organization is:

.
├── README.md
├── LICENSE
├── CITATION.cff
│
├── data/
│   ├── GR_Spacetime_V4_FULL.csv
│   ├── GR_Spacetime_V4_PARAMETERS.csv
│   ├── GR_Spacetime_V4_FEATURES.csv
│   ├── GR_Spacetime_V4_TRAIN.csv
│   ├── GR_Spacetime_V4_VAL.csv
│   ├── GR_Spacetime_V4_TEST.csv
│   └── FEATURE_LIST.txt
│
├── src/
│   ├── dataset_generation.py
│   ├── feature_importance.py
│   ├── minimum_k_analysis.py
│   ├── multi_seed_robustness.py
│   └── visualization.py
│
├── figures/
│   ├── Figure_1_Minimum_K_Analysis.png
│   ├── Figure_2_Feature_Importance_42.png
│   ├── Figure_3_Multi_Seed_Robustness.png
│   ├── Figure_4_Confusion_Matrix_8_Features.png
│   ├── Figure_5_XGBoost_Learning_Curve.png
│   ├── Figure_6_2D_Intrinsic_Spacetime_Manifold.png
│   ├── Figure_7_3D_Intrinsic_Spacetime_Manifold.png
│   └── Figure_8_8Feature_Correlation_Heatmap.png
│
└── results/
    ├── feature_importance/
    ├── minimum_k/
    └── multi_seed/

Reproducibility

The analysis uses fixed random seeds for the reported robustness experiments.

The ten-seed analysis uses:

SEEDS = [42, 52, 62, 72, 82,
         92, 102, 112, 122, 132]

The feature-selection procedure separates feature ranking from the subsequent Top-K evaluation so that the minimal representation can be evaluated systematically.

Visualizations

The repository contains visualizations for:

- minimum-K feature analysis,
- 42-feature importance ranking,
- multi-seed robustness,
- confusion matrix,
- XGBoost learning behavior,
- 2D intrinsic spacetime manifold,
- 3D intrinsic spacetime manifold,
- correlations among the final eight descriptors.

Software

The computational workflow is based primarily on Python and includes machine-learning and scientific-computing libraries such as:

Python
NumPy
Pandas
Scikit-learn
XGBoost
Matplotlib

Additional packages may be required for the manifold visualization analysis.

Research Questions

The project addresses the following questions:

1. Can intrinsic geometric descriptors distinguish the selected spacetime families?
2. How much redundancy exists among the 42 candidate descriptors?
3. What is the smallest empirically sufficient descriptor subset within the investigated feature space?
4. Is the resulting compact representation robust to changes in random data splitting?
5. How can the selected descriptors be interpreted in relation to spacetime geometry?

Limitations

The conclusions are restricted to:

- the eight spacetime families investigated,
- the 42 candidate descriptors,
- the synthetic data-generation framework,
- the selected noise level,
- the machine-learning methodology used.

The observed eight-feature representation therefore should not be interpreted as a proof that these eight descriptors constitute a universal complete basis for spacetime geometry.

Establishing mathematical descriptor completeness would require a substantially different analysis involving appropriate geometric equivalence relations and theoretical conditions.

Citation

If you use this repository or its datasets in academic work, please cite the associated paper:

Hussain, M. M.; Bhatti, Z.-u.-H.; Rahman, J. U.
Data-Driven Discovery of Minimal Intrinsic Curvature Dependencies
in Spacetime Geometry.

A formal citation will be added when the associated manuscript is published.

Contact

Mirza Mudassar Hussain
PhD Research Scholar
Abdus Salam School of Mathematical Sciences
University of the Punjab, Lahore, Pakistan

GitHub: "Mirza-PU" (https://github.com/Mirza-PU)

License

The repository license and dataset usage conditions will be specified before public release.
