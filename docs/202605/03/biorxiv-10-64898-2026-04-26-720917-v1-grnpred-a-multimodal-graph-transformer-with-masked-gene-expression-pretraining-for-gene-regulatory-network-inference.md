---
title: "GRNPred: A Multimodal Graph Transformer with Masked Gene Expression Pretraining for Gene Regulatory Network Inference"
title_zh: GRNPred：一种基于掩码基因表达预训练的多模态图 Transformer，用于基因调控网络推断
authors: "Nguyen, T. M., Hegde, A., Cheng, J."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.26.720917v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 整合基因表达和语义描述的多模态图变换器
tldr: 基因调控网络（GRN）推断面临标注数据稀缺和调控机制复杂的挑战。本文提出GRNPred，一种多模态图Transformer框架，整合了基因表达、功能注释、语义描述及基序先验等多源信息。通过自监督预训练（掩码基因表达重建）和有监督微调两阶段策略，该模型能有效捕捉长程和上下文相关的调控关系，在多个基准数据集上显著优于现有方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对现有GRN推断方法在处理标注数据有限、类别不平衡及复杂非线性调控关系方面的局限性。
method: 采用两阶段策略，先在TF中心子图上进行掩码基因表达重建的自监督预训练，再利用多模态信息进行有监督的调控边预测微调。
result: 在7个基准数据集上表现优异，AUROC和AUPRC分别达到0.94和0.93，显著超越了现有的最先进方法。
conclusion: GRNPred通过结合多模态数据和预训练机制，为鲁棒且准确的基因调控网络重建提供了一种高效的深度学习方案。
---

## 摘要
基因调控网络（GRN）推断是系统生物学中的一个基本问题，旨在从高维基因表达数据中识别转录因子（TF）与靶基因之间的相互作用。由于标记的调控数据有限、严重的类别不平衡以及转录调控的复杂非线性性质，准确的 GRN 重建仍然具有挑战性。在此，我们介绍了 GRNPred，这是一个用于鲁棒 GRN 推断的多模态图 Transformer 框架，它整合了基因表达、功能注释、语义基因描述、调控结合基序先验和基因共表达网络拓扑。GRNPred 遵循两阶段训练策略。在第一个自监督预训练阶段，利用掩码基因表达重建，在以 TF 为中心的基因共表达子图上训练图 Transformer 编码器，使模型能够从无标记数据中学习转录上下文。在第二个有监督微调阶段，使用可用的调控注释对预训练的编码器进行微调，以进行有监督的 TF-靶标边预测。基于 Transformer 的注意力机制使 GRNPred 能够捕捉长程和上下文相关的调控相互作用，而这些相互作用是传统图神经网络难以建模的。在 7 个基准数据集和 3 种调控网络构建上的广泛评估表明，GRNPred 一致优于最先进的 GRN 推断方法，AUROC 分数高达 0.94，AUPRC 分数高达 0.93，同时在不同的生物学背景下保持了强大的鲁棒性。

## Abstract
Gene regulatory network (GRN) inference is a fundamental problem in systems biology, aiming to identify transcription factor (TF)-target gene interactions from high-dimensional gene expression data. Accurate GRN reconstruction remains challenging due to limited labeled regulatory data, severe class imbalance, and the complex, nonlinear nature of transcriptional regulation. Here, we introduce GRNPred, a multimodal graph transformer framework for robust GRN inference that integrates gene expression, functional annotations, semantic gene descriptions, regulatory binding motif priors, and gene co-expression network topology. GRNPred follows a two-stage training strategy. In the first self-supervised pretraining phase, a graph transformer encoder is trained on TF-centered gene co-expression subgraphs using masked gene-expression reconstruction, enabling the model to learn transcriptional context from unlabeled data. In the second supervised fine-tuning stage, the pretrained encoder is finetuned for supervised TF-target edge prediction using available regulatory annotations. Transformer-based attention allows GRNPred to capture long-range and context-dependent regulatory interactions that are difficult to model with conventional graph neural networks. Extensive evaluation across 7 benchmark datasets and 3 regulatory network constructions demonstrates that GRNPred consistently outperforms state-of-the-art GRN inference methods, achieving AUROC scores of up to 0.94 and AUPRC scores of up to 0.93, while maintaining strong robustness across diverse biological contexts.