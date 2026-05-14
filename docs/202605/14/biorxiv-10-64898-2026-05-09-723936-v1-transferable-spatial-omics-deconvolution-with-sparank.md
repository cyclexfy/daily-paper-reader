---
title: Transferable spatial omics deconvolution with SpaRank
title_zh: 利用 SpaRank 进行可迁移的空间组学反卷积
authors: "Yan, X., Zheng, R., Chen, J., Li, M., Lan, W."
date: 2026-05-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.09.723936v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 将单细胞基础模型应用于空间组学
tldr: 空间转录组反卷积对解析组织细胞景观至关重要，但现有方法易受批次效应影响且需重复训练。本文提出SpaRank框架，通过将空间位点表示为排序特征序列，利用基于排名的编码实现对技术变异的鲁棒性。该方法支持“预训练-迁移”范式，在模拟和真实数据中表现出高精度、跨平台通用性及多模态整合能力，为统一细胞图谱支持的跨背景推理提供了新方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有反卷积方法对单细胞参考数据与空间数据间的批次效应敏感，导致模型在不同实验背景下缺乏通用性。
method: 提出SpaRank框架，将空间位点转化为排序特征序列，并结合门控融合机制实现多模态数据的自适应整合。
result: 预训练模型在多器官淋巴和乳腺癌图谱中实现了跨组织、跨平台的准确反卷积，且在计算效率和鲁棒性上优于现有方法。
conclusion: SpaRank建立了一种可迁移的反卷积范式，能够利用统一图谱在多种生物状态和组学模态下进行直接推理。
---

## 摘要
通过从多细胞空间测量中解析细胞类型组成，反卷积对于解析复杂组织的细胞图谱至关重要。现有的反卷积方法拟合连续的表达值，因此对单细胞参考数据与空间数据之间的批次效应较为敏感，且在每个新场景下都需要重新训练。在此，我们提出了 SpaRank，这是一个上下文感知的框架，通过将空间位点表示为排序特征序列来进行空间反卷积。该方法借鉴了单细胞基础模型的基于排名的编码方式，这种表述方式对技术变异具有内在的鲁棒性，从而实现了“预训练-迁移”范式。在模拟基准测试中，SpaRank 实现了极高的反卷积准确度、对表达扰动的鲁棒性以及显著的计算效率。在实验数据集上，预训练模型可以泛化到多种生物学场景：在多器官淋巴图谱上预训练的模型准确解析了不同组织和测序平台上的细胞类型分布；同样，在整合乳腺图谱上预训练的模型描绘了正常和恶性疾病状态下的细胞类型组成。此外，该框架通过采用门控融合自适应地整合多种组学信号，自然地扩展到多模态空间反卷积，提高了优于单模态方法的准确性。总之，SpaRank 建立了一种可迁移的反卷积范式，使统一的细胞图谱能够支持跨多种生物状态和分析模态的直接、上下文感知推理。

## Abstract
By resolving cell-type compositions from multi-cellular spatial measurements, deconvolution is central to resolving the cellular landscape of complex tissues. Existing deconvolution methods fit continuous expression values and are therefore sensitive to batch effects between single-cell references and spatial data, requiring retraining for each new context. Here we present SpaRank, a context-aware framework that performs spatial deconvolution by representing spots as ranked feature sequences. Adapting the rank-based encodings of single-cell foundation models, this formulation is inherently robust to technical variation, enabling a pretrain-transfer paradigm. On simulated benchmarks, SpaRank achieves strong deconvolution accuracy, robustness to expression perturbations, and substantial computational efficiency. On experimental datasets, pretrained models generalize across diverse biological contexts: a model pretrained on a multi-organ lymphoid atlas accurately resolved cell-type distributions across distinct tissues and sequencing platforms; likewise, a model pretrained on an integrated breast atlas delineated cell-type compositions across normal and malignant disease states. Furthermore, the framework naturally extends to multimodal spatial deconvolution by employing gated fusion to adaptively integrate diverse omics signals, improving accuracy over single-modality approaches. Overall, SpaRank establishes a transferable deconvolution paradigm, enabling unified cellular atlases to support direct, context-aware inference across diverse biological states and profiling modalities.