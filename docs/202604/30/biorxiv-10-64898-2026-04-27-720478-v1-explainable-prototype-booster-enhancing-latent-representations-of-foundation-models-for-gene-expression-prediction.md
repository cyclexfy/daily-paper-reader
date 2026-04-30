---
title: "Explainable Prototype Booster: Enhancing Latent Representations of Foundation Models for Gene Expression Prediction"
title_zh: 可解释原型增强器：增强基础模型在基因表达预测中的潜表征
authors: "Li, C., Nguyen, Q."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.27.720478v1.full.pdf"
tags: ["query:cpath"]
score: 9.5
evidence: "利用基础模型从H&E染色组织图像中预测基因标记"
tldr: "本研究针对空间转录组技术成本高且基础模型在基因表达预测中缺乏任务适应性的问题，提出了可解释原型增强器（EP-Booster）。该方法利用生物学先验知识指导可学习原型的构建，对基础模型的图像嵌入进行精炼，从而显著提升了从H&E染色图像预测基因表达的准确性。EP-Booster不仅在多项任务中表现优异，还通过通路级归因提供了强大的生物学可解释性，为精准病理诊断提供了新工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 空间转录组技术成本高昂，且现有基础模型生成的通用图像嵌入缺乏针对基因表达预测任务的优化和生物学可解释性。
method: 提出EP-Booster框架，通过引入生物学先验知识指导可学习原型的构建与训练，从而精炼基础模型的嵌入表示。
result: 在多个癌症数据集和空间转录组平台上，EP-Booster的预测性能一致优于现有方法，并能有效集成到多种基础模型中。
conclusion: 该方法不仅提升了基因表达预测的准确性，还通过通路级归因提供了生物学解释性，在癌症生物标志物预测和生存分析等临床应用中具有巨大潜力。
---

## 摘要
空间转录组学（ST）是一项前沿技术，它在测量基因表达的同时保留空间背景，并生成病理级组织图像。尽管 ST 已促成了许多发现，并在病理诊断和预后中展现出巨大的应用潜力，但该技术仍然耗时且昂贵。从组织学 H&E 染色图像中预测癌症基因标志物的能力可以克服这些技术障碍，为精准和个性化病理学开辟新视野。最近，基础模型在生成 H&E 图像的通用嵌入方面表现出了进步。然而，这些改进后的表征并未针对基因表达预测进行优化，且缺乏特定任务的适应性。为了解决这一局限性，我们提出了可解释原型增强器（EP-Booster），它结合了生物学先验知识来指导可学习原型的构建和训练，以进行嵌入细化，从而提高基因表达预测。重要的是，模型预测通过与原型相关的通路级归因具有内在的可解释性。在多个数据集、癌症类型和空间转录组学平台上的广泛实验表明，EP-Booster 始终优于现有方法。此外，EP-Booster 可以与多种基础模型集成，以增强特定任务的表征，从而在包括癌症生物标志物预测、生存分析和药物反应预测在内的临床相关应用中提高预测性能和生物学可解释性。

## Abstract
Spatial transcriptomics (ST) is a cutting-edge technology that measures gene expression while preserving spatial context and generating pathology-grade tissue images. Although ST has enabled numerous discoveries and demonstrated a huge application potential in pathological diagnosis and prognosis, the technology remains time-consuming and costly. The ability to predict gene markers of cancer from histological H&E-stained tissue images can overcome these technological barriers to open new horizons for precision and personalised pathology. Recently, foundation models have demonstrated improvements in generating general-purpose embeddings of H&E-images. However, these improved representations are not optimized for gene expression prediction and lack task-specific adaptability. To address this limitation, we propose the Explainable Prototype Booster (EP-Booster), which incorporates biological prior knowledge to guide the construction and training of learnable prototypes for embedding refinement, thereby improving gene expression prediction. Importantly, model predictions are inherently interpretable through pathway-level attributions associated with the prototypes. Extensive experiments across multiple datasets, cancer types, and spatial transcriptomics platforms demonstrate that EP-Booster consistently outperforms existing methods. Moreover, EP-Booster can be integrated with diverse foundation models to enhance task-specific representations, thereby improving predictive performance and biological interpretability in clinically relevant applications, including cancer biomarker prediction, survival analysis, and drug response prediction.

---

## 论文详细总结（自动生成）

这是一份关于论文《Explainable Prototype Booster: Enhancing Latent Representations of Foundation Models for Gene Expression Prediction》的结构化深入分析报告：

