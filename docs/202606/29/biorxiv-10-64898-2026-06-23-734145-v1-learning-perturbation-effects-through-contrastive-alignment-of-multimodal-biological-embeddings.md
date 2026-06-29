---
title: Learning Perturbation Effects Through Contrastive Alignment of Multimodal Biological Embeddings
title_zh: 通过多模态生物嵌入的对比对齐学习扰动效应
authors: "Long, W., Liu, T., Szalata, A., Theis, F. J., Xue, L., Zhao, H."
date: 2026-06-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.23.734145v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 提出CLIP风格的多模态学习，对齐转录组、文本和图像嵌入
tldr: 现有方法局限于单模态且未利用外部语义知识，难以跨模态泛化。PertOmni采用CLIP风格框架，通过对比学习对齐转录组、文本和图像嵌入，并使用掩码对比目标增强细胞类型内区分。在双向检索、药物-基因互作推断和扰动预测任务上均优于基线方法。该工作首次实现多模态扰动效应的统一表征，显著提升跨数据集泛化能力。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法局限于单模态且未利用外部语义知识，限制跨数据集和扰动类型的泛化能力。
method: 提出PertOmni，采用CLIP风格的对比学习联合训练共享转录组编码器和数据集特定文本编码器，并使用掩码对比目标强调细胞类型内区分。
result: 在双向检索、药物-基因互作推断和扰动预测任务上，PertOmni持续优于强基线方法。
conclusion: PertOmni通过多模态对齐有效整合外部语义知识，为扰动效应表征提供了统一的框架。
---

## 摘要
多模态单细胞扰动筛选为表征遗传和化学干预对细胞状态的影响提供了一种可扩展的方法。然而，大多数现有的表示学习方法仅针对单一扰动模态，且未能明确整合外部语义知识，这限制了它们在跨数据集和扰动类型中的泛化能力。在此，我们提出PertOmni，一种CLIP风格的多模态表示学习框架，该框架将转录组扰动信号与精心挑选的基因和化合物描述的文本嵌入，以及来自细胞成像的嵌入进行对齐。PertOmni使用掩码对比目标联合训练共享的转录组编码器和数据集特定的文本编码器，该目标强调细胞类型内的区分，同时减轻由细胞类型异质性引起的混杂效应。我们在小分子和CRISPRi扰动数据集上评估了生成的联合嵌入空间，包括双向检索、药物-基因相互作用推断和扰动预测，并展示了对强基线方法的一致改进。

## Abstract
Multimodal single-cell perturbation screens offer a scalable approach for characterizing the effects of genetic and chemical interventions on cellular state. However, most existing representation-learning methods are tailored to a single perturbation modality and fail to explicitly incorporate external semantic knowledge, which limits their ability to generalize across datasets and perturbation types. Here, we introduce PertOmni, a CLIP-style multimodal representation-learning framework that aligns transcriptomic perturbation signatures with text-derived embeddings of curated genes and compound descriptions, as well as image-derived embeddings from cell paintings. PertOmni jointly trains a shared transcriptomic encoder and dataset-specific text encoders using a masked contrastive objective that emphasizes within-cell-type discrimination while mitigating confounding effects arising from cell-type heterogeneity. We evaluate the produced joint embedding space on bi-directional retrieval, drug-gene interaction inference, and perturbation prediction across both small-molecule and CRISPRi perturbation datasets, and demonstrate consistent improvements over strong baseline methods.