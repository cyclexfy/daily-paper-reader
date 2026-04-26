---
title: "H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling"
title_zh: H2O：连接组织病理学与空间多组学分析的基础模型
authors: "Gu, Y., Wu, Z., Yan, R., Wang, Z., Li, Y., Lin, S., Cui, Y., Lai, H., Luo, X., Zhou, S. K., Yuan, Z., Yao, J."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.717342v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 利用ViT和LLM连接组织病理学与空间多组学的基础模型
tldr: "本研究提出H2O基础模型，旨在通过常规H&E染色图像直接推断空间转录组和蛋白质组图谱。针对空间组学成本高、难以大规模应用的问题，H2O结合视觉Transformer与大语言模型，通过对比学习对齐组织形态与分子语义。在涵盖25种器官的130万个样本上训练后，该模型在预测精度和泛化性上均优于现有模型，成功揭示了组织形态背后的分子异质性，为低成本、大规模的空间多组学研究提供了新工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: "空间组学技术成本高昂且难以大规模普及，而普及的H&E染色图像缺乏分子特异性。"
method: 开发了H2O框架，利用视觉Transformer与大语言模型进行对比学习，将组织学形态与语义分子知识进行跨模态对齐。
result: 在25种器官的大规模数据集上，H2O预测的空间组学表达与实测高度一致，并能准确识别细胞间通讯信号轴。
conclusion: H2O将常规病理切片转化为空间多组学分析的入口，显著增强了组织表型分析能力并推动了大规模组织图谱的构建。
---

## 摘要
空间组学技术彻底改变了组织的分子分析，但仍受限于高昂的成本和有限的可扩展性。虽然苏木精-伊红（H&E）染色应用广泛，但其缺乏分子特异性。在此，我们提出了 H2O，这是一个通用的 AI 框架，旨在弥合组织病理学与空间多组学之间的模态鸿沟，从而能够直接从常规 H&E 图像中推断空间转录组学（ST）和蛋白质组学（SP）图谱。H2O 通过对比学习将视觉 Transformer（ViT）与大语言模型（LLM）集成，使组织形态学与语义分子知识对齐。这种跨模态方法允许模型将空间表达谱纳入组织形态识别中，从而有效解码组织形态背后的分子异质性。H2O 在涵盖 25 种器官和癌症类型的 130 万个 H&E-空间配对切片的泛组织数据集上进行了训练，其从组织学预测的空间组学表达与测序测量结果高度一致，并在三个癌症基准测试中持续优于现有最先进模型。值得注意的是，H2O 直接从 H&E 图像中恢复了 MIF-CD74/CD44 信号轴，突显了其在无需分子分析的情况下推断具有生物学意义的细胞间通讯的能力。通过在涵盖胎儿和儿科胸腺组织、人类转移性淋巴结和乳腺癌的另外三个公共队列（涉及人类发育、3D 空间框架和综合多组学）上的应用，H2O 产生了生物学一致的见解，展示了在不同场景的实际应用中卓越的准确性、鲁棒性和泛化能力。H2O 通过计算生成转录组和蛋白质组图谱，将常规组织病理学转化为空间分辨率多组学分析的入口，从而增强了组织表型分析，并实现了可扩展的、综合性的组织图谱构建。

## Abstract
Spatial omics technologies have revolutionized the molecular profiling of tissues but remain constrained by high costs and limited scalability. While hematoxylin and eosin (H&E) staining is ubiquitous, it lacks molecular specificity. Here, we present H2O, a generalist AI framework that bridges the modality gap between histopathology and spatial multi-omics, enabling the direct inference of spatial transcriptomics (ST) and proteomics (SP) landscapes from routine H&E images. H2O integrates Vision Transformers (ViT) with Large Language Models (LLM) via contrastive learning to align histological morphology with semantic molecular knowledge. This cross-modal approach allows the model to incorporate spatial expression profiles into histological pattern recognition, effectively decoding the molecular heterogeneity underlying tissue morphology. Trained on a pan-tissue dataset of 1.3 million paired H&E-spatial patches across 25 organs and cancer types, H2O predicts spatial omics expression from histology with high concordance to sequenced measurements and consistently outperforms state-of-the-art models across three cancer benchmarks. Notably, H2O recovers the MIF-CD74/CD44 signaling axis directly from H&E images, highlighting its capacity to infer biologically meaningful cell-cell communication without molecular profiling. Applying on three additional public cohorts covering fetal and paediatric thymus tissues, human metastatic lymph node, and breast cancer, encompassing human development, 3D spatial frameworks, and integrative multi-omics, H2O yields biologically concordant insights, demonstrating superior accuracy, robustness, and generalizability across real-world applications in diverse scenarios. H2O converts routine histopathology into a portal for spatially resolved multi-omics profiling by computationally generating transcriptomic and proteomic landscapes, thereby enhancing tissue phenotyping and enabling scalable, integrative tissue-atlas construction.

---

## 论文详细总结（自动生成）

这是一份关于论文《H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling》的结构化深入总结：

