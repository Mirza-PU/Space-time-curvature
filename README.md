Data-Driven Discovery of Minimal Intrinsic Curvature Dependencies in Spacetime Geometry

<p align="center">A Data-Driven Framework for Identifying Compact Intrinsic Geometric Representations of Spacetime

</p><p align="center">""Python" (https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)" (https://www.python.org/)
""XGBoost" (https://img.shields.io/badge/XGBoost-ML-1F425F)" (https://xgboost.readthedocs.io/)
""Scikit-learn" (https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn&logoColor=white)" (https://scikit-learn.org/)
""Dataset" (https://img.shields.io/badge/Dataset-2M%20samples-5B5B5B)" (#dataset)
""Features" (https://img.shields.io/badge/Candidate%20features-42-5B5B5B)" (#feature-space)
""Minimal representation" (https://img.shields.io/badge/Minimal%20representation-8%20features-2E7D32)" (#minimal-eight-feature-representation)

</p>---

Abstract

This repository contains the computational resources associated with the study “Data-Driven Discovery of Minimal Intrinsic Curvature Dependencies in Spacetime Geometry.”

The study investigates whether a compact subset of physically meaningful intrinsic geometric descriptors can preserve sufficient information to distinguish a defined collection of spacetime geometries.

Starting from 42 candidate descriptors, we employ XGBoost-based feature-importance analysis and systematic sequential feature reduction to identify an empirically minimal representation for eight selected spacetime families.

The resulting eight-feature representation is subsequently evaluated using independent test data and a 10-random-seed robustness analysis.

«Scope: The identified eight-feature representation is an empirical result within the investigated descriptor space, data-generation framework, and selected spacetime families. It is not proposed as a universal mathematically complete set of spacetime invariants.»

---

Research Objective

The central research question is:

«Can a compact subset of intrinsic geometric descriptors preserve the information required to distinguish the selected spacetime families?»

The study therefore focuses on:

- identification of descriptor redundancy;
- data-driven feature reduction;
- compact intrinsic geometric representation;
- classification consistency;
- robustness to random data splits;
- interpretation of the selected descriptors.

The objective is not to replace Einstein's field equations or numerical relativity, but to investigate the informational structure of a predefined descriptor space.

---

Spacetime Families

The dataset represents eight spacetime families:

Class| Spacetime
1| Minkowski
2| Schwarzschild
3| Kerr
4| Reissner–Nordström
5| Kerr–Newman
6| de Sitter
7| Anti-de Sitter
8| FLRW

---

Dataset

The study uses 2,000,000 synthetically generated samples, with an equal number of samples assigned to each spacetime family.

Property| Value
Total samples| 2,000,000
Spacetime families| 8
Samples per family| 250,000
Candidate descriptors| 42
Noise level| 0.005
Training samples| 1,600,000
Validation samples| 200,000
Test samples| 200,000

The samples are constructed from established analytical spacetime geometries and their associated geometric quantities.

---

Methodology

The computational workflow is:

Established Analytical Spacetime Families
                    │
                    ▼
          Synthetic Data Generation
                    │
                    ▼
          42 Candidate Descriptors
                    │
                    ▼
            XGBoost Classification
                    │
                    ▼
          Feature-Importance Ranking
                    │
                    ▼
          Sequential Top-K Evaluation
                    │
                    ▼
       Minimal 8-Feature Representation
                    │
                    ▼
          Independent Test Evaluation
                    │
                    ▼
        10-Seed Robustness Analysis

Feature-selection strategy

The feature-selection procedure consists of:

1. ranking the 42 descriptors using XGBoost feature importance;
2. evaluating progressively smaller Top-K representations;
3. identifying the smallest representation satisfying the predefined performance criterion;
4. evaluating the resulting representation on independent test data;
5. repeating the evaluation across 10 random seeds.

---

Feature Space

The original descriptor space contains 42 candidate variables:

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

---

Minimal Eight-Feature Representation

The systematic feature-reduction analysis identified the following eight descriptors:

Rank| Descriptor
1| "abs_K"
2| "R"
3| "r2_R"
4| "Parity2"
5| "Rotation2"
6| "EM2"
7| "log_R"
8| "Cosmological"

Thus, the investigated descriptor space was reduced from:

42 candidate descriptors → 8 descriptors

while retaining the required classification performance under the study's predefined criterion.

---

Classification Performance

Final Eight-Feature Model

Metric| Test Performance
Accuracy| 0.999175
Macro-F1| 0.999175
Precision| 0.999176
Recall| 0.999175

---

Robustness Across Random Seeds

The final eight-feature representation was evaluated using 10 random seeds:

42, 52, 62, 72, 82,
92, 102, 112, 122, 132

Each seed corresponds to a new stratified train/validation/test split.

Aggregate Results

Metric| Mean ± Standard Deviation
Test Accuracy| 0.999189 ± 0.000062
Macro-F1| 0.999189 ± 0.000062
Precision| 0.999190 ± 0.000062
Recall| 0.999189 ± 0.000062

Test accuracy range:

0.999095 – 0.999285

95% confidence interval for the mean test accuracy:

[0.999150, 0.999228]

The multi-seed analysis is intended to assess the stability of the observed performance with respect to the tested random data partitions.

---

Results and Visualizations

The repository contains the principal figures associated with the analysis:

Figure| Description
Figure 1| Minimum-K Feature Analysis
Figure 2| 42-Feature Importance Ranking
Figure 3| Multi-Seed Robustness
Figure 4| Confusion Matrix for the Eight-Feature Representation
Figure 5| XGBoost Learning Curve
Figure 6| 2D Intrinsic Spacetime Manifold
Figure 7| 3D Intrinsic Spacetime Manifold
Figure 8| Correlation Heatmap of the Eight Selected Features

Figures can be viewed in the ""figures/"" (figures/) directory.

---

Scientific Scope and Limitations

The results are restricted to:

- the eight spacetime families investigated;
- the 42 candidate descriptors;
- the specified synthetic data-generation framework;
- the selected noise level;
- the XGBoost-based feature-selection methodology;
- the experimental evaluation protocol.

Accordingly, the eight-feature representation should be interpreted as an empirically minimal representation within the investigated setting.

It should not be interpreted as:

- a universal basis of spacetime invariants;
- a proof of descriptor completeness;
- a replacement for Einstein's field equations;
- a substitute for exact or numerical solutions of General Relativity.

A mathematical completeness result would require an independent theoretical treatment of invariant characterization and the appropriate geometric equivalence relations.

---

Reproducibility

The reported robustness experiment uses the following fixed seed set:

SEEDS = [42, 52, 62, 72, 82,
         92, 102, 112, 122, 132]

The repository is organized to separate:

Feature Ranking
      ↓
Top-K Evaluation
      ↓
Minimal Representation
      ↓
Independent Testing
      ↓
Multi-Seed Robustness

This separation allows the feature-reduction procedure and its robustness to be independently inspected.

---

Repository Structure

GR-Spacetime/
│
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

---

Software Requirements

The analysis is implemented in Python using:

- Python 3.x
- NumPy
- Pandas
- Scikit-learn
- XGBoost
- Matplotlib

Additional dependencies may be required for specific visualization routines.

---

Citation

If you use the code, datasets, or methodology from this repository, please cite the associated manuscript:

«Hussain, M. M.; Bhatti, Z.-u.-H.; Rahman, J. U.
Data-Driven Discovery of Minimal Intrinsic Curvature Dependencies in Spacetime Geometry.»

A complete bibliographic citation will be added following publication.

---

Authors

Mirza Mudassar Hussain
Abdus Salam School of Mathematical Sciences
University of the Punjab, Lahore, Pakistan

Zaeem-ul-Haq Bhatti
University of the Punjab

Jamshaid Ul Rahman

---

Project Status

Dataset: Completed
Feature-selection analysis: Completed
Eight-feature representation: Identified
10-seed robustness analysis: Completed
Visualization: Completed
Manuscript: In preparation

---

License

The license and data-use terms will be specified with the public release of the repository.
