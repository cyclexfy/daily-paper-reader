---
title: IMAS enables target-aware integration of tumour multiomics to resolve communication-guided regulatory mechanisms
title_zh: IMAS 通过目标感知的肿瘤多组学整合解析通讯引导的调控机制
authors: "Deyang, W., Yamashiro, T., Inubushi, T."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.09.717444v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 整合肿瘤多组学以解析调控机制
tldr: 针对肿瘤多组学数据稀疏且异质性强的问题，本文提出了IMAS框架。该框架利用泛癌单细胞资源，通过共享潜空间建模和目标域自适应技术，实现了多组学数据的增强与机制优先级排序。IMAS能够构建RNA-TF耦合网络并结合细胞间通讯模型，揭示肿瘤微环境中的调控级联反应，为数据受限的肿瘤系统提供了可解释的调控依赖分析工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 肿瘤多组学数据通常具有稀疏、异质且样本量有限的特点，阻碍了对调控机制的稳健且可解释的发现。
method: 提出IMAS框架，利用共享潜空间建模与目标域自适应技术，结合泛癌单细胞资源对目标数据集进行多组学数据增强与机制排序。
result: 在结肠癌独立数据验证中，IMAS显著提升了预测准确性，并揭示了恶性上皮细胞中由通讯引导的调控级联反应。
conclusion: IMAS为数据受限的肿瘤系统提供了一种目标感知且可解释的策略，能够有效构建调控机制发现支架并识别关键的背景特异性依赖。
---

## 摘要
肿瘤多组学数据集通常具有稀疏性、异质性且规模有限，阻碍了对调控机制进行稳健且可解释的发现。在此，我们提出了 IMAS，这是一个用于多组学数据增强和机制优先级排序的目标感知整合框架，它利用泛癌单细胞多组学资源为新的肿瘤数据集提供背景信息，并识别可靠的样本特异性机制假设。IMAS 将共享潜空间建模与目标域自适应相结合，以提高预测与观测到的 RNA 及转录因子（TF）谱图之间的一致性，同时将解释性预测支持集中在目标数据集内。基于这种自适应表示，IMAS 重建了结构化的 RNA-TF 耦合网络，通过配体感知的通讯建模细化了细胞间信号传导，并沿着通讯相关的顺序组织调控程序。在独立的结肠癌数据中，IMAS 提高了聚类解析的一致性，并揭示了跨恶性上皮状态的通讯引导调控级联。一项以 LAMB1 为中心的分析进一步展示了该框架如何支持局部调控结构的渐进式强化，并实现基于扰动的背景特异性依赖关系探测。IMAS 并非穷举预测所有可能的结果，而是提供了一种目标感知且可解释的策略，用于构建一致且可解释的机制发现支架，并在数据有限的肿瘤系统中对调控依赖关系进行优先级排序。

## Abstract
Tumour multiomic datasets are often sparse, heterogeneous and limited in size, hindering robust and interpretable discovery of regulatory mechanisms. Here we present IMAS, a target-aware integrative framework for multiomic data augmentation and mechanism prioritization that leverages a pan-cancer single-cell multiomic resource to contextualize new tumour datasets and identify reliable sample-specific mechanistic hypotheses. IMAS combines shared latent-space modelling with target-domain adaptation to improve correspondence between predicted and observed RNA and TF profiles while concentrating explanatory predictive supports within the target dataset. Building on this adapted representation, IMAS reconstructs structured RNA-TF coupling networks, refines intercellular signaling through ligand-informed communication modelling, and organizes regulatory programs along communication-associated ordering. In independent colon cancer data, IMAS improved cluster-resolved correspondence and revealed communication-guided regulatory cascades across malignant epithelial states. A LAMB1-centred analysis further demonstrates how the framework supports progressive reinforcement of local regulatory structure and enables perturbation-based probing of context-specific dependencies. Rather than exhaustively predicting all possible outcomes, IMAS provides a target-aware and interpretable strategy to construct consistent and interpretable mechanism-discovery scaffolds and prioritize regulatory dependencies in data-limited tumour systems.