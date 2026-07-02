---
title: "SpatialFuser: a unified framework for integrative analysis of unpaired spatial multi-omics data"
title_zh: SpatialFuser：用于非配对空间多组学数据整合分析的统一框架
authors: "Cai, W., Li, W."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.14.676067v3.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于非配对空间多组学数据整合的深度学习框架
tldr: 空间多组学技术蓬勃发展，但跨数据集整合分析因异质性和数据不对齐而困难。SpatialFuser提出一种统一深度学习框架，包含多头协作图注意力自编码器、几何预匹配和迭代匹配融合模块，实现未配对空间多组学数据的对齐与整合。在空间域识别、跨切片对齐和多组学整合任务中，它显著优于现有方法，并成功揭示组织微环境中的精细分子模式与发育动态。该框架具有通用性和可扩展性，为新兴组学整合提供了有效方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以处理未配对空间多组学数据的异质性和几何不匹配，亟需一种能整合多模态信息并保留空间结构的统一框架。
method: SpatialFuser包含MCGATE编码器、几何预匹配和迭代匹配融合模块，通过最优传输与对比学习实现跨切片对齐与多模态融合。
result: 在空间域识别、跨切片对齐和多组学整合任务中，SpatialFuser优于现有方法，并揭示弱相关模态间的隐藏生物学变异。
conclusion: SpatialFuser提供了一种通用、可扩展的未配对空间多组学整合方案，有望推动组织微环境研究。
---

## 摘要
近期空间多组学技术的进展为解读组织微环境中的分子特征提供了前所未有的机遇，但跨异质数据集的整合分析仍具挑战性。在此，我们提出SpatialFuser，一个用于跨表观基因组学、转录组学、蛋白质组学和代谢组学的非配对空间多组学数据整合分析的深度学习框架。SpatialFuser包含三个协调模块：MCGATE（多头协作图注意力自编码器），用于学习多尺度空间表示以解读超越预定义空间邻域的细粒度空间异质性；一个可选的几何预匹配模块，用于在组织几何不匹配情况下提供粗初始化；以及一个迭代匹配-融合模块，该模块将几何约束的最优传输匹配与对比学习引导的模态融合相结合，用于跨切片对齐与整合。系统基准测试表明，与现有最先进方法相比，在空间域识别、跨切片对齐和多组学整合方面具有优越性能和可靠性。应用于真实数据集的结果显示，SpatialFuser能够解析精确的空间分子模式，揭示发育动态，并恢复跨模态的互补信号。我们的方法对弱相关模态进行跨分辨率整合，进一步揭示了先前被掩盖的生物学变异。该框架的泛化性和多功能性支持定制化分析场景，并可能扩展到新兴组学。

## Abstract
Recent advances in spatial multi-omics technologies provide unprecedented opportunities to interpret molecular features in tissue microenvironments, but integrative analysis across heterogeneous datasets remains challenging. Here we present SpatialFuser, a deep learning framework for integrative analysis of unpaired spatial multi-omics data across epigenomics, transcriptomics, proteomics, and metabolomics. SpatialFuser consists of three coordinated modules: MCGATE, a Multi-head Collaborative Graph Attention auToEncoder that learns multi-scale spatial representations to decipher fine-grained spatial heterogeneity beyond predefined spatial neighbourhoods; an optional geometric pre-matching module that provides coarse initialization under tissue geometry mismatch; and an iterative matching-fusion module that couples geometry-constrained optimal transport matching with contrastive-learning-guided modality fusion for cross-slice alignment and integration. Systematic benchmarks demonstrate superior performance and reliability compared with existing state-of-the-art methods in spatial domain identification, cross-slice alignment, and multi-omics integration. Applications to real datasets illustrate that SpatialFuser resolves precise spatial molecular patterns, reveals developmental dynamics, and recovers complementary signals across modalities. Cross-resolution integration of weakly correlated modalities by our method further uncovers previously obscured biological variation. The generalizability and versatility of our framework enable customized analytical scenarios and potential extension for emerging omics.