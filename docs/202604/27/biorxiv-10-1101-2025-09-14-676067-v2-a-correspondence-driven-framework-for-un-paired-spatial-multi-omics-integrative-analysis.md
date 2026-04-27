---
title: A Correspondence-Driven Framework for Un-paired Spatial Multi-Omics Integrative Analysis
title_zh: 一种用于非配对空间多组学整合分析的对应驱动框架
authors: "Cai, W., Li, W."
date: 2026-04-21
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.14.676067v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 利用深度学习进行空间多组学整合分析
tldr: 空间多组学技术为理解组织微环境提供了机会，但异构数据的整合仍具挑战。本文提出SpatialFuser，一个基于对应关系的深度学习框架，用于整合非配对的空间表观组、转录组、蛋白组和代谢组数据。该框架通过多头协作图注意力自编码器和迭代优化的最优传输算法，实现了跨分辨率和跨模态的稳健对齐，为揭示复杂的生物变异提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对异构空间多组学数据在几何形状、分辨率和分子模态上的差异，解决非配对数据集整合困难的问题。
method: 提出SpatialFuser框架，利用多头协作图注意力自编码器推断细胞对应关系，并结合几何预匹配与迭代细化的最优传输进行跨切片对齐。
result: 在空间域识别、跨切片对齐和多组学整合方面表现优于现有先进方法，并成功揭示了发育动态和互补的分子信号。
conclusion: SpatialFuser是一个通用且灵活的框架，能够处理多种分析场景，为空间多组学数据的全面整合与生物学发现提供了新途径。
---

## 摘要
空间多组学技术的最新进展为解释组织微环境中的分子特征提供了前所未有的机遇，但在跨异构数据集的整合分析方面仍面临挑战。在这里，我们提出了 SpatialFuser，这是一个用于非配对空间表观组学、转录组学、蛋白质组学和代谢组学整合分析的对应驱动深度学习框架。SpatialFuser 引入了多头协作图注意力自动编码器 (MCGATE)，用于推断多尺度细胞对应关系，从而实现超越预定义空间邻域的空间异质性细粒度表征。通过结合用于粗略初始化的灵活几何预匹配，并利用迭代优化的最优传输推断自适应跨切片对应关系，SpatialFuser 能够跨具有不同几何形状、空间分辨率、发育阶段和分子模态的异构数据集实现稳健整合。基准测试表明，在空间域识别、跨切片比对和多组学整合方面，该方法优于现有的最先进方法。对真实数据集的应用表明，SpatialFuser 能够解析精确的分子模式，揭示发育动态，并恢复跨模态的互补信号。我们方法对弱相关模态的跨分辨率整合进一步揭示了此前被掩盖的生物学变异。我们的框架具有通用性和多功能性，支持定制化的分析场景，并可潜在扩展到新兴组学。亮点：1. 用于空间多组学整合数据分析的统一深度学习框架；2. 在空间识别、比对和多组学整合方面表现优于最先进的方法；3. 前所未有的跨模态分析场景，提供空间多组学的整体视图；4. 具有通用性和多功能性的全面框架设计，适用于定制场景和潜在扩展。

## Abstract
Recent advances in spatial multi-omics technologies provide unprecedented opportunities to interpret molecular features in tissue micro-environments but remain challenging in integrative analysis across heterogeneous datasets. Here we present SpatialFuser, a correspondence-driven deep learning framework for integrative analysis across un-paired spatial epigenomics, transcriptomics, proteomics, and metabolomics. SpatialFuser introduces a Multi-head Collaborative Graph Attention auToEncoder (MCGATE) to infer multi-scale cellular correspondences for fine-grained characterization of spatial heterogeneity beyond predefined spatial neighbourhoods. By incorporating flexible geometric pre-matching for coarse initialization and inferring adaptive cross-slice correspondences via iteratively refined optimal transport, SpatialFuser enables robust integration across heterogeneous datasets with varying geometries, spatial resolutions, developmental stages, and molecular modalities. Benchmarking demonstrates superior performance and reliability against existing state-of-the-art methods in spatial domain identification, cross-slice alignment, and multi-omics integration. Applications to real datasets demonstrate that SpatialFuser resolves precise molecular patterns, reveals developmental dynamics, and recovery of complementary signals across modalities. Cross-resolution integration of weakly correlated modalities by our method further uncovers previously obscured biological variation. Our framework is generalizable and versatile, enabling customized analytical scenarios and potential extension for emerging omics.

HighlightsO_LIA unified deep learning framework for spatial multi-omics integrative data analysis
C_LIO_LISuperior performance against state-of-the-art methods in spatial identification, alignment, and multi-omics integration
C_LIO_LIUnprecedented cross-modality analysis scenarios to offer a holistic view of spatial multi-omics
C_LIO_LIComprehensive framework design with generalizability and versatility for customized scenarios and potential extension
C_LI