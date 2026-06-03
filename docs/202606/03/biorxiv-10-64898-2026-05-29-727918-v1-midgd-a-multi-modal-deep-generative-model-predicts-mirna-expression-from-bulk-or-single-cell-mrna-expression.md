---
title: "miDGD: a multi-modal deep generative model predicts miRNA expression from bulk or single-cell mRNA expression"
title_zh: miDGD：一种多模态深度生成模型，可从批量或单细胞mRNA表达预测miRNA表达
authors: "Zamani, F., Rasmussen, A. M., Schuster, V., Diekema, M. H., Krogh, A., Pedersen, J. S."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.727918v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 多模态深度生成模型从mRNA预测miRNA
tldr: miRNA在单细胞和多数bulk RNA-seq数据中无法直接观测，miDGD提出一种深度生成解码器模型，仅从mRNA表达预测miRNA丰度。通过TCGA、GTEx和人类细胞系数据训练，模型学习共享潜在表示，成功重建组织特异性和广泛表达的miRNA，并复现已知靶标关系。在稀疏和单细胞数据中表现稳健，优于现有方法，为miRNA表达预测提供了改进框架。
source: biorxiv
selection_source: fresh_fetch
motivation: miRNA在单细胞和多数bulk RNA-seq数据中无法直接观测，现有方法预测精度有限。
method: miDGD采用深度生成解码器，学习mRNA和miRNA联合潜在表示，从基因表达直接预测miRNA丰度。
result: 在TCGA、GTEx和细胞系数据上，miDGD重建了组织特异性miRNA，再现靶标关系，稀疏和单细胞数据表现优于现有方法。
conclusion: miDGD为无法直接测量miRNA的场景提供了准确预测工具，性能优于现有方法。
---

## 摘要
MicroRNAs（miRNA）是重要的转录后调控因子，然而在单细胞和大多数批量RNA-seq数据集中，其表达通常未被观测。我们提出了miDGD，这是一种深度生成解码器模型，可直接从基因表达预测miRNA丰度。该模型利用来自TCGA、GTEx和人类细胞系的批量及单细胞数据集进行训练，学习了mRNA与miRNA配对图谱的共享潜在表示，将样本组织成反映组织及癌症类型的生物意义聚类。模型重建了组织特异性和广泛表达的miRNA，重现了已知的miRNA-靶标关系，并在稀疏数据和单细胞数据中表现出稳健性能。miDGD优于miRSCAPE及近期miRNA活性推断方法，并改进了跨数据集泛化能力。这些结果表明，在无法直接测量miRNA表达时，深度生成模型可作为预测miRNA表达的更优框架。

## Abstract
MicroRNAs (miRNAs) are important post-transcriptional regulators, yet their expression is typically unobserved in single-cell and most bulk RNA-seq datasets. We present miDGD, a deep generative decoder model that predicts miRNA abundance directly from gene expression alone. Trained on bulk and single-cell datasets from TCGA, GTEx, and human cell lines, miDGD learned a shared latent representation of matched mRNA and miRNA profiles that organized samples into biologically meaningful clusters reflecting tissue and cancer types. The model reconstructed both tissue-specific and broadly expressed miRNAs, recapitulated known miRNA-target relationships, and showed robust performance in sparse and single-cell data. miDGD outperformed miRSCAPE and recent miRNA activity inference methods, with improved cross-dataset generalization. These results establish a deep generative model as an improved framework for predicting miRNA expression when direct measurements are unavailable.