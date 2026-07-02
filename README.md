# Protein Conformation Generation using Geometry-Aware Variational Autoencoders
## Overview

This project explores deep generative modeling of protein conformational ensembles using Variational Autoencoders (VAEs). The model learns latent structural representations of proteins and generates physically plausible conformations through geometry-aware constraints and internal-coordinate reconstruction.

The pipeline combines:

* Variational Autoencoders
* Internal-coordinate protein representation
* NeRF-based Cartesian reconstruction
* Distance-map regularization
* Contact-map analysis
* Structural evaluation metrics

The primary objective is to generate realistic protein conformations while preserving global fold topology and local geometric consistency.

## Model Architecture

- Encoder: Multi-layer Variational Encoder
- Latent Space: Gaussian latent manifold
- Decoder: Geometry-aware decoder for internal-coordinate reconstruction
- Reconstruction: NeRF-based Cartesian reconstruction
- Regularization:
  - KL divergence
  - Distance-map loss
  - Radius-of-gyration loss
  - Contact-map constraints


## Results

### Prior Sampling RMSD

| State | RMSD |
|---|---|
| Open | 2.33 Å |
| Closed | 3.33 Å |

## Contact Map Comparison

![ Contact Map](figures/contact_map.png)



---

## Geometry Distribution Analysis

### Dihedral Distributions
![Dihedral Distribution](figures/dihedral_distribution.png)

### Bond Angle Distributions
![Bond Angle Distribution](figures/bond_angle_distribution.png)

### Bond Length Distributions
![Bond Length Distribution](figures/bond_length_distribution.png)

---

## PyMOL Structural Alignment

![PyMOL Alignment](figures/pymol_alignment.png)

## Tech Stack

- Python
- PyTorch
- NumPy
- Matplotlib
- PyMOL

## Future Improvements

- Residual CNN decoder
- Equivariant architectures
- Diffusion-based conformational generation


## Author

Vikash Kumar Mahato

### Research Interests
- Generative AI for proteins
- Computational biology
- Deep learning
- Protein structure modeling