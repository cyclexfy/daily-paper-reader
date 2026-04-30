---
title: Unified imputation of missing data modalities and features in multi-omic data via shared representation learning
title_zh: 通过共享表示学习统一填补多组学数据中缺失的数据模态和特征
authors: "Nambiar, A., Melendez, C., Noble, W. S."
date: 2026-04-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.04.703630v2.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 多组学数据中缺失数据模态的统一填补
tldr: 多组学研究常面临模态缺失和特征缺失的挑战，现有方法难以同时处理这两类问题。本文提出MIMIR框架，利用掩码自编码器学习模态特定表示，并通过共享表示学习将其投影到统一潜空间，实现从任意观测子集进行重构。在TCGA泛癌数据上的实验表明，MIMIR在多种缺失场景下均优于基准方法，并揭示了不同组学间的结构化依赖关系，为异构缺失下的多组学数据补全提供了灵活有效的方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对多组学数据中普遍存在的整模态缺失与特征级缺失共存且现有方法难以统一处理的问题。
method: 采用掩码自编码器学习各模态表示，并将其投影至共享潜空间以实现跨模态的统一重构与补全。
result: 在TCGA数据集的多种缺失场景下，MIMIR的补全性能均优于现有基准方法，并揭示了转录组与表观遗传组间的强对齐关系。
conclusion: 共享表示学习为处理异构缺失模式下的多组学数据补全提供了一个强大且灵活的基础框架。
---

## 摘要
多组学研究通过联合测量多个分子层级，有望提供对生物系统更全面的视角。然而在实践中，此类数据集很少是完整的：许多样本可能缺失整个分子模态，且观测到的模态通常包含大量的特征级缺失。现有的填补方法通常只解决这两个问题中的一个，要么依赖于单一模态内的特征级填补，要么依赖于无法适应任意缺失模态组合的成对转换模型。我们提出了 MIMIR，这是一个用于大体数据统一多组学填补的深度学习框架，通过共享表示学习同时解决缺失模态和缺失值问题。MIMIR 首先使用掩码自编码器学习特定模态的表示，然后将这些表示投影到一个共同的潜空间中，从而能够从观测模态的任何子集进行重建。在来自癌症基因组图谱（TCGA）的泛癌多组学数据上进行的评估表明，MIMIR 在包括完全随机缺失和非随机缺失在内的一系列缺失模态和缺失值场景中，始终优于基准方法。对所学习的共享空间的分析揭示了结构化的跨模态依赖关系，这解释了填补准确性在不同模态间的差异，其中转录组和表观遗传模态形成了强对齐的核心，而拷贝数变异则贡献了更独特的信号。总之，这些结果表明，共享表示学习为异构缺失模式下的多组学填补提供了一个有效且灵活的基础。

## Abstract
Multi-omic studies promise a more comprehensive view of biological systems by jointly measuring multiple molecular layers. In practice, however, such datasets are rarely complete: entire molecular modalities may be missing for many samples, and observed modalities often contain substantial feature-level missingness. Existing imputation approaches typically address only one of these two problems, relying either on feature-level imputation within a single modality or on pairwise translation models that cannot accommodate arbitrary combinations of missing modalities.

We present MIMIR, a deep learning framework for unified multi-omic imputation of bulk data that addresses both missing modalities and missing values through shared representation learning. MIMIR first learns modality-specific representations using masked autoencoders and then projects these representations into a common latent space, enabling reconstruction from any subset of observed modalities. Evaluated on pan-cancer multi-omic data from The Cancer Genome Atlas, MIMIR consistently outperforms baseline methods across a range of missing-modality and missing-value scenarios, including missing completely at random and missing not at random settings. Analysis of the learned shared space reveals structured cross-modal dependencies that explain modality-specific differences in imputation accuracy, with transcriptional and epigenetic modalities forming a strongly aligned core and copy number variation contributing more distinct signal. Together, these results demonstrate that shared representation learning provides an effective and flexible foundation for multi-omic imputation under heterogeneous patterns of missingness.