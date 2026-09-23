# Single-Cell Transcriptomic Characterization of Tumor Immune States and an Immune State Index in HNSCC

This repository contains the computational framework and single-cell pipeline for characterizing heterogeneous immune populations, checkpoint-associated expression patterns, and transcriptionally defined immune states in Head and Neck Squamous Cell Carcinoma (HNSCC).

## 📌 Overview
The framework processes raw transcriptomic matrices to calculate an **Immune State Index (ISI)** derived from the balance of T-cell activity signatures and checkpoint/myeloid-associated signals. The computational labeling workflow categorizes cellular environments into *Inflamed*, *Immune-Excluded*, and *Immune-Desert* states, which are subsequently evaluated using a Random Forest classifier.

## 📂 Repository Structure
*   `Single_Cell_Analysis_and_Immune_State_Modeling_of_the_Tumor_Microenvironment.ipynb`: The core Google Colab / Jupyter notebook containing the Scanpy workflow, visualization scripts, and machine learning classification tracking.
*   `CITATION.cff`: The formal schema block mapping dataset authorship, project version parameters, and software tracking attributes for automated Zenodo archiving.

## ⚙️ How to Load the Workspace
You can execute the entire analysis pipeline using the cloud-hosted runtime environment without local package installations:

1. Open the file `Single_Cell_Analysis_and_Immune_State_Modeling_of_the_Tumor_Microenvironment.ipynb` in this repository.
2. Click the **"Open in Colab"** badge at the top of the file layout workspace.
3. Once inside Google Colab, execute the setup blocks to initialize the analysis stack:
   ```python
   import scanpy as sc
   import numpy as np
   import pandas as pd
   ```
4. The notebook automatically streams the primary primary single-cell expression matrices directly from public accessions (**GSE164690** and **GSE131907**), executing the quality control pipelines down to downstream indexing workflows.

## 🔬 Key Methodological Components
*   **Quality Control & Preprocessing:** Low-quality filtering using mitochondrial transcript percentages and variable gene screening via Scanpy.
*   **Dimensionality Reduction:** Neighborhood graph constructions mapped across optimized UMAP coordinates and Leiden clustering variations.
*   **Scoring Infrastructure:** Average gene-set enrichment tracking utilizing candidate marker configurations (`CD3D`, `CD3E`, `GZMB` vs `CD274`, `C1QA`, `LST1`, `CXCL9`).
*   **Classification Engine:** Balanced ensembled Random Forest sorting over stratified validation matrices.

## 📄 License
This repository is shared as an open-access scientific resource. Please refer to the workspace properties or the file declarations for downstream redistribution permissions.
