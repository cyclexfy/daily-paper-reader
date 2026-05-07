---
title: Tumor cell specific total mRNA expression informed neural networks predicts cancer progression
title_zh: 基于肿瘤细胞特异性总 mRNA 表达信息的神经网络预测癌症进展
authors: "Paul, A., Lal, J. C., Ji, S., Fong, C., Chen, K., Ding, Y., Li, R., Dai, Y., Tran, Q., Montierth, M., Alberti, S., Kopetz, S., Wang, W."
date: 2026-05-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.01.722212v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 利用深度学习整合多组学数据进行癌症进展预测
tldr: 本研究针对从多组学数据推断肿瘤表型的挑战，提出了TmSNet深度学习框架。该框架旨在预测肿瘤细胞特异性总mRNA表达量（TmS），克服了传统方法依赖匹配DNA/RNA数据且计算量大的局限。通过整合mRNA、DNA甲基化、miRNA和免疫细胞比例等特征，TmSNet在TCGA及外部队列中表现出优异的预测性能，能有效进行患者风险分层，为异质性队列中的肿瘤转录活性建模提供了可扩展的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的肿瘤细胞特异性总mRNA表达量估算方法计算复杂且依赖匹配的DNA与RNA测序数据。
method: 开发了名为TmSNet的深度学习框架，结合结构化特征选择与专门的神经架构，利用多组学数据预测TmS。
result: TmSNet在12种癌症类型中实现了高达0.93的一致性相关系数，并在外部验证集中展现了良好的泛化能力。
conclusion: TmSNet能够从多组学数据中推断具有生物学意义的表型，为预测癌症进展和患者风险分层提供了高效的计算方案。
---

## 摘要
从高维多组学数据中推断肿瘤分子表型是计算生物学中的一项基本挑战。目前估计肿瘤细胞特异性总 mRNA 表达（TmS）的方法需要匹配的 DNA 和 RNA 测序数据，并依赖于计算密集型的解卷积流程。我们提出了 TmSNet，这是一个利用 mRNA、DNA 甲基化、miRNA 和免疫细胞比例作为输入特征来预测 TmS 的深度学习框架。TmSNet 将结构化特征选择（梯度提升、LASSO、弹性网络）与专门的神经架构相结合，以预测连续的 TmS。在 12 种 TCGA 癌症类型中，TmSNet 的交叉验证性能达到了一致性相关系数（CCC）= 0.93 和相关性 R 平方 = 0.88，并推广到外部队列，相关性分别为 0.54（SCAN-B）和 0.43（FUSCC）。预测的 TmS 值能有效地根据风险对患者进行分层，并保留了跨肿瘤亚型的已知转录谱。这些结果表明，TmSNet 可以从多组学数据中推断出具有生物学意义的表型，并为在异质队列中模拟肿瘤转录活性提供了一个可扩展的框架。

## Abstract
Inferring tumor molecular phenotypes from high-dimensional multi-omic data is a fundamental challenge in computational biology. Current methods for estimating tumor cell-specific total mRNA expression (TmS) require matched DNA and RNA sequencing data and rely on computationally intensive deconvolution pipelines. We present TmSNet, a deep learning framework that predicts TmS using mRNA, DNA methylation, miRNA, and immune cell proportions as input features. TmSNet integrates structured feature selection (gradient boosting, LASSO, elastic net) with specialized neural architectures to predict continuous TmS. Across 12 TCGA cancer types, TmSNet achieved cross-validated performance up to concordance correlation coefficient (CCC) = 0.93 and correlation R-squared = 0.88 and generalized to external cohorts with correlations of 0.54 (SCAN-B) and 0.43 (FUSCC). Predicted TmS values effectively stratify patients by risk and preserve known transcriptional profiles across tumor subtypes. These results demonstrate that TmSNet can infer biologically meaningful phenotypes from multi-omic data and provide a scalable framework for modeling tumor transcriptional activity in heterogeneous cohorts.