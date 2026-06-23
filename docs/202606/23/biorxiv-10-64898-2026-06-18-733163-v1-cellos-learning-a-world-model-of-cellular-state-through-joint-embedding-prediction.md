---
title: "CellOS: Learning a World Model of Cellular State through Joint Embedding Prediction"
title_zh: CellOS：通过联合嵌入预测学习细胞状态的世界模型
authors: "Zhou, Q., Le, Y., Qi, X., Chang, S., Lu, H., Wu, Y., Wang, H., Ran, R., li, x."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733163v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 从配对表达和感知数据学习细胞状态的多视图基础模型
tldr: 现有单细胞基础模型多从单一基因表达视图学习，难以捕捉细胞状态的互补信息。CellOS提出多视图框架，结合表达与感知视图，通过因果语言建模、密集到混合专家扩展和LLM-JEPA对齐的三阶段训练，在3.9亿细胞上训练了120亿参数模型。在细胞注释和扰动响应预测任务中超越当前最优模型，同时保持稳健的批次整合能力。该工作表明，互补视图的预测对齐为实现表示中心的细胞世界模型和可迁移AI虚拟细胞提供了可扩展路径。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞基础模型局限于单视图学习，无法显式整合互补的细胞状态信息。
method: 结合表达与感知视图，采用因果语言建模、密集到混合专家扩展和LLM-JEPA潜在空间对齐的三阶段训练策略。
result: 120亿参数模型在细胞状态注释和扰动响应预测上超越SOTA，且批次整合性能稳健。
conclusion: 多视图预测对齐为实现表示中心的细胞世界模型和可迁移AI虚拟细胞提供了可行路径。
---

## 摘要
基于单细胞转录组学学习的基础模型对于构建能够表示、查询和预测细胞状态的AI虚拟细胞至关重要。然而，当前大多数单细胞基础模型仅从单一基因表达视图学习，并主要通过重构或下一标记预测进行优化。因此，它们能够捕捉表达丰度，但无法明确协调细胞状态的互补视图。在此，我们提出CellOS，一个多视图基础模型，通过配对的表达和感知视图学习细胞表征。CellOS通过可扩展的三阶段训练策略整合互补视图：因果细胞句子语言建模、功能保持的密集到专家混合扩展，以及通过LLM-JEPA目标的潜在空间对齐。利用该框架，我们在3.905亿个单细胞转录组上训练了一个120亿参数的模型。在涵盖细胞状态注释、批次整合和扰动响应预测的多个基准测试中，CellOS在细胞状态注释和扰动响应预测上持续优于最先进的单细胞基础模型，同时保持稳健的批次整合。这些结果表明，互补细胞视图之间的预测对齐为构建以表征为中心的细胞世界模型和可迁移的AI虚拟细胞提供了一条可扩展的路径。

## Abstract
Foundation models learned from single-cell transcriptomes are central to the prospect of AI virtual cell that can represent, query and predict cellular state. However, most current single-cell foundation models learn from a single view of gene expression and are optimized primarily through reconstruction or next-token prediction. As a result, they capture expression abundance but can-not explicitly reconcile complementary views of cellular state. Here we present CellOS, a multi-view foundation model that learns cellular representations from paired expression and perception views. CellOS integrates complementary views through a scalable three-stage training strategy that combines causal cell-sentence language modelling, function-preserving dense-to-mixture-of-experts expansion and latent-space alignment via an LLM-JEPA objective. Using this framework, we trained a 12-billion-parameter model on 390.5 million single-cell transcriptomes. Across diverse benchmarks spanning cell-state annotation, batch integration and perturbation-response prediction, CellOS consistently outperformed state-of-the-art single-cell foundation models in cell-state annotation and perturbation-response prediction while preserving robust batch integration. Together, these results suggest that predictive alignment between complementary cellular views provides a scalable path toward representation-centric cellular world models and transferable AI virtual cells.