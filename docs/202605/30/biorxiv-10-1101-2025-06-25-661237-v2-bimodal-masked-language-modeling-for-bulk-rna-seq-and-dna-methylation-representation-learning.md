---
title: Bimodal masked language modeling for bulk RNA-seq and DNA methylation representation learning
title_zh: 双峰掩码语言建模用于批量RNA-seq和DNA甲基化表示学习
authors: "Gelard, M., Benkirane, H., Pierrot, T., Richard, G., Cournede, P.-H."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.25.661237v2.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 双模态掩码语言建模用于RNA-seq和DNA甲基化表示学习在癌症中
tldr: 肿瘤诊断依赖多模态数据，但转录组和DNA甲基化等高维数据的整合面临困难。本文提出双峰掩码语言模型，利用自监督学习联合表示bulk RNA-seq和DNA甲基化，并通过减少内存占用的架构处理长序列。该双峰嵌入在癌症类型分类和生存预测任务上达到SOTA性能，且引入的鲁棒学习框架能在缺失模态时仍保持下游任务效果，增强了临床适用性。
source: biorxiv
selection_source: fresh_fetch
motivation: 转录组与DNA甲基化数据的高维性及模态整合困难，限制了多模态模型在肿瘤临床中的应用。
method: 提出双峰掩码语言模型，通过自监督学习联合编码bulk RNA-seq和DNA甲基化，并设计低内存架构处理长序列。
result: 双峰嵌入在癌症分类和生存预测上达到SOTA，且鲁棒框架在模态缺失时仍保持高性能。
conclusion: 该工作为多模态组学数据的有效融合提供了新范式，并提升了在实际临床中的鲁棒性。
---

## 摘要
肿瘤学家越来越依赖多种模态来模拟疾病的复杂性。在这种背景下，转录组和表观遗传数据已被证明特别有用，并在临床应用中发挥着日益重要的作用。然而，将它们整合到多模态模型中仍然是一个挑战，特别是考虑到它们的高维性。在这项工作中，我们提出了一种新颖的双峰模型，该模型利用掩码语言建模的自监督学习，共同学习批量RNA-seq和DNA甲基化的表示。我们实现了一种架构，减少了通常归因于纯Transformer模型在处理长序列时的内存占用。我们证明了获得的双峰嵌入可以用于微调癌症类型分类和生存模型，与单峰模型相比，达到了最先进的性能。此外，我们引入了一个鲁棒的学习框架，即使在缺失模态的情况下也能保持下游任务性能，增强了模型在真实临床环境中的适用性。

## Abstract
Oncologists are increasingly relying on multiple modalities to model the complexity of diseases. Within this landscape, transcriptomic and epigenetic data have proven to be particularly instrumental and play an increasingly vital role in clinical applications. However, their integration into multimodal models remains a challenge, especially considering their high dimensionality. In this work, we present a novel bimodal model that jointly learns representations of bulk RNA-seq and DNA methylation leveraging self-supervision from masked language modeling. We implement an architecture that reduces the memory footprint usually attributed to purely transformer-based models when dealing with long sequences. We demonstrate that the obtained bimodal embeddings can be used to fine-tune cancer-type classification and survival models that achieve state-of-the-art performance compared to unimodal models. Furthermore, we introduce a robust learning framework that maintains downstream task performance despite missing modalities, enhancing the model's applicability in real-world clinical settings.