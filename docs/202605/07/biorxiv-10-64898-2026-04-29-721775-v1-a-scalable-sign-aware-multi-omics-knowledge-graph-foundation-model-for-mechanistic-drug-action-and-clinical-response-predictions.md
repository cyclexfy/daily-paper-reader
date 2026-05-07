---
title: A Scalable Sign-Aware Multi-Omics Knowledge Graph Foundation Model for Mechanistic Drug Action and Clinical Response Predictions
authors: "Mottaqi, M., Zhang, S., Adoremos, I., Zhang, P., Xie, L."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.29.721775v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于临床反应的大规模多组学知识图谱基础模型
tldr: 本研究针对现有生物医学知识图谱缺乏符号化（激活/抑制）逻辑的问题，提出了SIGMA-KG大规模符号化多组学知识图谱及FLASH轻量化符号异构图神经网络。通过在包含化学基因组、转录组和临床数据的图谱上进行自监督预训练，FLASH能够捕捉生物路径中的极性效应。实验证明，该模型在药物作用机制预测、临床反应建模等任务中优于多种SOTA基准，并成功预测了具有高临床验证率的候选药物，为药物研发提供了可扩展且具解释性的机制推理框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有生物医学知识图谱多为无符号关联，无法区分分子间的激活或抑制作用，限制了对药物作用机制的理解和临床预测的准确性。
method: 开发了集成极性信息的SIGMA-KG图谱，并提出基于结构平衡原理的FLASH模型，通过自监督预训练学习跨多组学尺度的符号化表示。
result: "FLASH在药物作用模式、临床反应及药物相互作用预测等任务中表现优异，且在药物重定向任务中取得了69.6%的外部临床验证成功率。"
conclusion: SIGMA-KG与FLASH构建了一个可扩展的符号感知框架，显著提升了药物发现、多药联用设计及临床安全性评估的预测精度。
---

## Abstract
Mechanistically predicting the consequences of drug action requires distin-guishing whether molecular interactions are activating or inhibitory, yet most biomedical knowledge graphs and graph neural networks represent biology as unsigned associations. This limitation obscures regulatory logic, restricts mechanistic interpretability and reduces the accuracy of downstream therapeutic predictions. Existing approaches are further constrained by limited chemical coverage and insufficient integration of molecular and clinical data across biological scales. Here we present SIGMA-KG (SIGned Multi-omics Atlas Knowledge Graph), a large-scale signed multi-omics knowledge atlas, and FLASH (Fast Lightweight Architecture for Signed Heterogeneous GNN), a fast and lightweight signed heterogeneous graph neural network for foundation-model pretraining on biomedical knowledge graphs. SIGMA-KG integrates chemogenomic perturbations beyond approved drugs with transcriptomic, proteomic and clinical data, explicitly encoding the direction and polarity of biological and phenotypic effects. FLASH enables efficient self-supervised pretraining on this signed atlas at scale, learning transferable representations that preserve how activating and inhibitory effects compose across multi-hop biological pathways through structural balance principles. Across multiple downstream tasks (without task-specific fine-tuning), including target-specific mode-of-action prediction, drug-induced clinical response modeling and drug-drug interaction prediction, the pretrained FLASH foundation model consistently outperforms or matches nine state-of-the-art unsigned, relational and signed graph baselines while substantially improving computational efficiency. We further demonstrate the translational utility of FLASH through explainable inductive drug repurposing, identifying novel ther-apeutic candidates for four complex diseases with a 69.6% external clinical validation success rate. Together, SIGMA-KG and FLASH provide a scalable, sign-aware framework for mechanistic latent-space reasoning, advancing the predictive accuracy of drug discovery, polypharmacy design, and clinical safety assessment.