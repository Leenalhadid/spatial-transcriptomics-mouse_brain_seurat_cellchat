# Spatial Transcriptomics of Mouse Brain Using Seurat and CellChat

This repository contains an end-to-end analysis pipeline for spatial transcriptomics data obtained from a 10X Genomics Visium experiment. The project focuses on gene expression profiling, spatial patterning, and intercellular communication in mouse brain tissue slices using the Seurat, CellChat, and SCDC packages in R.

## 🧠 Overview

Spatial transcriptomics enables transcriptome-wide analysis of gene expression within the spatial context of tissue architecture. In this project, two mouse brain samples are processed and analyzed to:

- Explore spatial gene expression patterns
- Cluster spatial transcriptomic spots
- Integrate multiple tissue sections
- Identify differentially expressed genes (DEGs)
- Annotate cell types using reference scRNA-seq data

## 📊 Methods and Tools

### Main Tools
- [Seurat](https://satijalab.org/seurat/) — spatial transcriptomics analysis
- [CellChat](https://github.com/sqjin/CellChat) — cell–cell communication
- [SCDC](https://github.com/meichendong/SCDC) — deconvolution analysis

### Data Sources
The raw spatial data can be downloaded from:  
https://icbb-share.s3.eu-central-1.amazonaws.com/single-cell-bioinformatics/scbi_p3.zip


## 🖼️ Outputs

![12](https://github.com/user-attachments/assets/3e36f67f-3c8e-48dd-b2ef-6b54737cdd60)
![15](https://github.com/user-attachments/assets/b9cec21d-ce1b-4f78-a9e1-f192a08c7c09)
![666](https://github.com/user-attachments/assets/78f44031-21e2-4f11-b2d7-e4515dae2331)


## ⚙️ System Setup

Before running the analysis, ensure your R environment is properly configured with the required packages.

## ⚙️ System Setup

### 🖥️ 1. General Setup (All Users)

Open an R session and run the following:

```r
# Install devtools if not already installed
install.packages("devtools")

# Install CellChat from GitHub
devtools::install_github("sqjin/CellChat")

# Install Seurat and other commonly used packages
install.packages(c("Seurat", "patchwork", "ggplot2", "dplyr", "Matrix"))

# Install Bioconductor manager
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
# SCDC for deconvolution
devtools::install_github("meichendong/SCDC")
````
Some packages may need manual installation on Windows:
```r
# glmGamPoi (used in SCTransform)
devtools::install_github("const-ae/glmGamPoi")

# BiocNeighbors (used in Seurat integration)
BiocManager::install("BiocNeighbors")
```