### 0. 论文源代码链接
*   **GitHub 链接**：[https://github.com/TencentAILabHealthcare/H2O](https://github.com/TencentAILabHealthcare/H2O)

### 1. 论文的核心问题与整体含义
*   **研究动机**：空间组学（Spatial Omics）能揭示组织内的分子异质性，但成本极高、技术复杂且难以应用于存档的 FFPE 样本。相比之下，H&E 染色图像虽然普及且廉价，但缺乏分子特异性。
*   **核心问题**：如何利用 AI 技术弥合组织病理形态与空间分子表达之间的模态鸿沟，实现从常规 H&E 图像直接推断高维的空间转录组（ST）和蛋白质组（SP）信息。

### 2. 论文提出的方法论
H2O 采用了一种基于对比学习的跨模态对齐框架，核心思想是将视觉基础模型（Vision FM）锚定在分子语义空间中。
*   **双基础模型对齐**：
    *   **图像端**：基于 DINOv2 训练的视觉 Transformer（ViT），用于提取组织形态特征。
    *   **分子端**：利用 scGPT（单细胞大模型）并在大规模空间转录组数据集（HEST-1k）上进行微调，使其学习空间表达的语义知识。
*   **关键技术细节**：
    *   **对比学习（Contrastive Learning）**：通过最大化配对 H&E 图像块与 ST 表达谱之间的相似度，将分子知识蒸馏到图像编码器中。
    *   **上下文感知预测**：引入邻域块聚合（Neighborhood Aggregation），利用中心块周围的 8 个邻居块提供空间上下文。
    *   **直径条件调制（FiLM）**：使用特征线性调制层（FiLM），根据不同平台的探针/斑点直径（如 2μm 到 150μm）动态调整特征，增强跨平台泛化性。
*   **算法流程**：输入 H&E 图像块 -> 视觉编码器提取特征 -> 结合邻域上下文与直径条件 -> 解码器预测 5000+ 基因的表达水平。

### 3. 实验设计
*   **数据集**：
    *   **训练集**：使用 TCGA、GTEx 及内部乳腺癌数据（共 4.5 万个样本，5400 万个图像块）预训练图像模型；使用 HEST-1k（130 万个配对点，涵盖 25 种器官）进行跨模态训练。
    *   **验证/测试集**：HEST-1k 的预留测试集（ccRCC 肾癌、PRAD 前列腺癌）、IDCLymphNode（外部验证）、HTSA（人类胸腺发育）、OpenST（3D 淋巴结）、HTAPP（乳腺癌多组学）。
*   **Benchmark 与对比方法**：
    *   对比了 **HisToGene**、**BLEEP**、**DeepPT** 和 **OmiCLIP** 等当前最先进的（SOTA）图像转录组预测模型。

### 4. 资源与算力
*   **算力说明**：论文中未明确列出具体的 GPU 型号、数量或总训练时长。但考虑到其训练数据量（5400 万图像块 + 130 万空间组学配对点）以及使用了 ViT 和 scGPT 等大模型，推测其消耗了相当规模的工业级算力集群。

### 5. 实验数量与充分性
*   **实验规模**：
    *   **基准测试**：在 3 个癌症数据集上进行了性能对比。
    *   **多维度验证**：涵盖了时间维度（胸腺发育轨迹）、空间维度（3D 组织重建）和模态维度（转录组+蛋白质组）。
    *   **消融实验**：对邻域上下文、FiLM 模块等进行了有效性验证。
*   **充分性评价**：实验设计非常充分且具有高度的客观性。通过跨器官、跨平台（Visium, Xenium, MERFISH, CODEX）以及跨生物学场景（发育、癌症转移）的验证，证明了模型的鲁棒性。

### 6. 论文的主要结论与发现
*   **预测精度领先**：H2O 在所有基准测试中的皮尔逊相关系数（PCC）和斯皮尔曼相关系数（SRCC）均显著优于现有模型。
*   **发现分子机制**：模型能直接从 H&E 图像中恢复 MIF-CD74/CD44 等关键细胞通讯信号轴。
*   **跨场景泛化**：成功重建了人类胸腺的发育轨迹，并能通过 2D 切片构建 3D 肿瘤浸润前沿的分子图谱。
*   **多组学整合**：证明了图像特征可以同时预测 RNA 和蛋白质水平，且两者结合能更精准地识别肿瘤亚区。

### 7. 优点
*   **知识蒸馏创新**：首次将单细胞大模型（scGPT）的生物学语义引入组织病理图像表征，而非简单的端到端回归。
*   **解决尺度异质性**：通过 FiLM 模块解决了空间组学中不同平台分辨率不一的痛点。
*   **应用价值高**：为临床低成本获取空间多组学信息提供了切实可行的路径，具有极强的转化潜力。

### 8. 不足与局限
*   **稀有组织覆盖**：尽管训练集庞大，但对于极罕见组织或特定病理状态的覆盖可能仍有不足。
*   **非生成式模型**：目前主要基于固定 Patch 进行预测，尚未实现全片尺度的端到端生成。
*   **细胞分辨率限制**：预测仍基于 Patch（224x224 像素）及其上下文，对于真正的单细胞级空间异质性捕捉可能存在平滑效应。
*   **蛋白质组预测依赖**：相比转录组，蛋白质组预测缺乏大规模预训练编码器的支持，目前主要依赖轻量级 MLP 映射。

（完）
