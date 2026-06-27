---
title: "EventHorizon: A Foundation Model for Clinical Flow Cytometry"
title_zh: EventHorizon：临床流式细胞术的基础模型
authors: "Medina Grespan, M., Morrison, M., O'Fallon, B., Shean, R., Spies, N. C., Ng, D."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733197v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 用于临床流式细胞术的自监督基础模型
tldr: 流式细胞术诊断依赖专家手工，现有ML方法需大量标注且泛化性差。本文提出自监督基础模型EventHorizon，采用两阶段分层Transformer和标记感知令牌化，在10万+临床样本上预训练。冻结嵌入的k近邻探测在三个分类任务上性能与全监督基线相当。结果表明该模型产生生物学有意义、面板无关的标本表示，为可扩展诊断支持奠定基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决流式细胞术诊断依赖专家手工且现有机器学习方法泛化性差的问题。
method: 两阶段分层Transformer架构结合标记感知令牌化，采用DINO式自蒸馏在10万+临床样本上预训练。
result: 在17种面板上预训练后，冻结嵌入的k近邻探测在三个分类任务中性能与全监督基线模型相当。
conclusion: EventHorizon产生生物学有意义的、面板无关的标本表示，可支持临床诊断。
---

## 摘要
流式细胞术是诊断血液系统恶性肿瘤的重要工具，但现有的临床工作流程高度依赖于专家的人工解读。现有的机器学习方法通常需要大量标注数据，并且对方案设计、仪器和实验室工作流程的变异性敏感，从而限制了其泛化能力。我们提出了EventHorizon，一个用于临床流式细胞术的自监督基础模型，它能够从异质的多方案数据中生成统一的标本级表示。EventHorizon采用了两阶段层次化Transformer架构，并具备标志物感知的令牌化，使得在不同抗体方案下测量的细胞能够无缝整合到单一的共享潜在空间中。我们使用基于DINO的自蒸馏策略，结合多种流式细胞术特定的数据增强方法，在包含超过10万个临床标本、涵盖17种不同方案的数据集上对模型进行了预训练。我们在三个临床相关的分类任务上评估了生成的嵌入表示，这些任务覆盖了常见和罕见的方案。结果表明，对冻结的EventHorizon嵌入进行简单的k近邻探测，其性能可与完全监督的基线模型以及先前方案特定的自监督模型相媲美。为确保EventHorizon不会仅仅根据给定标本所运行的标志物/方案等特征进行捷径学习，我们对EventHorizon的潜在空间进行了图论分析，结果表明标本嵌入主要按生物学诊断进行组织。综合来看，这些结果表明EventHorizon能够从临床流式细胞术数据中生成具有生物学意义、且与方案无关的标本表示，经过进一步开发和验证，它可能为不同临床实验室环境中可扩展、可重复的诊断支持提供潜在基础。

## Abstract
Flow cytometry is an essential tool for diagnosis of hematologic malignancies, but existing clinical workflows are highly dependent on expert manual interpretation. Existing machine learning approaches typically require extensive labeled data and are sensitive to variability in panel design, instrumentation, and laboratory workflows, limiting their generalizability. We present EventHorizon, a self-supervised foundation model for clinical flow cytometry that produces unified specimen-level representations from heterogeneous multi-panel data. EventHorizon employs a two-stage hierarchical transformer architecture with marker-aware tokenization, enabling seamless integration of cells measured across different antibody panels into a single shared latent space. We pre-train the model using a DINO-inspired self-distillation strategy with a variety of flow cytometry-specific augmentations on a dataset of more than 100,000 clinical specimens across 17 distinct panels. We evaluate the resulting embeddings on three clinically relevant classification tasks spanning common and rare panels, demonstrating that simple k-nearest neighbor probing of frozen EventHorizon embeddings achieves performance comparable to a fully supervised baseline model and a prior panel-specific self-supervised model. To ensure EventHorizon is not simply shortcut learning on features such as the markers/panels run for a given specimen, we perform a graph-theoretic analysis of EventHorizons latent space which argues that specimen embeddings are organized primarily by biological diagnosis. Taken together, these results demonstrate that EventHorizon produces biologically meaningful, panel-agnostic specimen representations from clinical flow cytometry data which, with further development and validation, could provide a potential basis for scalable, reproducible diagnostic support across diverse clinical laboratory settings.