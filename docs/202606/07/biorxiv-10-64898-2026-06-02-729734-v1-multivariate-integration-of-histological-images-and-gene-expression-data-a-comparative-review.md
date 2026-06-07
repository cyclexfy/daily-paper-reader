---
title: "Multivariate integration of histological images and gene expression data: a comparative review"
title_zh: 组织学图像与基因表达数据的多变量整合：一项比较性综述
authors: "Ma, C., Mao, J., Le Cao, K.-A."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729734v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 整合组织学图像与基因表达数据用于疾病亚型分析
tldr: 整合组织学图像与基因表达数据可关联组织形态与分子特征，但高维、异质性和可解释性差带来挑战。本研究系统比较了Sparse CCA、Joint NMF和AJIVE三种多变量方法在乳腺癌数据上的应用。结果显示各方法捕捉不同且互补的潜在信息。该比较为成像-组学整合的方法选择提供了指导，并指出了未来发展方向。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法缺乏系统比较，用户难以针对实际数据选择合适的多变量整合策略。
method: "以乳腺癌H&E图像和基因表达数据为例，比较Sparse CCA、Joint NMF和AJIVE的方法特性与可解释性。"
result: 三种方法各自捕捉独特且互补的生物学信息，揭示了不同建模假设下的差异性表现。
conclusion: 本研究凸显了各方法的优缺点，为成像-组学整合的方法选择与未来发展提供参考。
---

## 摘要
将组织学图像与基因表达数据整合，为将组织形态与分子特征联系起来以及改善疾病分型提供了一种有前景的方法。然而，由于这些数据集的高维度、跨模态异质性和有限的可解释性，这种整合仍然具有挑战性。多变量方法如稀疏典型相关分析（Sparse CCA）、联合非负矩阵分解（Joint NMF）和基于角度的联合与个体变异解释（AJIVE）已被用于应对这些挑战，通过降低维度同时识别与潜在因子相关的特征，从而增强生物学可解释性。尽管在成像-组学研究中的应用日益增多，对其方法学特性的系统比较仍然有限。因此，用户在实践中往往缺乏如何适当选择这些方法的指导，并且这些方法尽管建模假设不同，却常被视为可互换使用。在此，我们使用乳腺癌的配对H&E图像和基因表达数据作为代表性案例研究，考察这些整合方法的方法学特征、可解释性和互补性质。我们的结果表明，每种方法都捕捉了底层信息的不同但互补的方面。尽管生物学发现源自TCGA-BRCA数据集，但此处识别的方法学见解更广泛地适用于成像-组学整合研究。总体而言，这项比较性综述强调了每种方法的优势和局限性，并概述了未来方法学发展的考虑因素。

## Abstract
Integrating histological images with gene expression data offers a promising approach for linking tissue morphologies to molecular signatures and improving disease subtyping. However, such integration remains challenging due to the high dimensionality of these datasets, cross-modal heterogeneity, and limited interpretability. Multivariate methods such as Sparse Canonical Correlation Analysis (Sparse CCA), Joint Nonnegative Matrix Factorisation (Joint NMF), and Angle-based Joint and Individual Variation Explained (AJIVE), have been used to address these challenges by reducing dimensionality while identifying features associated with latent factors, thereby enhancing biological interpretability. Despite increasing application in imaging-omics research, systematic comparisons of their methodological properties remain limited. Consequently, users often lack guidance on how to appropriately select these methods in practice, and these approaches are frequently treated as interchangeable despite differing modelling assumptions. Here, we use paired H\&E images and gene expression data from breast cancer as a representative case study to examine the methodological characteristics, interpretability, and complementary properties of these integration approaches. Our results show that each method captures distinct yet complementary aspects of the underlying information. Although the biological findings are derived from the TCGA-BRCA datasets, the methodological insights identified here extend more broadly to imaging-omics integration studies. Overall, this comparative review highlights the strengths and limitations of each approach and outlines considerations for future methodological development.