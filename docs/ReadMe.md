# MSCRC

The MSCRC framework gathers the codes that have been used to study the integration of three omics data (mRNA expression, microRNA expression, and DNA methylation data) using [sparse mCCA](https://www.degruyter.com/document/doi/10.2202/1544-6115.1470/html)               to classify colorectal cancer samples.
A multi-omics classifier was trained and is available for colorectal caner subtype prediction with [MSCRCclassifier](https://github.com/Carpentierbio/MSCRCclassifier) R package.
<br/>

![workflow](https://github.com/Carpentierbio/MSCRC/blob/main/docs/Workflow.jpg)
<img src="https://github.com/Carpentierbio/MSCRC/blob/main/docs/Workflow.jpg" alt="workflow" width="50%">

## Multi-omics data integration
From TCGA-COAD and TCGA-READ datasets, we obtained 315 primary tumor samples with matched RNA-seq, microRNA-seq and gene-level DNA methylation profiles for multi-omics data integration. The first step includes multi-omics data [pre-precessing](https://github.com/Carpentierbio/MSCRC/blob/main/1_Multi-omics_data_pre-processing.Rmd) and [multi-omics data fusion](https://github.com/Carpentierbio/MSCRC/blob/main/2_Multi-omics_data_fusion_and_subtyping.Rmd). 
Before fusion, mRNA and microRNA expression data  need to be log2-scaled. And each omics data need to be z-score scaled. [Sparse mCCA](https://www.degruyter.com/document/doi/10.2202/1544-6115.1470/html)               was applied for multi-omics data projection, followed by a weighted average for multi-omics data fusion. Sparse mCCA was implemeted with [PMA](https://cran.r-project.org/web/packages/PMA/index.html) R package.

## Unsupervised colorectal cancer subtyping
After getting the integared multi-omics data, consensus clustering was applied for colorectal cancer subtyping. The details can be accessed [here](https://github.com/Carpentierbio/MSCRC/blob/main/2_Multi-omics_data_fusion_and_subtyping.Rmd).

## Multi-omics classifier building
Subsequently, using the consensus clustering results as labels, a multi-omics classification model using the naïve Bayes algorithm, which has generated reliable and accurate classification results, was [built](https://github.com/Carpentierbio/MSCRC/blob/main/3_Multi-omics_classifier_training.Rmd).

## Multi-omics classifier prediction
To assess the generalization of the multi-omics classifier, we applied it to independent datasets. The detailed prediction procedures can be accessed [here](https://github.com/Carpentierbio/MSCRC/blob/main/4_Multi-omics_classifier_validation.Rmd).




