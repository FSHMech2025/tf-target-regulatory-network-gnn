# TF–Target Regulatory Interaction Ranking with Graph Neural Networks

## Overview

This project investigates the use of graph neural networks (GNNs) for ranking candidate transcription factor (TF)–target gene regulatory interactions.

The study compares a GNN-based ranking approach with a topology-based degree baseline and an embedding-aware residual ranking strategy. Candidate interactions are generated from a biological regulatory network and evaluated against externally curated regulatory interactions from TRRUST.

The main goal is not to assume that a more complex model is necessarily superior, but to evaluate whether graph-based representation learning provides additional predictive value beyond simple network topology.

---

## Research Question

Can a graph neural network improve the ranking of candidate TF–target regulatory interactions compared with a simple topology-based degree baseline?

A secondary objective is to investigate whether incorporating embedding-derived information after GNN prediction improves the ranking of candidate interactions.

---

## Study Workflow

The analysis follows the pipeline:

**Regulatory Network → Biological Split → GNN Training → Candidate Generation → Ranking → External Validation**

The evaluation framework includes:

1. Construction of the TF–target regulatory network
2. Leakage-controlled biological train/test splitting
3. GNN model training
4. Independent test evaluation
5. Degree-based baseline construction
6. Candidate interaction generation
7. GNN-based candidate ranking
8. Embedding and bias analysis
9. Embedding-aware residual ranking
10. External validation using TRRUST
11. Comparison of ranking strategies

---

## Network and Candidate Space

The regulatory network contains:

- **32,286** TF–target interactions
- **3,926,526** generated candidate TF–target pairs

The candidate space was constructed to enable ranking of potentially novel regulatory interactions.

---

## External Validation

External validation was performed using the TRRUST regulatory interaction database.

A total of:

**2,607 candidate TF–target pairs**

were supported by TRRUST within the candidate space.

The validated interactions contained multiple regulatory effect annotations, including:

- Activation: **905**
- Repression: **595**
- Unknown: **1,270**

These values represent TRRUST annotation records. Some TF–target pairs have multiple annotations or references, so the annotation counts should not be interpreted as unique interaction counts.

---

## Ranking Results

External validation was evaluated at several values of K.

| Ranking method | Top-K | TRRUST validated | Precision@K |
|---|---:|---:|---:|
| Degree baseline | 100 | 0 | 0.0000 |
| Degree baseline | 500 | 0 | 0.0000 |
| Degree baseline | 1,000 | 0 | 0.0000 |
| **Degree baseline** | **5,000** | **47** | **0.0094** |
| Raw GNN | 100 | 0 | 0.0000 |
| Raw GNN | 500 | 3 | 0.0060 |
| Raw GNN | 1,000 | 4 | 0.0040 |
| Raw GNN | 5,000 | 20 | 0.0040 |
| Embedding-aware residual | 100 | 0 | 0.0000 |
| Embedding-aware residual | 500 | 1 | 0.0020 |
| Embedding-aware residual | 1,000 | 1 | 0.0010 |
| Embedding-aware residual | 5,000 | 3 | 0.0006 |

---

## Main Finding

In this experimental setting, the topology-based degree baseline achieved higher external validation precision than the evaluated GNN-based rankings.

At Top-5,000:

- Degree baseline: **47 validated interactions**
- Raw GNN: **20 validated interactions**
- Embedding-aware residual: **3 validated interactions**

This result indicates that simple network topology captured substantial information relevant to the recovery of known regulatory interactions in the evaluated network.

Importantly, the result does not imply that GNNs are generally inferior to topology-based methods. Rather, it shows that the current GNN architecture, feature representation, and experimental setting did not provide a clear advantage over the degree baseline.

---

## Interpretation

The findings highlight an important methodological point in biological network prediction:

> Model complexity does not necessarily translate into improved ranking performance when strong structural information is already present in the network.

The degree baseline provides a useful reference for evaluating whether learned graph representations contribute information beyond basic network connectivity.

The current results therefore support the use of strong, interpretable baselines when evaluating machine-learning approaches for biological network inference.

---

## Limitations

Several limitations should be considered:

- The regulatory network represents an incomplete view of biological regulation.
- External validation depends on the coverage and annotation quality of TRRUST.
- Known regulatory interactions are more likely to be represented in curated databases than newly discovered interactions.
- The candidate space depends on the network construction and candidate-generation strategy.
- The evaluated GNN architecture and feature representation represent one modeling configuration rather than the full space of possible GNN approaches.
- Network topology may already encode strong signals that overlap with information learned by graph-based models.
- TRRUST-based validation cannot establish that unvalidated predictions are biologically incorrect.

---

## Reproducibility

The analysis is organized around reproducible stages:

text
Data preparation
      ↓
Network construction
      ↓
Biological split
      ↓
GNN training
      ↓
Model evaluation
      ↓
Candidate generation
      ↓
Candidate ranking
      ↓
External TRRUST validation
      ↓
Ranking comparison

## Technologies
- Python
- PyTorch
- PyTorch Geometric
- pandas
- NumPy
- scikit-learn
- NetworkX
- Graph Neural Networks (GNNs)
- Biological Network Analysis
- Transcription Factor–Target Interaction Prediction
- External Validation with TRRUST

## Project Status

**Status: Completed — analysis and validation phase**

The core experimental analysis, ranking evaluation, and external validation have been completed. The remaining work consists of final visualization, documentation, and repository organization.

---

## Future Work

Potential future extensions include:

- richer biological node and edge features
- additional regulatory databases
- alternative GNN architectures
- heterogeneous biological graphs
- incorporation of additional omics information
- improved candidate construction
- prospective biological validation

These are considered future directions rather than components of the current study.

---

## Author

**Fatemeh Orak Shirani**

Biomedical Engineering → Mechatronics Engineering → AI / Machine Learning / Computational Medicine

---

## Citation

If this repository contributes to your research, please cite the associated manuscript when available.
