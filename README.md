# Clustering the Forest CoverType Dataset

This repository contains the final project for a university course in **Unsupervised Learning**.
The goal of the project was to explore hidden structure within the Forest CoverType dataset
*without using the original labels*, and to examine how clustering algorithms interpret the data
compared to the human-defined categories.

---

## Project Overview

The analysis combines:
- **Dimensionality Reduction:** PCA, t-SNE, UMAP  
- **Clustering Algorithms:** KMeans (main), DBSCAN, GMM  
- **Cluster Evaluation:** Silhouette Score, NMI, ARI, V-Measure  
- **Feature Contribution Analysis:** Kruskal–Wallis, Eta², Random Forest feature importance  

A core part of the project examines how the clusters formed by unsupervised learning
differ from the original *CoverType* labels — revealing alternative structural patterns
driven by topography, shading, and environmental features.

A detailed academic report summarizing the full analysis is included under `report/`.

---

## How to Run the Project

### 1. Download the dataset
The full dataset is available on Kaggle:

https://www.kaggle.com/datasets/uciml/forest-cover-type-dataset

Download `covtype.csv` and place it in the **root directory of the repository**.

*(The dataset is too large to include directly in GitHub.)*

---

### 2. Run the main notebook
Open:

```
forest_cover_analysis.ipynb
```

The notebook includes:
- Data loading and preprocessing  
- Sampling for faster experimentation  
- PCA and visualization  
- Clustering (KMeans, DBSCAN, GMM)  
- Statistical comparison between cluster labels and true labels  
- Export of result files  

**Before running the notebook**, execute the initial setup cell that creates 
the necessary folder structure and ensures consistent imports.

---

## Working With the Data

This repository includes several helper datasets generated during the analysis:

- `sampled_data.csv`  
  A representative sample of 10,000 observations used for PCA, t-SNE, and exploratory clustering.

- `clustering_performance_results.csv`  
  A table summarizing cluster performance metrics across different methods.

- `comparison_clusters_pca_vs_normalized.xlsx`  
  Side-by-side comparison of:
  - Original labels (`Cover_Type`)  
  - KMeans clusters on normalized data  
  - KMeans clusters after PCA  

These files can be opened in Excel, Google Sheets, or loaded with `pandas`.

---

## Repository Structure

```
project/
│
├── forest_cover_analysis.ipynb      # Main analysis notebook
├── data/
│   ├── sampled_data.csv
│   ├── clustering_performance_results.csv
│   ├── comparison_clusters_pca_vs_normalized.xlsx
│
└── report/
    └── Final_Project_Report.pdf      # Academic report summarizing methodology & results
```

---

## Summary of Findings

Key insights from the project include:
- PCA reduced 54 features to **14 components while preserving ~95% variance**.
- KMeans identified **k = 6** clusters consistently (with and without PCA).
- Similarity between clusters and true labels was extremely low  
  (e.g., **NMI = 0.053**, **ARI = 0.023**), indicating the algorithms uncovered a *different*
  internal structure.
- Feature contribution differed sharply between supervised vs. unsupervised partitions:  
  - Elevation dominated the supervised labels  
  - Hillshade features & Aspect dominated the unsupervised clusters  
- t-SNE visualizations highlighted clear structural differences between the two grouping schemes.

These findings show how unsupervised learning can uncover alternative patterns that do not necessarily
align with human-defined labels, offering complementary insights into the dataset’s structure.

---

## Files

- **Notebook:** `forest_cover_analysis.ipynb`  
- **Dataset samples & outputs:** Located under `/data`
- **Full written report:** `report/Final_Project_Report.pdf`

---

## License
This project is shared for academic and portfolio purposes.  
**No license is granted for reuse or redistribution.**
