Data-Driven Discovery of Minimal Intrinsic Curvature Dependencies in Spacetime Geometry

<p align="center">
<b>Compact Intrinsic Geometric Representations of Spacetime</b>
</p><p align="center">
A data-driven machine learning framework for identifying compact representations within a predefined space of intrinsic geometric descriptors.
</p>---

📖 Overview

This repository contains the computational resources developed for investigating the redundancy and minimality of intrinsic geometric descriptors across a selected collection of spacetime geometries.

The framework begins with a set of 42 candidate descriptors derived from curvature invariants and related geometric and physical quantities. XGBoost-based feature-importance analysis is combined with systematic sequential feature reduction to investigate whether a substantially smaller descriptor representation can preserve the information required to distinguish the selected spacetime families.

The analysis identifies an eight-feature representation that maintains very high classification performance on the investigated dataset.

The study is intended as a data-driven exploratory analysis of descriptor redundancy and compact representation. The identified representation is specific to the investigated descriptor space, data-generation framework, and spacetime families.

---

✨ Key Features

- Data-driven analysis of intrinsic spacetime descriptors
- 42 candidate geometric descriptors
- Eight selected spacetime families
- XGBoost-based feature-importance analysis
- Systematic Top-K feature reduction
- Identification of an eight-feature representation
- Independent test-set evaluation
- 10-random-seed robustness analysis
- 2D and 3D intrinsic-space visualization
- Feature-correlation analysis
- Reproducible computational workflow

---

🌌 Spacetime Families

The dataset represents eight selected spacetime families:

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

🔬 Methodology

The complete computational workflow consists of the following stages:

1. Construction of samples from established analytical spacetime geometries
2. Generation of associated geometric quantities
3. Construction of the 42-dimensional descriptor space
4. Dataset preparation and stratified splitting
5. XGBoost model training
6. Feature-importance analysis
7. Sequential Top-K feature evaluation
8. Identification of the minimal eight-feature representation
9. Independent test-set evaluation
10. Multi-seed robustness analysis
11. Geometric and statistical visualization

---

📐 Intrinsic Descriptor Representation

The initial representation contains 42 candidate descriptors involving curvature invariants, transformed curvature quantities, electromagnetic terms, rotation-related quantities, cosmological terms, parity-related quantities, and descriptor couplings.

The complete descriptor list is provided in:

FEATURE_LIST.txt

The final compact representation identified by the analysis consists of:

Descriptor| Role in the selected representation
"abs_K"| Absolute Kretschmann-related descriptor
"R"| Ricci scalar
"r2_R"| Squared radial-scaled Ricci descriptor
"Parity2"| Parity-related descriptor
"Rotation2"| Rotation-related descriptor
"EM2"| Electromagnetic descriptor
"log_R"| Log-transformed Ricci scalar
"Cosmological"| Cosmological descriptor

Thus, the investigated descriptor space is reduced from:

42 candidate descriptors
          ↓
8 selected descriptors

---

📊 Dataset

GR-Spacetime V4 Dataset

The computational study uses a synthetic dataset containing 2,000,000 samples distributed equally across the eight spacetime families.

Dataset Statistics

Property| Value
Total samples| 2,000,000
Number of classes| 8
Samples per class| 250,000
Candidate descriptors| 42
Noise level| 0.005
Training samples| 1,600,000
Validation samples| 200,000
Test samples| 200,000

The target class is kept separate from the descriptor variables.

Physical parameters are also retained separately for scientific analysis and interpretation.

---

🧠 Machine Learning Framework

<p align="center">
<img src="figures/ML_Workflow.png" width="850">
</p>The machine-learning framework uses XGBoost to evaluate the information contained in the candidate descriptor space.

Feature importance is first used to obtain a descriptor ranking. The ranked descriptors are subsequently evaluated using systematic Top-K experiments.

This procedure allows the relationship between descriptor dimensionality and classification performance to be examined.

---

🔎 Feature Reduction

The feature-reduction procedure follows:

42 Candidate Descriptors
          ↓
XGBoost Feature Importance
          ↓
Feature Ranking
          ↓
Sequential Top-K Evaluation
          ↓
Performance Criterion
          ↓
Minimal 8-Feature Representation

The resulting representation is then evaluated independently rather than relying only on the feature-selection stage.

---

🎯 Final Eight-Feature Representation

The selected descriptors are:

abs_K
R
r2_R
Parity2
Rotation2
EM2
log_R
Cosmological

The final model using these eight descriptors achieved:

Metric| Test Performance
Accuracy| 0.999175
Macro-F1| 0.999175
Precision| 0.999176
Recall| 0.999175

