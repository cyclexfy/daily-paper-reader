---
title: Finetuning masking challenges narrow-task evaluation of cell foundation models
title_zh: 微调掩盖了细胞基础模型在窄任务评估中的挑战
authors: "Shakeel, M. H., Shen, M., Mangiola, S."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730272v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 微调掩盖效应下细胞基础模型的评估
tldr: 单细胞基础模型假设预训练数据越多下游性能越好，但该假设未经严格检验。通过大规模缩减预训练数据并微调后发现，性能对数据规模不敏感，存在微调掩盖效应。这表明现有窄任务基准无法体现预训练的真实价值，挑战了当前模型评估标准。未来应转向开放推断、冻结表示和零样本能力等评估方式。
source: biorxiv
selection_source: fresh_fetch
motivation: 检验单细胞基础模型中预训练数据规模越大下游性能越好的核心假设。
method: 在黄金标准任务上系统缩减预训练数据规模，比较微调后的下游性能变化。
result: 下游性能对预训练数据规模高度不敏感，微调掩盖了预训练质量的差异。
conclusion: 当前窄任务基准低估了预训练价值，需采用开放推断等更全面的评估方法。
---

## 摘要
单细胞基础模型是大型自监督深度学习网络，在数百万个细胞转录组上进行了预训练。这些模型有望提供跨不同生物领域可转移的细胞表征，并且在特定任务中使用时，其性能将超过窄范围模型。一个核心假设是，更多的预训练数据会带来更好的下游性能。然而，尽管这一假设至关重要，但在很大程度上仍未得到检验。在这里，我们测试了在大量数据缩减情况下的金标准基准任务的下游性能，结果表明，一旦允许微调，性能对预训练数据大小基本不敏感。这一趋势揭示了一种微调掩盖效应，它抵消了预训练引起的表征质量差异，使得额外预训练规模带来的益处在当前基准设置下基本不可见。这些发现挑战了当前的基准评估标准，这些标准依赖于封闭式的微调任务，而这些任务过于狭窄，无法充分展示预训练的表征价值。同时，在通过常见的窄任务进行评估时，这些发现也挑战了单细胞基础模型发展的主要驱动力。我们建议，下一代基础模型的评估应较少关注高度优化的微调任务上的性能，而更多地关注其支持开放式生物学推理、冻结表征评估和零样本能力的能力。

## Abstract
Single-cell foundation models are large, self-supervised deep learning networks pretrained on millions of cellular transcriptomes. These models promise to deliver cell representations that are transferable across diverse biological domains and, when used in specific tasks, would outperform narrowly scoped models. A central assumption is that more pretraining data translates to better downstream performance. However, despite its centrality, this assumption remains largely untested. Here, we tested downstream performance on gold-standard benchmarking tasks across massive dataset reductions, showing that performance was largely insensitive to pretraining data size once finetuning was allowed. This trend reveals a finetuning masking effect that offsets differences in representation quality induced by pretraining, making the benefit of additional pretraining scale largely invisible under current benchmark settings. These findings challenge current benchmarking standards, which rely on closed-ended finetuning tasks that are too narrow to expose the full representational value of pretraining. They also challenge the main driving force in single-cell foundation-model development when evaluated through common narrow tasks. We propose that the next generation of foundation models should be assessed less by performance on highly optimised finetuning tasks and more by their ability to support open-ended biological inference, frozen-representation evaluation and zero-shot capability.