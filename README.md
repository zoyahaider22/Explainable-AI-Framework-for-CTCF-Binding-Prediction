# Explainable-AI-Framework-for-CTCF-Binding-Prediction
Leakage-free multi-omics deep learning framework for CTCF binding prediction using CNN-BiLSTM, Transfer Learning, SHAP, and LIME.


## Overview

This project presents a leakage-free, interpretable deep learning framework for predicting CTCF binding sites using multi-omics integration and transfer learning.

The proposed framework combines:

- DNA sequence information
- Chromatin accessibility (DNase-seq)
- Histone modification signals (H3K27ac)
- 3D genome organization (Hi-C loop counts)

A dual-branch CNN-BiLSTM architecture is used to learn sequence motifs and epigenetic patterns simultaneously.

To ensure biological transparency, Explainable AI (XAI) techniques including SHAP and LIME are incorporated.

---

## Research Motivation

CTCF (CCCTC-Binding Factor) is a critical transcription factor responsible for chromatin organization, enhancer-promoter interactions, and genome insulation.

Many existing deep learning approaches suffer from:

- Data leakage
- Poor cross-region generalization
- Black-box predictions
- Lack of biological interpretability

This work addresses these challenges through rigorous dataset construction, transfer learning, and explainable AI.

---

## Key Contributions

### Leakage-Free Dataset Construction

- RAD21 summit-centered positive windows
- GC-content matched random genomic negatives
- Strict genomic position splitting
- Removal of label-defining features

### Multi-Omics Integration

The framework combines:

- DNA Sequence
- DNase Accessibility
- H3K27ac Signals
- Hi-C Loop Counts

through a gated fusion mechanism.

### Transfer Learning

A pretrained sequence encoder is fine-tuned on unseen genomic regions to improve cross-region generalization.

### Explainable AI

The framework incorporates:

#### SHAP

- Global feature importance
- Biological validation

#### LIME

- Local prediction explanations
- Error analysis

#### Gradient Saliency

- Sequence-level attention visualization
- Motif localization

---

## Methodology

### Phase 1: Data Acquisition

Source:

- ENCODE Project
- Human Genome hg38

Chromosome:

- Chromosome 22

### Phase 2: Dataset Construction

Positive Sites:

- RAD21 ChIP-seq summit-centered windows

Negative Sites:

- GC-matched random genomic background regions

### Phase 3: Feature Engineering

Epigenetic Features:

- DNase-seq
- H3K27ac
- Hi-C Loop Count

Sequence Representation:

- One-hot encoded DNA sequences

### Phase 4: Deep Learning Model

Architecture:

CNN → BiLSTM → Gated Fusion → Dense Layers → Output

### Phase 5: Explainable AI

- SHAP
- LIME
- Gradient Saliency

---

## Model Architecture

```text
DNA Sequence
       │
       ▼
CNN Layers
       │
       ▼
BiLSTM
       │
       ▼
Sequence Features
       │
       ├──────────┐
       │          │
       ▼          ▼

 Epigenetic Features
(DNase + H3K27ac + Hi-C)

       │
       ▼
 Gated Fusion Layer
       │
       ▼
 Dense Layers
       │
       ▼
CTCF Binding Prediction
```

---

## Results

| Model | AUROC |
|---------|---------|
| Logistic Regression | 0.8306 |
| Gradient Boosting | 0.8334 |
| CNN-BiLSTM Sequence Only | 0.7413 |
| Gated Hybrid CNN-BiLSTM | 0.8450 |
| Transfer Learning Model | 0.9197 |

---

## Explainability Results

### SHAP Analysis

DNase accessibility emerged as the most influential predictor, confirming known biological mechanisms.

### LIME Analysis

Provided local explanations for:

- True Positives
- True Negatives
- False Positives
- False Negatives

### Saliency Maps

Highlighted sequence regions corresponding to known CTCF motif footprints.

---

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Scikit-Learn
- SHAP
- LIME
- Matplotlib
- Seaborn

---

## Dataset

ENCODE Project:

https://www.encodeproject.org

Reference Genome:

https://genome.ucsc.edu

---

## Future Work

- Genome-wide validation
- Multi-cell-type evaluation
- DNA methylation integration
- Pan-cancer applications
- Clinical decision-support systems

---

## Author

Zoya Haider

M.Tech Data Science

Jamia Hamdard University

Research Area:
Bioinformatics | Deep Learning | Explainable AI | Genomics

---

## Citation

If you use this work, please cite:

Zoya Haider,
"Explainable AI Framework for CTCF Binding Prediction:
Leveraging Multi-Omics Integration and Transfer Learning",
M.Tech Dissertation,
Jamia Hamdard University,
2026.