---

🔁 Robustness Analysis

To investigate sensitivity to random data partitioning, the final eight-feature representation was evaluated using 10 random seeds.

42
52
62
72
82
92
102
112
122
132

Each seed corresponds to a new stratified train/validation/test split.

Multi-Seed Results

Metric| Mean ± SD
Test Accuracy| 0.999189 ± 0.000062
Macro-F1| 0.999189 ± 0.000062
Precision| 0.999190 ± 0.000062
Recall| 0.999189 ± 0.000062

Test Accuracy Range

Minimum: 0.999095
Maximum: 0.999285

95% Confidence Interval

[0.999150, 0.999228]

The multi-seed experiment provides an assessment of the stability of the observed performance across the tested random partitions.

---

📈 Results and Visualizations

The repository contains the main visualizations generated during the analysis.

Figure| Description
Figure 1| Minimum-K Feature Analysis
Figure 2| 42-Feature Importance Ranking
Figure 3| Multi-Seed Robustness
Figure 4| Eight-Feature Confusion Matrix
Figure 5| XGBoost Learning Curve
Figure 6| 2D Intrinsic Spacetime Manifold
Figure 7| 3D Intrinsic Spacetime Manifold
Figure 8| Eight-Feature Correlation Heatmap

Figures are available in the:

figures/

directory.

---

🖼️ Visualization

2D Intrinsic Spacetime Manifold

<p align="center">
<img src="figures/Figure_6_2D_Intrinsic_Spacetime_Manifold.png" width="750">
</p>3D Intrinsic Spacetime Manifold

<p align="center">
<img src="figures/Figure_7_3D_Intrinsic_Spacetime_Manifold.png" width="750">
</p>Eight-Feature Correlation Structure

<p align="center">
<img src="figures/Figure_8_8Feature_Correlation_Heatmap.png" width="750">
</p>---

💻 Software Requirements

The computational framework is implemented using:

- Python 3.x
- NumPy
- pandas
- scikit-learn
- XGBoost
- matplotlib

Install the required dependencies using:

pip install -r requirements.txt

---

📁 Repository Structure

GR-Spacetime/
│
├── data/
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
├── src/
│   ├── dataset_generation.py
│   ├── feature_importance.py
│   ├── minimum_k_analysis.py
│   ├── multi_seed_robustness.py
│   └── visualization.py
│
├── results/
│
├── requirements.txt
├── README.md
├── CITATION.cff
└── LICENSE

---

🚀 Installation

Clone the repository:

git clone https://github.com/Mirza-PU/GR-Spacetime.git

Navigate to the repository:

cd GR-Spacetime

Install the required packages:

pip install -r requirements.txt

---

▶️ Usage

Step 1: Prepare the Dataset

python src/dataset_generation.py

Step 2: Calculate Feature Importance

python src/feature_importance.py

Step 3: Perform Sequential Top-K Analysis

python src/minimum_k_analysis.py

Step 4: Run Multi-Seed Robustness Analysis

python src/multi_seed_robustness.py

Step 5: Generate Visualizations

python src/visualization.py

---

🔬 Scientific Scope

The study investigates descriptor redundancy within a predefined feature space and selected spacetime families.

The eight-feature representation should therefore be interpreted as an empirically minimal representation for the investigated setting.

It does not establish:

- universal descriptor completeness;
- a universal basis of spacetime invariants;
- equivalence of all possible spacetime geometries;
- replacement of Einstein's field equations;
- replacement of exact or numerical General Relativity.

The work instead provides a computational framework for exploring whether a compact descriptor representation can retain discriminative information within a specified family of geometries.

---

📚 Citation

If you use this repository, datasets, code, or methodology in your research, please cite the associated manuscript:

Hussain, M. M.; Bhatti, Z.-u.-H.; Rahman, J. U.

Data-Driven Discovery of Minimal Intrinsic Curvature
Dependencies in Spacetime Geometry.

A complete bibliographic citation will be added following publication.

---

👨‍🔬 Authors

Mirza Mudassar Hussain
Abdus Salam School of Mathematical Sciences
University of the Punjab
Lahore, Pakistan

Zaeem-ul-Haq Bhatti
University of the Punjab

Jamshaid Ul Rahman

---

🤝 Contributions

Contributions, suggestions, reproducibility checks, and scientific discussions are welcome.

For questions concerning the computational implementation or scientific methodology, please open an issue in the repository.

---

📄 License

The repository license and data-use conditions will be specified with the public release.

---

<p align="center">Data → Geometry → Feature Reduction → Compact Representation → Robustness

</p>