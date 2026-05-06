# Dataset for Continuous B-Cell Epitope Prediction

## Overview

This repository contains the curated dataset used in our study on the prediction of continuous B-cell epitopes using machine learning approaches, specifically recurrent neural networks (RNNs).

The dataset was originally developed for the identification and prediction of linear (continuous) B-cell epitopes in antigenic protein sequences. This resource may be useful for researchers working in:

- Immunoinformatics
- Vaccine design
- Antibody epitope prediction
- Computational immunology
- Machine learning-based peptide classification

---

## Citation

Saha S, Raghava GP. Prediction of continuous B-cell epitopes in an antigen using recurrent neural network. Proteins. 2006 Oct 1;65(1):40-8. doi: 10.1002/prot.21078. PMID: 16894596.
---

## Dataset Description

The dataset consists of experimentally validated B-cell epitopes and negative peptide samples.

### Positive Dataset

- Contains **700 non-redundant experimentally validated continuous B-cell epitopes**
- Collected from the **Bcipep database**
- Only epitopes of length **≤ 20 amino acids** were considered
- Redundant sequences were removed to reduce bias

### Negative Dataset

- Contains **700 non-epitope peptide sequences**
- Randomly generated from **Swiss-Prot proteins**
- Any sequence identical to known epitopes was removed

Thus, the final benchmark dataset contains:

| Dataset Type | Number of Sequences |
|-------------|----------------------|
| B-cell Epitopes | 700 |
| Non-Epitopes | 700 |
| Total | 1400 |

---

## Data Processing

To create fixed-length patterns suitable for neural network training:

- Variable-length epitopes were normalized to fixed window lengths
- Neighboring residues from the parent antigen sequence were added when needed
- Multiple window sizes (10, 12, 14, 16, 18, and 20 residues) were evaluated

The best performance was achieved with:

- **Window Length:** 16 residues
- **Model:** Recurrent Neural Network (Jordan Network)

---

## Repository Contents

```bash
.
├── positive_epitopes.csv        # Positive B-cell epitopes
├── negative_epitopes.csv        # Negative peptide samples
├── combined_dataset.csv         # Combined benchmark dataset
├── README.md                    # Repository documentation
```

*(File names can be modified according to your repository structure.)*

---

## Applications

This dataset can be used for:

- Training machine learning/deep learning models
- Benchmarking epitope prediction tools
- Feature engineering on peptide sequences
- Comparative studies with modern protein language models



### BibTeX

```bibtex
@article{saha2006abcpred,
  title={Prediction of continuous B-cell epitopes in an antigen using recurrent neural network},
  author={Saha, Sudipto and Raghava, G.P.S.},
  journal={Proteins: Structure, Function, and Bioinformatics},
  volume={65},
  number={1},
  pages={40--48},
  year={2006},
  publisher={Wiley},
  doi={10.1002/prot.21078}
}
```

---

## License

This dataset is shared for academic and research purposes only. Please cite the original publication when using this resource.

---
