---
title: "H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling"
authors: "Gu, Y., Wu, Z., Yan, R., Wang, Z., Li, Y., Lin, S., Cui, Y., Lai, H., Luo, X., Zhou, S. K., Yuan, Z., Yao, J."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.717342v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 连接组织病理学与空间多组学的基座模型
tldr: "空间组学技术成本高且难以大规模应用，而常规H&E染色缺乏分子特异性。本研究提出H2O基础模型，通过对比学习将视觉Transformer与大语言模型结合，实现了从H&E图像直接推断空间转录组和蛋白质组。该模型在25种器官的130万个配对样本上训练，不仅在预测精度上超越现有模型，还能恢复生物信号轴，为低成本、大规模的空间多组学分析提供了新途径。"
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决空间组学技术成本高昂、扩展性受限，以及常规病理切片缺乏分子深度信息的问题。
method: 开发了H2O框架，利用对比学习将视觉Transformer与大语言模型结合，以对齐组织形态学与语义分子知识。
result: 在25种器官的大规模数据集上，H2O的预测结果与实测高度一致，且在多个癌症基准测试中优于现有最先进模型。
conclusion: H2O成功将常规病理图像转化为空间多组学分析的入口，显著提升了组织表型分析的能力和可扩展性。
---

## Abstract
Spatial omics technologies have revolutionized the molecular profiling of tissues but remain constrained by high costs and limited scalability. While hematoxylin and eosin (H&E) staining is ubiquitous, it lacks molecular specificity. Here, we present H2O (Histopathology to Omics), a generalist AI framework that bridges the modality gap between histopathology and spatial multi-omics, enabling the direct inference of spatial transcriptomics (ST) and proteomics (SP) landscapes from routine H&E images. H2O integrates Vision Transformers (ViT) with Large Language Models (LLM) via contrastive learning to align histological morphology with semantic molecular knowledge. This cross-modal approach allows the model to incorporate spatial expression profiles into histological pattern recognition, effectively decoding the molecular heterogeneity underlying tissue morphology. Trained on a pan-tissue dataset of 1.3 million paired H&E-spatial patches across 25 organs and cancer types, H2O predicts spatial omics expression from histology with high concordance to sequenced measurements and consistently outperforms state-of-the-art models across three cancer benchmarks. Notably, H2O recovers the MIF-CD74/CD44 signaling axis directly from H&E images, highlighting its capacity to infer biologically meaningful cell-cell communication without molecular profiling. Applying on three additional public cohorts covering fetal and paediatric thymus tissues, human metastatic lymph node, and breast cancer, encompassing human development, 3D spatial frameworks, and integrative multi-omics, H2O yields biologically concordant insights, demonstrating superior accuracy, robustness, and generalizability across real-world applications in diverse scenarios. H2O converts routine histopathology into a portal for spatially resolved multi-omics profiling by computationally generating transcriptomic and proteomic landscapes, thereby enhancing tissue phenotyping and enabling scalable, integrative tissue-atlas construction.

---

## 论文详细总结（自动生成）

以下是对论文《H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling》的结构化深入总结：

