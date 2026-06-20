---
title: Sparse Autoencoders Reveal Interpretable Features in Single-Cell Foundation Models
title_zh: 稀疏自编码器揭示单细胞基础模型中的可解释特征
authors: "Pedrocchi, F., Barkmann, F., Joudaki, A., Boeva, V."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.22.681631v3.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 单细胞基础模型的可解释性研究
tldr: 单细胞基础模型(scFM)内部机制不透明。本研究在scGPT、scFoundation和Geneformer三个scFM的隐藏表示上训练稀疏自编码器(SAE)，学习到的特征揭示了多样且复杂的生物和技术信号，且不同模型编码方式存在差异。进一步证明SAE特征与模型行为功能相关：抑制批次相关特征可减少技术变异、改善数据整合；激活药物编码特征能以浓度依赖方式将对照细胞导向药物扰动状态。研究为构建更可解释、可控的单细胞基础模型提供了途径。
source: biorxiv
selection_source: fresh_fetch
motivation: 单细胞基础模型应用广泛但内部机制不透明，需要可解释性方法揭示其学习到的知识。
method: 在scGPT、scFoundation和Geneformer的隐藏表示上训练稀疏自编码器，提取可解释特征。
result: SAE特征捕获生物和技术信号，不同模型编码方式不同；抑制批次特征可改善整合，激活药物特征可导向药物状态。
conclusion: SAE为理解并控制scFM内部机制提供了有效工具，有助于构建更可解释、可控的模型。
---

## 摘要
单细胞基础模型在细胞类型注释、数据整合以及细胞扰动效应预测方面具有应用前景，但其内部机制仍知之甚少。我们通过在三个广泛使用的单细胞基础模型（scGPT、scFoundation和Geneformer）的隐藏表示上训练稀疏自编码器，来研究这些模型的结构。学习到的特征揭示了多样且复杂的生物学和技术信号，这些信号甚至在预训练模型中就已出现。我们还观察到，具有不同训练协议和架构的单细胞基础模型对这些信息的编码方式存在差异。最后，我们证明了稀疏自编码器导出的特征在功能上与模型行为相关，并且可以进行干预。抑制批次相关特征可减少不理想的技术变异，改善数据整合，同时保留核心生物学信号。激活药物编码特征能以浓度依赖的方式将对照细胞引导至药物扰动状态。这些发现为实现更可解释和可控的单细胞基础模型提供了途径。

## Abstract
Single-cell foundation models (scFMs) hold promise for applications in cell type annotation, data integration, and prediction of the effects of cell perturbations, but their internal mechanisms remain poorly understood. We investigate the structure of these models by training sparse autoencoders (SAEs) on the hidden representations of three widely used scFMs: scGPT, scFoundation, and Geneformer.The learned features reveal diverse and complex biological and technical signals, which emerge even in pre-trained models. We also observe that the encoding of this information differs between scFMs with distinct training protocols and architectures. Finally, we demonstrate that SAE-derived features are functionally related to model behavior and can be intervened upon. Suppressing batch-associated features reduces unwanted technical variation and improves data integration while preserving the core biological signal. Activating drug-encoding features steers control cells toward drug-perturbed states in a concentration-dependent manner. These findings provide a path toward more interpretable and controllable single-cell foundation models.