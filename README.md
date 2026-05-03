# Multimodal Spatial Transcriptomics Reveals Complementary Gene and Morphology Signals for High-Resolution Cell Type Identification

> A multimodal Graph Transformer framework integrating transcriptomics and morphology for spatially-resolved cell type identification in the tumour microenvironment.

---

## Overview

This repository presents a complete and reproducible pipeline for analysing **multiplex spatial transcriptomics data** through the integration of **gene expression** and **morphology-derived imaging features**. The framework operates at single-cell resolution and demonstrates that combining transcriptomic and morphological signals improves the identification of biologically meaningful cell populations.

Gene expression is modelled using a **Graph Transformer Network** to capture spatial neighbourhood relationships, while morphological features are extracted using a **convolutional neural network (CNN)**. These modalities are integrated within a multimodal graph-based framework to learn enriched spatial representations of tissue architecture, building on recent advances in multimodal and cross-attention learning for biomedical data integration.

---

## Key Contributions

- Integration of **spatial transcriptomics** and **histology-derived morphology**
- Application of a **Graph Transformer Network** for spatial representation learning
- Development of a **multimodal embedding framework** at single-cell resolution
- Systematic comparison of:
  - Gene-only representations  
  - Morphology-only representations  
  - Multimodal representations  
- Demonstration that multimodal integration improves:
  - Cluster separation  
  - Stability (ARI)  
  - Spatial coherence  
  - Biological interpretability  

---

## Repository Structure

```

project/
│── README.md
│── requirements.txt
│── .gitignore
│
│── notebooks/
│   ├── 1_OC_preprocessing_updated.ipynb
│   ├── 2_Graph_gene_only.ipynb
│   ├── 3_Cnn_embeddings.ipynb
│   ├── 4_Multimodal_Graph_Transformer_Model.ipynb
│   ├── 5_Results.ipynb
│   └── 6_Annotations.ipynb
│
│── dataset/
│   ├── raw/
│   ├── processed/
│   └── images/
│
└── outputs/
├── gene_embeddings/
├── cnn_embeddings/
└── multimodal_embeddings/

````

---

## Pipeline Overview

### 1. Preprocessing
**`1_OC_preprocessing_updated.ipynb`**
- Quality control and filtering  
- Removal of low-quality cells and control probes  
- Normalisation and selection of highly variable genes  

---

### 2. Gene-only Graph Transformer
**`2_Graph_gene_only.ipynb`**
- Construction of spatial k-NN graph  
- Training of a **Graph Transformer Network** on gene expression  
- Generation of spatially-aware gene embeddings  

---

### 3. Morphological Feature Extraction
**`3_Cnn_embeddings.ipynb`**
- Extraction of features from histology images  
- CNN-based encoding of cell morphology  
- Generation of per-cell morphological embeddings  

---

### 4. Multimodal Graph Transformer
**`4_Multimodal_Graph_Transformer_Model.ipynb`**
- Integration of gene and CNN embeddings  
- Construction of multimodal feature space  
- Training of a **Graph Transformer Network**  
- Learning joint spatial multimodal representations, consistent with recent multimodal AI frameworks in cancer and spatial omics analysis [1,6,9]  

---

### 5. Results and Evaluation
**`5_Results.ipynb`**
- Clustering using the Leiden algorithm  
- Evaluation using:
  - Silhouette score  
  - Calinski–Harabasz index  
  - Davies–Bouldin index  
  - Adjusted Rand Index (ARI)  
- Comparative analysis across:
  - Gene-only  
  - CNN-only  
  - Multimodal  

---

### 6. Biological Annotation
**`6_Annotations.ipynb`**
- Differential gene expression analysis  
- Identification of marker genes  
- Cell type annotation  
- Biological interpretation of clusters  

---

## Visualisations

- UMAP projections (clusters and cell types)  
- Spatial tissue maps  
- Clustering performance comparisons  
- Marker gene heatmaps  
- Quality control plots  

---

## Data Source

This project uses data from the **Vizgen MERSCOPE FFPE Human Immuno-Oncology Data Release**:

https://info.vizgen.com/ffpe-showcase?submissionGuid=c2b903c1-af36-4e0e-be04-08489f6aeb95

---

## Key Findings

- Multimodal integration consistently outperforms unimodal approaches  
- Graph Transformer models effectively capture spatial dependencies  
- Combining gene expression and morphology improves:
  - Cell type resolution  
  - Cluster robustness  
  - Biological interpretability  
- These findings are consistent with recent work on multimodal and mechanism-aware AI in biomedical systems [7,9]  

---

## Requirements

Install dependencies using:

```bash
pip install -r requirements.txt
````

---

## Notes

* The pipeline is modular and reproducible
* Each notebook follows a logical progression of analysis
* GPU is recommended for training CNN and Graph Transformer models

---

## References

[1] Chelebian, E., Avenel, C., Wählby, C.(2025) Combining spatial transcriptomics with tissue morphology. *Nature Communications*, 16(1):4452.

[2] Luo, J., Fu, J., Lu, Z., Tu, J. (2025) Deep learning in integrating spatial transcriptomics with other modalities.  
*Briefings in Bioinformatics*, 26(1):bbae719.

[3] Doan, L. M. T., Shahhosseini, K., Verma, S., Marefat, A., Locicero, G., Verma, S., Angione, C., Occhipinti, A. (2026) 
Bridging modalities with AI: a review of AI advances in multimodal biomedical imaging. *Communications Engineering*, 5(1):30.

```