### 0. 源代码链接
*   **GitHub 链接**：[https://github.com/TencentAILabHealthcare/H2O](https://github.com/TencentAILabHealthcare/H2O)

### 1. 论文的核心问题与整体含义
*   **研究动机**：常规的 H&E 染色组织病理切片在临床中极其普遍且成本低廉，但其缺乏分子层面的特异性。相比之下，空间组学（转录组学 ST 和蛋白质组学 SP）能提供高分辨率的分子图谱，但受限于高昂的成本、技术复杂性以及对样本（如 FFPE 存档样本）的兼容性。
*   **核心问题**：如何利用人工智能技术，直接从常规 H&E 图像中准确推断出高维的空间分子表达（转录组和蛋白质组），从而弥合形态学与分子生物学之间的鸿沟。

### 2. 论文提出的方法论
H2O 采用了一种基于对比学习的跨模态对齐框架，核心思想是将组织形态学特征锚定到高维分子空间中。
*   **双基座模型架构**：
    *   **图像编码器**：基于 DINOv2 的 Vision Transformer (ViT)，在包含 TCGA 和 GTEx 的 4.5 万个样本（约 5400 万个图像块）上进行预训练，涵盖多种癌症和组织类型。
    *   **分子编码器**：基于 scGPT（单细胞大模型），并在 HEST-1k 空间转录组数据集上进行微调，以学习空间特有的基因表达模式。
*   **关键技术细节**：
    *   **对比学习对齐**：通过最大化配对 H&E 图像块与 ST 表达谱之间的相似性，将分子知识“蒸馏”到图像特征中。
    *   **邻域上下文聚合**：利用 1D 卷积整合中心图像块周围的 8 个邻域块特征，捕捉血管生态位或免疫梯度等宏观组织结构。
    *   **直径条件学习 (FiLM)**：引入特征线性调制（FiLM）层，根据不同平台的点位直径（如 2μm 到 150μm）动态调整特征，解决空间组学平台间的分辨率差异。
*   **算法流程**：输入 H&E 图像块 -> 图像编码器提取特征 -> 结合邻域上下文与直径参数 -> 解码器预测 5033 个高变基因的表达水平。

### 3. 实验设计
*   **数据集**：
    *   **训练集**：TCGA、GTEx（图像预训练）；HEST-1k（1.3M 个配对点位，涵盖 25 种器官）。
    *   **测试与验证集**：HEST-1k 的独立子集（ccRCC 肾癌、PRAD 前列腺癌）；外部验证集 IDCLymphNode（乳腺癌淋巴结转移）。
    *   **应用场景数据集**：HTSA（人类胸腺发育）、OpenST（3D 空间构建）、HTAPP（乳腺癌多组学整合）。
*   **Benchmark 与对比方法**：
    *   对比了 **HisToGene**、**BLEEP**、**DeepPT** 和 **OmiCLIP** 等当前最先进的（SOTA）模型。
*   **评估指标**：Pearson 相关系数 (PCC)、Spearman 秩相关系数 (SRCC)、一致性相关系数 (CCC) 和均方根误差 (RMSE)。

### 4. 资源与算力
*   **算力说明**：文中**未明确列出**具体的 GPU 型号、数量或总训练时长。但考虑到其处理了超过 5400 万个图像块以及使用了 DINOv2 和 scGPT 等大型基座模型，推测该研究依赖于大规模 GPU 集群（如 A100 或 H100 级别）进行训练。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了从 2D 预测到 3D 构建，从发育生物学（胸腺）到肿瘤免疫微环境（淋巴结、乳腺癌）的多个维度。
*   **充分性评价**：
    *   **非常充分**：不仅在标准 Benchmark 上取得了领先，还进行了跨数据集验证、消融实验（验证邻域特征和 FiLM 的有效性）。
    *   **客观性**：通过 3D 渲染和细胞通讯分析（如 MIF-CD74/CD44 轴）验证了预测结果的生物学真实性，而非简单的统计拟合。

### 6. 主要结论与发现
*   **性能领先**：H2O 在所有测试基准上均显著优于现有模型，展现出极强的跨器官和跨平台泛化能力。
*   **生物学发现**：H2O 能够直接从 H&E 图像中恢复出复杂的细胞间通讯网络（如 MIF 信号通路），并能准确捕捉胎儿到出生后的免疫发育轨迹（如 CD19 和 SPP1 的表达演变）。
*   **多组学能力**：模型不仅能预测转录组，还能通过并行解码器预测蛋白质组（SP），且在某些场景下 SP 的预测准确度甚至高于 ST。
*   **3D 潜力**：通过对连续切片的预测，H2O 成功构建了肿瘤侵袭前沿的 3D 分子图谱。

### 7. 优点
*   **知识增强**：通过引入预训练的单细胞大模型（scGPT）作为先验，比纯图像驱动的模型更具生物学解释力。
*   **平台适应性**：FiLM 模块有效解决了空间组学领域长期存在的“分辨率不统一”难题。
*   **多尺度视野**：结合邻域上下文，使模型能够识别超出单个图像块范围的复杂组织模式。

### 8. 不足与局限
*   **稀有组织覆盖**：尽管训练集庞大，但对于极罕见组织或特定病理状态的覆盖可能仍有不足。
*   **非单细胞分辨率**：目前的预测基于固定大小的图像块（Patch），虽然捕捉了区域异质性，但尚未达到真正的单细胞物理分辨率。
*   **预测而非生成**：模型目前主要执行推理任务，未来若能结合生成式 AI，可能在合成全片尺度的超分辨率分子图谱方面有更大突破。
*   **蛋白质组训练受限**：相比于 ST，蛋白质组预测缺乏大规模的预训练编码器支持，目前主要依赖轻量级 MLP 映射。

（完）
