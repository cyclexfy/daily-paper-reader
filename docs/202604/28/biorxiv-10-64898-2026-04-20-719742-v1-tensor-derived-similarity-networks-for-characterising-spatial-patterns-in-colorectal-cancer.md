---
title: Tensor-Derived Similarity Networks for Characterising Spatial Patterns in Colorectal Cancer
title_zh: 用于表征结直肠癌空间模式的张量衍生相似性网络
authors: "Pham, T. D."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.20.719742v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 表征结直肠癌的空间模式
tldr: 本研究针对结直肠癌的空间转录组数据，提出了一种基于张量分解的相似性网络框架，旨在量化肿瘤组织的组织架构。通过将基因表达数据表示为空间结构张量并利用低秩正则多项式模型提取潜在特征，构建了表征区域间空间关系的相似性网络。研究发现，真实组织的组织结构具有显著的约束性，表现出比随机配置更低的密度和异质性，为发现空间生物标志物提供了新方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在利用空间转录组学深入理解结直肠癌的肿瘤异质性及其复杂的空间组织模式。
method: 采用低秩张量分解技术提取空间分子特征，并构建相似性网络及嵌入置换框架进行对比分析。
result: 实验表明真实组织的相似性网络呈现稀疏且有结构的连接模式，且其密度和异质性显著低于随机生成的空间配置。
conclusion: 该框架能有效捕捉肿瘤组织的关键空间模式并提供定量衡量指标，为分析空间转录组数据和发现生物标志物提供了通用方法。
---

## 摘要
空间转录组学使得在组织结构的物理背景下研究基因表达成为可能，为理解肿瘤异质性提供了新机遇。本研究提出了一种用于分析结直肠癌空间组织的张量衍生相似性网络框架。来自四名患者的基因表达数据被表示为空间结构张量，并使用低秩正则多项式模型进行分解，以提取潜在的空间-分子特征。这些特征被用于构建相似性网络，以表征组织区域之间的空间关系。包括相似性、密度和空间异质性在内的全局网络度量揭示了所有患者中稀疏但结构化的连接模式。本文引入了一种嵌入置换框架，在保留特征分布的同时生成随机空间配置。对比分析表明，随机化网络比真实数据表现出更高的相似性、密度和异质性，这表明空间组织约束了网络结构。结果证明，所提出的框架捕捉到了肿瘤组织中具有意义的空间模式，并提供了空间异质性的定量度量。该方法为分析空间转录组数据提供了一种通用方法，在空间生物标志物发现和肿瘤架构表征方面具有潜在应用价值。

## Abstract
Spatial transcriptomics enables the study of gene expression within the spatial context of tissue architecture, offering new opportunities for understanding tumour heterogeneity. This study proposes a tensor-derived similarity network framework for analysing spatial organisation in colorectal cancer. Gene expression data from four patients are represented as spatially structured tensors and decomposed using a low-rank canonical polyadic model to extract latent spatial-molecular features. These features are used to construct similarity networks that characterise spatial relationships between tissue regions. Global network measures, including similarity, density, and spatial heterogeneity, reveal sparse but structured connectivity patterns across all patients. An embedding-permutation framework is introduced to generate randomised spatial configurations while preserving feature distributions. Comparative analysis shows that randomised networks exhibit higher similarity, density, and heterogeneity than real data, indicating that spatial organisation constrains network structure. The results demonstrate that the proposed framework captures meaningful spatial patterns in tumour tissue and provides quantitative measures of spatial heterogeneity. This approach offers a general methodology for analysing spatial transcriptomics data and has potential applications in spatial biomarker discovery and characterisation of tumour architecture.