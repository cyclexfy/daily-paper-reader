---
title: From unsupervised clustering to atlas-guided annotation in cohort-scale spatial omics with HiCAT
title_zh: 从无监督聚类到图谱引导的队列级空间组学注释：HiCAT
authors: "Huang, J., Shen, X., Smith, Y., Harik, L., Wang, L., Yu, J., Epstein, M., Hu, J."
date: 2026-05-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728266v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 机器学习用于空间组学组织学图像标注
tldr: "空间组学数据依赖病理学家手动标注，耗时且易忽略分子区域异质性。HiCAT框架自动生成病理学家级区域注释，通过无监督聚类和图集引导注释，在七个数据集上中位准确率提升107%。该方法能发现原始标注未覆盖的肿瘤亚区和脑区时空进展相关异质性，支持大规模队列分析和基础模型训练。"
source: biorxiv
selection_source: fresh_fetch
motivation: 病理学家手动标注空间组学数据耗时且仅基于形态学，忽略分子定义区域和样本内异质性。
method: HiCAT结合无监督聚类与图集引导注释，自动生成病理学家均认可的分子区域标注。
result: "在七个数据集中中位准确率较现有方法提升107%，并发现与临床结果相关的肿瘤亚区。"
conclusion: HiCAT提供一致、高粒度且生物学相关的区域标注，实现可扩展下游分析并为基础模型生成训练标签。
---

## 摘要
病理学家注释的组织区域为检查空间组学数据提供了基本参考，但由于需要大量人工操作，此类注释仅适用于有限数量的样本。此外，这些注释源自单个组织学图像中的形态学，可能会忽略分子定义的区域并掩盖样本内异质性。为解决这些局限性，我们提出HiCAT，一个机器学习框架，能够自动生成基于病理学家知识的区域注释，并表征空间组学数据中的区域异质性。在七个数据集中，HiCAT consistently优于最先进的方法，准确率中位数相对提升107%。除了转移病理学家注释，HiCAT还揭示了原始注释未捕获的分子层面区域异质性，包括与临床结局相关的肿瘤亚区域以及与时空疾病进展一致的大脑亚区域。通过在大规模队列中生成一致、高粒度且具有生物学信息的区域注释，HiCAT能够实现可扩展的下游分析，并为空间生物学的基础模型提供训练标签。

## Abstract
Pathologist-annotated tissue regions provide a fundamental reference for examining spatial omics data, yet such annotations are available for a limited number of samples due to the substantial manual effort required. Moreover, these annotations are derived from morphology within individual histology images, which can overlook molecularly defined regions and obscure intra-sample heterogeneity. To address these limitations, we present HiCAT, a machine-learning framework that automatically generates pathologist-informed region annotations and characterizes regional heterogeneity in spatial omics data. Across seven datasets, HiCAT consistently outperforms state-of-the-art methods, achieving a median relative improvement of 107% in accuracy. Beyond transferring pathologist annotations, HiCAT uncovers molecularly informed regional heterogeneity not captured by original annotations, including tumor subregions associated with clinical outcomes and brain subregions aligned with spatiotemporal disease progression. By generating consistent, highly granular, and biologically informative region annotations across large cohorts, HiCAT enables scalable downstream analysis and provides training labels for foundation models in spatial biology.