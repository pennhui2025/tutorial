## Proteomics Data Analysis Tutorials
This repository provides simple example code and data resources for the hands-on tutorial chapter “Hands-On Tutorials and Sample Codes” in a proteomics data analysis book. The tutorials are designed to help readers understand how workflow optimization, multi-view learning, and machine learning can be applied to proteomics differential expression analysis and biomarker discovery.

The repository is intended for teaching and demonstration. The scripts are simplified examples that illustrate the major analytical ideas. For full-scale analysis, users should refer to the original software packages and publications.

Tutorials included

# Tutorial 1: Workflow Optimization Using AI
This tutorial is based on the OpDEA framework. It introduces proteomics differential expression analysis as a workflow-level optimization problem. Instead of selecting a single arbitrary pipeline, users learn how different choices of expression matrix, normalization method, missing-value imputation method, and statistical test can affect differentially expressed protein discovery.

# Main topics:
•	Preparing a protein-by-sample expression matrix

•	Checking sample metadata

•	Inspecting missing values

•	Running simple differential expression analysis

•	Comparing multiple workflow outputs

•	Summarizing robust differentially expressed proteins

•	Interpreting the idea of OpDEA-guided workflow optimization

# Tutorial 2: Multi-View Learning for Proteomics Data
This tutorial is inspired by the M-VIDIA framework: Multi-View representation to Increase modality Depth using Integrative AI. It shows how multiple quantitative views of the same proteomics dataset can be aligned and integrated.

# Main topics:
•	Loading multiple proteomics views, such as directLFQ, MaxLFQ, and TopN intensity
•	Matching proteins and samples across views
•	Preprocessing and scaling each view
•	Building a simple integrated representation
•	Comparing single-view and multi-view results
•	Visualizing sample separation and clustering patterns

# Tutorial 3: Biomarker Discovery with Machine Learning
This tutorial connects OpDEA-guided candidate generation with M-VIDIA-style multi-view representation and machine-learning-based biomarker selection.

# Main topics:
•	Generating candidate proteins from differential expression results

•	Constructing machine-learning feature matrices

•	Training simple classification models

•	Evaluating predictive performance

•	Assessing feature stability

•	Building a small candidate biomarker panel

•	Interpreting biomarkers with biological context
    
# Quick start

git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git

cd YOUR_REPOSITORY

Run the tutorials in R:

source("R/01_tutorial1_workflow_optimization.R")

source("R/02_tutorial2_multiview_learning.R")

source("R/03_tutorial3_biomarker_discovery.R")

Required R packages

install.packages(c(
  "tidyverse",
  "limma",
  "VennDiagram",
  "pheatmap",
  "ggplot2",
  "caret",
  "pROC",
  "randomForest"
))

For limma, some systems may require Bioconductor:
if (!requireNamespace("BiocManager", quietly = TRUE)) {
  install.packages("BiocManager")
}
BiocManager::install("limma")
Optional packages:
install.packages(c("glmnet", "xgboost", "Rtsne", "uwot"))
Input data format
Protein expression matrix
Rows should represent proteins and columns should represent samples.
ProteinID,Sample1,Sample2,Sample3,Sample4
P001,23.1,24.0,28.3,27.9
P002,18.4,NA,20.1,21.5
P003,30.2,29.8,31.4,32.1
Sample metadata
SampleID,Group
Sample1,Control
Sample2,Control
Sample3,Disease
Sample4,Disease
Sample names in the metadata file must match the column names in the expression matrix.
Important notes
1.	These scripts are simplified teaching examples.
2.	The example data are intended for demonstration only.
3.	Users should inspect data quality, missingness, and batch effects before biological interpretation.
4.	Machine-learning results should be evaluated using cross-validation and, ideally, independent validation datasets.
5.	Candidate biomarkers require further biological and experimental validation before clinical use.

# Relation to OpDEA and M-VIDIA
This repository is designed to accompany tutorials based on the following methodological ideas:

•	OpDEA: workflow optimization for proteomics differential expression analysis using large-scale benchmarking, high-performing rules, and ensemble inference.

•	M-VIDIA: multi-view representation learning for proteomics data to increase modality depth and improve downstream analysis.

The code in this repository provides simplified examples for education. For complete implementation and full functionality, please refer to the original tools and publications.

# Citation
If you use this tutorial repository, please cite the relevant publications:

Peng H., Wang H., Kong W., Li J., Goh W. W. B.
Optimizing differential expression analysis for proteomics data via high-performing rules and ensemble inference.
Nature Communications, 2024.

Peng H., Goh W. W. B.
M-VIDIA: A Multi-View representation to Increase modality Depth using Integrative AI.
License

Please specify a license before public release. Common choices include MIT License, GPL-3.0 License, or CC BY 4.0 for tutorial text and documentation.
Contact
For questions, bug reports, or suggestions, please open an issue in this GitHub repository.
Repository maintainer: Hui Peng
Email: penghui@suat-sz.edu.cn
