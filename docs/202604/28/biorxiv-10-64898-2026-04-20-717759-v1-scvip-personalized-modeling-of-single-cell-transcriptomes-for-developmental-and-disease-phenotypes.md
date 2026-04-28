---
title: "scVIP: personalized modeling of single-cell transcriptomes for developmental and disease phenotypes"
title_zh: scVIP：针对发育与疾病表型的单细胞转录组个性化建模
authors: "Lai, H.-Y., Yoo, Y., Tjaernberg, A., Travaglini, K. J., Agrawal, A., Kana, O., van Velthoven, C., Carroll, J. B., Qiao, Q., Mukherjee, S., Fardo, D. W., Lein, E., Gabitto, M. I."
date: 2026-04-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.20.717759v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于疾病表型的细胞类型感知多实例学习
tldr: 单细胞RNA测序虽能揭示细胞异质性，但将细胞状态与个体表型联系起来仍具挑战。本文提出scVIP，一个整合转录谱与表型标记的生成式框架。该方法结合生成模型与细胞类型感知的多实例学习，学习个性化的个体级嵌入，能有效预测发育年龄、疾病进展及神经病理特征，并能协调不同定义的表型数据集，识别与神经退行性疾病相关的关键细胞群和转录程序。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决单细胞转录组数据与个体层面复杂表型（如发育和疾病状态）之间难以建立直接关联的问题。
method: 提出scVIP框架，利用生成模型和细胞类型感知的多实例学习技术来学习个性化的个体级嵌入表示。
result: 该模型成功预测了发育年龄和疾病进展，并能有效整合具有不同表型定义的异构数据集。
conclusion: scVIP为识别疾病相关的细胞群体和揭示神经退行性疾病背后的转录机制提供了一个强大的计算工具。
---

## 摘要
单细胞RNA测序揭示了细胞异质性，但将细胞状态与个体层面的表型联系起来仍然具有挑战性。我们提出了scVIP，这是一个生成式框架，它整合了转录谱和表型标记，利用生成模型和细胞类型感知的多实例学习来学习个性化的个体层面嵌入。scVIP能够预测发育年龄、疾病进展和神经病理学，同时整合具有不同表型定义的多个数据集。该模型突出了与疾病相关的细胞群体以及神经退行性疾病背后的转录程序。

## Abstract
Single-cell RNA sequencing reveals cellular heterogeneity, but linking cellular states to individual-level phenotypes remains challenging. We present scVIP, a generative framework that integrates transcriptional profiles and phenotypic markers to learn personalized individual-level embeddings using generative models and cell-type-aware multi-instance learning. scVIP predicts developmental age, disease progression, and neuropathology, while harmonizing datasets with distinct phenotype definitions. The model highlights disease-relevant cell populations and transcriptional programs underlying neurodegeneration.