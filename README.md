# MORPH2DIAG  
**Atlas-free, automated morphometric pipeline for structural MRI**

MORPH2DIAG is an end-to-end Python framework for standardized preprocessing, tissue segmentation, feature construction, unsupervised subtype discovery, and machine/deep-learning analysis of T1-weighted structural MRI.  
Designed for transparency, reproducibility, and full automation, MORPH2DIAG transforms raw MRI volumes into interpretable morphometric signatures—without requiring anatomical atlases or clinical labels.

---

## Motivation
Structural MRI contains rich information about brain morphology, yet differences in preprocessing, alignment, and feature construction often lead to inconsistent or irreproducible results. MORPH2DIAG provides a **fully standardized, atlas-free pipeline** that:

- normalizes intensity across subjects,
- aligns volumes using PCA-based affine transforms,
- segments GM/WM/CSF via Gaussian Mixture Models,
- constructs regional features via voxelwise parcellation, and
- discovers latent morphometric subtypes through unsupervised learning.

These features support exploratory neuroanatomical analysis and downstream supervised classification.

---

## Key Features

- **One-command preprocessing**  
  Skull-stripped input → intensity-normalized, aligned, scaled, and ready for segmentation.

- **Atlas-free tissue segmentation**  
  GMM-based gray matter (GM), white matter (WM), and cerebrospinal fluid (CSF) estimation.

- **Unsupervised subtype discovery**  
  K-means clustering reveals GM–CSF morphometric gradients without requiring labels.

- **Voxelwise parcellation (~100 parcels)**  
  Data-driven spatial regions with parcel-level mean & variance intensity features.

- **Unified ML/DL evaluation suite**  
  Benchmarks Random Forests, Logistic Regression, XGBoost, and MLP variants  
  (lean, deep, hybrid) with options for focal loss, label smoothing, SWA, and PCA-based dimensionality reduction.

- **Reproducible and modular**  
  Standardized pipeline, version-controlled code, and reproducible outputs.

---

## Pipeline Overview

T1w MRI (NIfTI)
↓
Intensity Normalization
↓
PCA-Based Affine Alignment
↓
Isotropic Rescaling
↓
GMM Tissue Segmentation (GM / WM / CSF)
↓
Global Tissue Fractions
↓
Voxelwise Parcellation (~100 parcels)
↓
Parcel-wise Mean & Variance Features
↓
Unsupervised Clustering (K-Means)
↓
ML/DL Classification (RF, LR, XGBoost, MLP)

---

## Dataset Compatibility

MORPH2DIAG accepts any skull-stripped T1-weighted MRI in NIfTI format (.nii, .nii.gz), including:

- NFBS (Neurofeedback Skull-Stripped dataset)
- OASIS-1 / OASIS-3
- ADNI skull-stripped volumes
- FreeSurfer-, FSL-, or ANTs-derived brain extractions

Clinical labels are not required; MORPH2DIAG supports label-free morphometric analysis.

---

## Citation

If you use MORPH2DIAG in your work, please cite:
