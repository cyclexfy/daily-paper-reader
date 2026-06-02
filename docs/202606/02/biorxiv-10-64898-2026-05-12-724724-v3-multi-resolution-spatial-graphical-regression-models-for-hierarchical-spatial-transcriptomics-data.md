---
title: Multi-resolution Spatial Graphical Regression Models for Hierarchical Spatial Transcriptomics Data
title_zh: 多层次空间转录组数据的多分辨率空间图回归模型
authors: "Chen, L., Acharyya, S., May, A. M., Udager, A. M., Keller, E. T., Baladandayuthapani, V."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.12.724724v3.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 空间转录组模型用于癌症基因网络推断，与计算病理学相关
tldr: 针对多分辨率空间转录组数据，提出贝叶斯多分辨率空间图形回归（mSGR）模型，允许精度矩阵随层次空间域变化，通过空间结构化边选择和高斯过程先验捕捉基因网络的空间变异。采用增强平均场变分贝叶斯算法实现高效推断。模拟表明网络结构恢复优于现有方法；应用于肾癌数据揭示上皮-间充质转化过渡区更强的调控连接，并识别沿肿瘤梯度的关键枢纽基因，为理解肿瘤微环境空间组织提供新见解。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因网络推断方法忽略肿瘤内分层空间组织，无法捕捉病理梯度相关的调控变化。
method: 提出贝叶斯多分辨率空间图形回归（mSGR），通过空间结构化边选择和高斯过程先验建模多分辨率ST数据的基因网络空间变异。
result: 模拟中网络结构恢复优于对比方法；肾癌数据应用发现过渡区更强调控连接，识别沿肿瘤梯度hub基因。
conclusion: mSGR为多分辨率空间转录组数据提供了推断空间变异基因网络的框架，揭示了肿瘤微环境的空间调控组织。
---

## 摘要
空间转录组学（ST）技术的进步使得能够对肿瘤微环境、肿瘤梯度和基因调控网络进行系统的分子表征。已知癌症进展沿病理梯度变化，然而现有的基因网络推断方法通常忽略了肿瘤内的层次空间组织。我们开发了一个贝叶斯多分辨率空间图回归（mSGR）框架，用于从多分辨率ST数据推断空间变化的基因网络。该模型允许精度矩阵在层次结构化的空间域中变化，捕捉肿瘤内的局部和全局组织。为了识别空间变化的调控关系，我们引入了一种空间结构化边选择策略，该策略根据空间邻近性和病理梯度跨区域借用强度，而高斯过程先验灵活地建模边强度的空间变化。通过增强平均场变分贝叶斯算法与节点级并行回归实现可扩展推断，能够在高维设置中高效估计。模拟研究表明，与竞争方法相比，网络结构的恢复有所改进。将mSGR应用于肾癌的多分辨率ST数据，揭示了上皮-间质转化途径过渡区域中更强的调控连通性，并识别了沿肿瘤梯度的枢纽基因，说明了空间解析的网络分析如何为肿瘤微环境组织提供关键见解。

## Abstract
Advances in spatial transcriptomics (ST) technologies enable systematic molecular characterization of tumor microenvironment, tumor gradients and gene regulatory networks. Cancer progression is known to vary along pathological gradients, yet existing network approaches for gene network inference typically ignore hierarchical spatial organization across the tumor. We develop a Bayesian multi-resolution spatial graphical regression mSGR framework to infer spatially varying gene networks from multi-resolution ST data. The proposed model allows precision matrices to vary across hierarchically structured spatial domains, capturing both local and global organization within the tumor. To identify spatially varying regulatory relationships, we introduce a spatially structured edge selection strategy that borrows strength across regions according to spatial proximity and pathological gradients, while Gaussian-process priors flexibly model spatial variation in edge strengths. Scalable inference is achieved through an augmented mean-field variational Bayes algorithm with node-wise parallel regressions, enabling efficient estimation in high-dimensional settings. Simulation studies demonstrate improved recovery of network structures compared with competing approaches. Applying mSGR to multi-resolution ST data from kidney cancer reveals stronger regulatory connectivity in transitional regions of epithelial-mesenchymal transition pathway and identifies hub genes along the tumor gradient, illustrating how spatially resolved network analysis can provide key insights into tumor microenvironment organization.