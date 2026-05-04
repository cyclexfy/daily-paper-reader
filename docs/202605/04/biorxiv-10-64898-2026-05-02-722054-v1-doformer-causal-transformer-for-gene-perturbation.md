---
title: "DoFormer: Causal Transformer for Gene Perturbation"
title_zh: DoFormer：用于基因扰动的因果 Transformer
authors: "Karbalayghareh, A., Paull, E., Califano, A."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.02.722054v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 转录组基础模型和多模态Transformer
tldr: DoFormer是一个因果多模态Transformer模型，旨在从单细胞数据中学习基因调控机制并预测未见过的扰动效果。针对现有模型无法区分观测与干预数据且依赖DAG假设的局限，DoFormer通过在注意力机制中引入do算子，实现了对基因扰动的精准建模。实验表明，该模型在扰动预测任务上显著优于现有基准和基础模型，为单细胞基因组学的因果建模提供了新思路。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的单细胞模型难以区分观测与干预数据，且往往依赖不切实际的有向无环图（DAG）假设，限制了对基因扰动效果的准确预测。
method: 提出DoFormer模型，通过在Transformer注意力机制中适配因果do算子，使受扰动基因设定为干预值并阻断其对其他基因的注意力，从而模拟因果干预。
result: DoFormer在多项扰动预测指标上大幅超越了传统基准模型和现有的转录组基础模型。
conclusion: 结合干预感知架构和生物学启发的目标函数对于在单细胞基因组学中进行有效的因果建模至关重要。
---

## 摘要
从单细胞数据中学习因果基因调控机制，并以此预测未见扰动的影响，仍然具有挑战性。仅靠观测性 RNA-seq 数据不足以进行因果建模，而扰动数据则至关重要。经典的因果推理方法通常依赖于不切实际的有向无环图（DAG）假设，且不适合整合多模态数据。目前的转录组基础模型通常也将观测数据和扰动数据同等对待，限制了它们建模扰动的能力。我们提出了 DoFormer，这是一种因果多模态 Transformer，它不作 DAG 假设，并利用丰富的扰动数据来准确预测此前未见的扰动。DoFormer 通过在注意力机制中适配因果 do-算子（do-operator），实现了原则性的计算机模拟（in silico）扰动：被扰动的基因被设置为干预值，并被阻止关注其他基因，从而使模型能够充分区分观测状态与干预状态。我们使用具有生物学启发性的损失函数训练 DoFormer，并使用全面的扰动预测指标对其进行评估。相对于基准模型和先前的基础模型，DoFormer 显著提高了扰动预测的准确性，强调了干预感知架构和基于生物学目标的因果建模在单细胞基因组学中的重要性。

## Abstract
Learning causal gene regulatory mechanisms from single-cell data, and thereby predicting the effects of unseen perturbations, remains challenging. Observational RNA-seq data alone is insufficient for causal modeling, whereas perturbational data is essential. Classical causal inference methods often rely on unrealistic directed acyclic graph (DAG) assumptions and are not well suited to integrating multimodal data. Current transcriptomic foundation models also typically treat observational and perturbational data identically, limiting their ability to model perturbations. We present DoFormer, a causal multimodal Transformer that makes no DAG assumptions and leverages rich perturbational data to accurately predict previously unseen perturbations. DoFormer enables principled in silico perturbations by adapting the causal do-operator within the attention mechanism: the perturbed gene is set to the intervention value and prevented from attending to other genes, allowing the model to fully distinguish observational from interventional regimes. We train DoFormer using biologically informed loss functions and evaluate it with comprehensive perturbation prediction metrics. DoFormer substantially improves perturbation prediction relative to baseline and prior foundation models, underscoring the importance of intervention-aware architectures and biologically grounded objectives for causal modeling in single-cell genomics.