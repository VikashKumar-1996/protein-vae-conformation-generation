# Protein Conformation Generation Using Geometry-Aware Variational Autoencoders

## Overview

This project explores deep generative models for protein conformational ensemble generation, focusing on Variational Autoencoders (VAEs) and geometry-aware deep learning.

The objective is to learn meaningful latent representations of protein structures and generate conformations that preserve global fold topology and local geometric consistency.

### Key Methods

- Variational Autoencoders (VAEs)
- Internal-coordinate protein representation
- NeRF-based Cartesian reconstruction
- Distance-map and contact-map regularization
- SE(3)-equivariant geometric modeling
- Structural evaluation and conformational analysis

## Implemented Models

### 1. Geometry-Aware VAE

The initial VAE framework uses internal-coordinate representations and NeRF-based reconstruction to generate protein conformations.

**Key components:**
- Variational encoder and Gaussian latent space
- Geometry-aware decoder
- Internal-coordinate reconstruction
- KL divergence regularization
- Distance-map and radius-of-gyration losses
- Contact-map analysis

**Prior Sampling Results**

| Conformational State | RMSD |
|---|---:|
| Open | 2.33 Å |
| Closed | 3.33 Å |

**Structural Analysis**

The following visualizations illustrate generated structures and geometric properties.

| Analysis | Figure |
|---|---|
| Contact map | `figures/contact_map.png` |
| Dihedral distributions | `figures/dihedral_distribution.png` |
| Bond-angle distributions | `figures/bond_angle_distribution.png` |
| Bond-length distributions | `figures/bond_length_distribution.png` |
| PyMOL structural alignment | `figures/pymol_alignment.png` |

### 2. SE(3)-Equivariant Conditional VAE

The second implementation explores an SE(3)-equivariant Conditional Variational Autoencoder for T4 Lysozyme (T4L) conformational generation.

The model generates 3D Cα coordinate structures conditioned on the conformational state (Open or Closed).

**Notebook:** `02_Protein_SE3_CVAE_T4L.ipynb`

**Key components:**
- SE(3)-invariant encoder
- SE(3)-equivariant decoder
- Conditional conformational generation
- Graph-based geometric message passing
- Radial basis function (RBF) distance embeddings
- Chirality-aware geometric modeling
- Rotation and translation augmentation
- Kabsch-aligned reconstruction loss
- KL annealing and free-bits regularization

**Training Configuration**

| Parameter | Value |
|---|---:|
| Protein system | T4 Lysozyme |
| Cα atoms | 162 |
| Latent dimension | 64 |
| Hidden dimension | 128 |
| Encoder layers | 4 |
| Decoder layers | 4 |
| Spatial neighbours | 16 |
| Maximum epochs | 150 |
| Optimizer | Adam |
| Learning rate | 0.0003 |

## Evaluation

The implementations include structural and latent-space diagnostics such as:

- Kabsch-aligned RMSD
- Pairwise distance distributions
- Contact-map F1 score
- Radius of gyration
- Bond-length and bond-angle distributions
- Dihedral-angle distributions
- RMSF analysis
- PCA-based conformational landscape analysis
- Latent-space and posterior-collapse diagnostics

The SE(3)-CVAE notebook also includes tests for encoder invariance, decoder equivariance, and chirality sensitivity.

## Repository Structure

```text
protein-vae-conformation-generation/
│
├── 02_Protein_SE3_CVAE_T4L.ipynb
├── figures/
│   ├── contact_map.png
│   ├── dihedral_distribution.png
│   ├── bond_angle_distribution.png
│   ├── bond_length_distribution.png
│   └── pymol_alignment.png
│
└── README.md
```

*Update this structure if your repository contains additional notebooks or files.*

## Dataset

The SE(3)-CVAE notebook expects two PDB trajectory files:

- `trainca_open.pdb`
- `trainca_close.pdb`

Each structure is expected to contain 162 corresponding Cα atoms.

The dataset is not included in this repository. Configure the dataset paths according to your local environment or Google Drive.

## Requirements

- Python
- PyTorch
- NumPy
- MDTraj
- Scikit-learn
- Matplotlib
- PyMOL (for structural visualization)

## Running the Notebook

The SE(3)-CVAE notebook was developed for Google Colab.

1. Open `02_Protein_SE3_CVAE_T4L.ipynb`.
2. Configure the dataset paths.
3. Mount Google Drive if required.
4. Install the required dependencies.
5. Execute the notebook cells sequentially.

## Future Work

- Improved equivariant architectures
- Residual CNN-based decoders
- Diffusion-based protein conformational generation
- Better modeling of conformational diversity
- Enhanced structural validation

## Research Status

This project is an ongoing research effort exploring geometry-aware and equivariant generative models for protein conformational ensembles.

## Author

**Vikash Kumar Mahato**

Research Interests:
- Generative AI for proteins
- Computational structural biology
- Deep generative modeling
- Protein structure and dynamics
