---
title: "CodeCytos: AI-assisted spatial molecular imaging analysis via code-augmented agent action space"
title_zh: CodeCytos：通过代码增强的智能体动作空间实现AI辅助空间分子成像分析
authors: "Vo, H. Q., Ly, S. T., Wan, Z., Nguyen, A.-V., Zhao, H., Sheng, J., Wong, S. T. C., Nguyen, H. V."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.30.728935v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 计算病理学研究工具
tldr: 传统组织图像分析软件需要手动操作且缺乏代码集成，限制了空间分子成像研究的效率和可扩展性。CodeCytos提出编码推理代理框架，通过动态可编程交互支持自定义空间细胞特征探索。在四种不同组织数据集上的评估表明，即使使用最小提示和领域外少样本示例，CodeCytos仍优于基线方法。该工作凸显了代码驱动推理代理在加速生物标志物发现中的潜力。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统空间分析工具依赖手动流程且仅支持固定特征集，缺乏代码集成和灵活性，难以应对复杂研究需求。
method: 提出CodeCytos，基于代码增强的推理代理框架，通过动态编程交互实现自定义空间细胞特征分析与自动化流程。
result: 在四个数据集上，CodeCytos在最小提示设置下结合领域无关少样本示例，显著优于传统基线方法。
conclusion: 编码驱动的推理代理可有效支持空间分子成像中的自定义特征探索，有望加速生物标志物发现。
---

## 摘要
传统的组织图像分析软件为细胞分析提供了基础功能，包括分割、形态特征提取和空间组织分析；然而，这些工具通常需要手动干预，缺乏与代码驱动自动化的无缝集成，限制了复杂空间组织研究的效率和可扩展性，同时由于仅支持一组固定的预定义空间细胞特征，对自定义分析的灵活性有限。为解决这些局限性，我们提出了CodeCytos，一个基于编码的推理智能体框架，能够实现对空间分子成像数据的动态、可编程交互，并简化跨不同研究需求的自定义空间细胞特征的探索。我们通过四个专家策划的数据集（涵盖不同组织类型，包括额叶皮层、非小细胞肺癌、胰腺和扁桃体）的案例研究展示了其实用性，并在现实的最小提示设置下进行评估，其中生物科学家提出简单问题，无需特定任务指令或先验上下文知识，并以多种具有强大编码能力的大型语言模型作为骨干进行基准测试。我们进一步证明，纳入从空间分析领域外随机采样的领域无关的少量样本上下文内编码推理示例，能够在不需昂贵专家制作的领域内演示的情况下显著提升性能；总体而言，CodeCytos优于基线方法，凸显了代码驱动推理智能体在支持空间分子成像中自定义特征探索和加速生物标志物发现的潜力。

## Abstract
Conventional tissue image analysis software provides foundational capabilities for cellular analysis, including segmentation, morphological feature extraction, and spatial organization analysis; however, these tools often require manual intervention and lack seamless integration with code-driven automation, limiting efficiency and scalability for complex spatial tissue studies, while also offering limited flexibility for custom analyses by supporting only a fixed set of predefined spatial cellular features. To address these limitations, we propose CodeCytos, a coding-based reasoning agent framework that enables dynamic, programmable interaction with spatial molecular imaging data and streamlines the exploration of custom spatial cellular features across diverse research needs. We demonstrate its utility through case studies on four expert-curated datasets spanning distinct tissue types, including frontal cortex, non-small-cell lung cancer, pancreas, and tonsil, and evaluate it under a realistic minimal prompt setting in which bioscientists pose simple questions without task-specific instructions or prior contextual knowledge, benchmarking multiple large language model backbones with strong coding capabilities. We further show that incorporating domain-agnostic few-shot in-context coding-reasoning examples, randomly sampled from outside the spatial analysis domain, substantially improves performance without requiring costly expert-crafted in-domain demonstrations; overall, CodeCytos outperforms baseline approaches, highlighting the potential of code-driven reasoning agents to support custom feature exploration in spatial molecular imaging and accelerate biomarker discovery.