### 0. 论文的源代码链接
*   **GitHub 链接**：[https://github.com/GenomicsMachineLearning/NCSTAR/tree/main/EP-Booster](https://github.com/GenomicsMachineLearning/NCSTAR/tree/main/EP-Booster)

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：空间转录组学（ST）虽然能提供组织的空间分子信息，但成本极高且耗时。利用深度学习从廉价的 H&E 染色图像中预测基因表达成为一种替代方案。
*   **研究动机**：
    *   现有的病理基础模型（Foundation Models, FMs）虽然能生成强大的图像嵌入（Embeddings），但这些嵌入是通用的，并非针对基因表达预测任务优化，包含大量冗余信息。
    *   现有模型往往缺乏生物学可解释性，难以将图像特征与具体的生物通路联系起来。
    *   在样本量有限的情况下，微调庞大的基础模型并不现实。

### 2. 论文提出的方法论
论文提出了 **EP-Booster（可解释原型增强器）**，这是一个轻量级模块，旨在精炼冻结的基础模型所提取的特征。
*   **核心思想**：通过引入生物学先验知识（基因程序）来指导“可学习原型”的构建，利用交叉注意力机制重构图像嵌入，使其在保留视觉特征的同时注入生物学信号。
*   **关键技术细节**：
    1.  **原型引导的交叉注意力（PGCA）**：将图像嵌入作为 Key/Value，将可学习原型作为 Query，通过注意力机制提取任务相关的特征。
    2.  **原型初始化策略**：
        *   **随机初始化**：作为基准。
        *   **基因程序引导初始化**：利用空间可变基因（SVG）与生物通路（如 MSigDB）的交集构建“基因程序”，使每个原型在初始阶段就代表特定的生物学功能。
    3.  **双重门控机制**：引入原型门控（Prototype Gate）和维度门控（Latent Dimension Gate），自动筛选重要的原型和特征维度。
    4.  **联合优化目标**：
        *   **重构损失（$L_{Recon}$）**：确保精炼后的特征不丢失原始视觉信息。
        *   **回归损失（$L_{Reg}$）**：利用高变基因（HVG）作为监督信号，强制特征与基因表达对齐。
    5.  **通路级解释性**：通过计算回归权重与原型注意力分数的乘积，将预测结果分解到具体的生物通路上。

### 3. 实验设计
*   **数据集与场景**：
    *   **HEST Benchmark**：涵盖 IDC（乳腺癌）、SKCM（黑色素瘤）、LUAD（肺癌）和 PRAD（前列腺癌）。
    *   **ST 平台**：包括高分辨率的 Xenium 和传统的 Visium。
    *   **临床验证集**：TCGA（用于生存分析）和 transNEO（用于药物反应预测）。
*   **Benchmark 与对比方法**：
    *   **对比方法**：ST-Net, HisToGene, TRIPLEX, STEM, BLEEP 等 SOTA 模型。
    *   **基础模型适配**：测试了包括 UNI, CONCH, Virchow 2, GigaPath, H-Optimus-0 在内的 9 种主流病理基础模型。
*   **评估指标**：皮尔逊相关系数（PCC）和均方误差（MSE）。

### 4. 资源与算力
*   **硬件**：使用单张 **NVIDIA L40 GPU (48GB)**。
*   **训练参数**：使用 Adam 优化器，训练 50 个 epoch，Batch Size 为 128。
*   **超参数**：学习率在 [0.00001, 0.005] 之间微调，原型维度选择 {128, 256, 512}。

### 5. 实验数量与充分性
*   **实验规模**：
    *   在 4 种癌症类型和 2 种 ST 平台上进行了广泛测试。
    *   针对 9 种不同的基础模型进行了泛化性验证。
    *   进行了详尽的**消融实验**，验证了 PGCA 模块、门控机制、基因程序初始化以及两种损失函数的各自贡献。
    *   进行了**敏感性分析**（如原型数量、阈值选择等）。
*   **充分性评价**：实验设计非常充分且客观。通过交叉验证确保了结果的稳定性，并引入了外部临床数据集（TCGA, transNEO）进行独立验证，证明了模型不仅在技术指标上领先，在临床应用（生存预测、药敏分析）中也具有实际价值。

### 6. 论文的主要结论与发现
*   **性能卓越**：EP-Booster 在所有测试的数据集和基础模型上均显著优于现有方法，尤其在处理大量基因预测时表现出更强的扩展性。
*   **特征精炼有效**：相比于简单的 PCA 降维，EP-Booster 能更有效地剔除基础模型嵌入中的噪声，保留生物学相关的低方差特征。
*   **生物学一致性**：模型预测的基因表达模式与真实的组织学结构高度吻合，且其解释性分析成功还原了黑色素瘤等癌症的经典调控轴（如 cAMP 和 Wnt 通路）。
*   **临床转化潜力**：基于预测基因生成的风险评分能有效区分患者的生存预后，并能预测乳腺癌患者对曲妥珠单抗等药物的反应。

### 7. 优点
*   **轻量且高效**：无需重新训练或微调庞大的基础模型，仅通过一个轻量级插件即可实现性能飞跃。
*   **生物学驱动**：不同于纯数据驱动的模型，它巧妙地将生物通路先验知识融入架构设计，增强了模型的可信度。
*   **高度泛化**：能够无缝集成到各种不同的病理基础模型中，具有极强的通用性。
*   **端到端解释性**：提供了从图像到通路再到基因的清晰解释路径。

### 8. 不足与局限
*   **SVG 选择策略**：目前的基因程序构建依赖于训练集中共享的 SVG，可能会忽略某些样本特有的空间异质性。
*   **静态原型限制**：原型在训练后是静态的，而同一生物通路在不同微环境下的形态表现可能存在差异。
*   **计算依赖**：虽然 EP-Booster 本身轻量，但仍依赖于高性能基础模型提取的前期特征，对于缺乏算力支持的临床环境仍有一定门槛。

（完）
