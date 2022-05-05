# Molecular Classification of Cancer: a PCA Approach

Jinghan Cui, Xinyang Liu

STAT697MV Final Project

## Introduction
The project is inspired by the study published in 1999 by Golub _et al_ in which researchers developed a systematic approach to cancer classification based on global gene expression analysis using DNA microarrays. Traditionally, diagnosis of cancer has relied on histopathological appearance, but a serious limitation is that tumors with similar histopathological appearance may have different clinical courses and responses to therapy. 

Taking acute leukemias for example, there are two sub-types: acute lymphoblastic leukemia(ALL) and acute myeloid leukemia(AML). It is important to distinguish ALL from AML for target treatment.  The distinction between them can be well done in clinical practice, but misclassification may occur sometimes.

We developed a classification model based on the gene expression data. Out of thousands of genes, we tried to identify a small portion of gene with significantly different gene expression levels. If we have a new, unknown sample of acute leukemia, then researchers can perform gene sequencing on targeted gene we have identified and use the classification model as an assistance to the diagnosis of cancer sub-type.

## Data
We used the same data as Golub _et al_ used in their study. The dataset consists of quantitative expression levels of 7192 genes from 72 acute leukemia patients. The patients are labeled with Acute myeloid leukemia(AML) and Acute lymphoblastic leukemia(ALL) from previous clinical diagnoses. 

## Methods
Since this is a problem of "$p>>n$", dimension reduction should be done before we implement a logistic regression model. Hence, we will perform Principal Component Analysis (PCA) on the gene expression data for dimension reduction. Then we use the principal components to classify the types of leukemia. Comparing the accuracies of classification with different numbers of components, we pick the model with the best balance of sensitivity and specificity. Next, we calculate the bootstrap confidence interval for each component along with the z-score confidence interval and find the significant one. We then analyze the components using marginal correlation to identify genes that are differentially expressed between AML and ALL.
