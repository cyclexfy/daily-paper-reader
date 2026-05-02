---
title: "H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling"
title_zh: H2O：连接组织病理学与空间多组学分析的基础模型
authors: "Gu, Y., Wu, Z., Yan, R., Wang, Z., Li, Y., Lin, S., Cui, Y., Lai, H., Luo, X., Zhou, S. K., Yuan, Z., Yao, J."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.717342v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 连接组织病理学图像与空间多组学的视觉语言大模型框架
tldr: "空间组学技术成本高且难以大规模应用，而常规H&E染色缺乏分子特异性。本研究提出H2O框架，通过对比学习将视觉Transformer与大语言模型结合，实现了从H&E图像直接推断空间转录组和蛋白质组。该模型在包含25种器官的130万个样本上训练，在多个癌症基准测试中表现优于现有模型，并能恢复生物信号轴，为低成本、大规模的空间多组学分析提供了新途径。"
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决空间组学技术成本高昂且难以普及，而常规病理切片缺乏深层分子信息的问题。
method: 开发了H2O框架，利用对比学习将视觉Transformer与大语言模型结合，以对齐组织形态学与语义分子知识。
result: 在25种器官的大规模数据集上，H2O预测的空间组学表达与实测高度一致，且在多个癌症基准测试中超越了现有最先进模型。
conclusion: H2O成功将常规病理图像转化为空间多组学分析的入口，显著提升了组织表型分析的效率和可扩展性。
---

## 摘要
空间组学技术彻底改变了组织的分子分析，但仍受限于高昂的成本和有限的可扩展性。虽然苏木精-伊红（H&E）染色无处不在，但它缺乏分子特异性。在此，我们提出了 H2O（Histopathology to Omics），这是一个通用的 AI 框架，旨在弥合组织病理学与空间多组学之间的模态鸿沟，从而能够从常规 H&E 图像中直接推断空间转录组学（ST）和蛋白质组学（SP）图谱。H2O 通过对比学习将视觉 Transformer（ViT）与大语言模型（LLM）集成，使组织形态学与语义分子知识对齐。这种跨模态方法允许模型将空间表达谱纳入组织学模式识别中，从而有效地解码组织形态背后的分子异质性。H2O 在涵盖 25 种器官和癌症类型的 130 万个 H&E-空间配对切片的泛组织数据集上进行了训练，它能以与测序测量结果高度一致的准确度从组织学中预测空间组学表达，并在三个癌症基准测试中始终优于现有最先进的模型。值得注意的是，H2O 直接从 H&E 图像中恢复了 MIF-CD74/CD44 信号轴，突显了其在无需分子分析的情况下推断具有生物学意义的细胞间通讯的能力。在涵盖胎儿和儿科胸腺组织、人类转移性淋巴结和乳腺癌的另外三个公共队列（涉及人类发育、3D 空间框架和综合多组学）上的应用表明，H2O 产生了生物学一致的见解，在不同场景的现实应用中展示了卓越的准确性、鲁棒性和泛化能力。H2O 通过计算生成转录组和蛋白质组图谱，将常规组织病理学转化为空间分辨率多组学分析的入口，从而增强了组织表型分析，并实现了可扩展的、综合性的组织图谱构建。

## Abstract
Spatial omics technologies have revolutionized the molecular profiling of tissues but remain constrained by high costs and limited scalability. While hematoxylin and eosin (H&E) staining is ubiquitous, it lacks molecular specificity. Here, we present H2O (Histopathology to Omics), a generalist AI framework that bridges the modality gap between histopathology and spatial multi-omics, enabling the direct inference of spatial transcriptomics (ST) and proteomics (SP) landscapes from routine H&E images. H2O integrates Vision Transformers (ViT) with Large Language Models (LLM) via contrastive learning to align histological morphology with semantic molecular knowledge. This cross-modal approach allows the model to incorporate spatial expression profiles into histological pattern recognition, effectively decoding the molecular heterogeneity underlying tissue morphology. Trained on a pan-tissue dataset of 1.3 million paired H&E-spatial patches across 25 organs and cancer types, H2O predicts spatial omics expression from histology with high concordance to sequenced measurements and consistently outperforms state-of-the-art models across three cancer benchmarks. Notably, H2O recovers the MIF-CD74/CD44 signaling axis directly from H&E images, highlighting its capacity to infer biologically meaningful cell-cell communication without molecular profiling. Applying on three additional public cohorts covering fetal and paediatric thymus tissues, human metastatic lymph node, and breast cancer, encompassing human development, 3D spatial frameworks, and integrative multi-omics, H2O yields biologically concordant insights, demonstrating superior accuracy, robustness, and generalizability across real-world applications in diverse scenarios. H2O converts routine histopathology into a portal for spatially resolved multi-omics profiling by computationally generating transcriptomic and proteomic landscapes, thereby enhancing tissue phenotyping and enabling scalable, integrative tissue-atlas construction.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **H2O (Histopathology to Omics)** 的通用人工智能框架，旨在通过常规的 H&E 染色组织病理学图像直接推断空间多组学（转录组和蛋白质组）信息。

以下是对该论文的结构化总结：

### 0. 论文的源代码链接
*   **GitHub 链接**：[https://github.com/TencentAILabHealthcare/H2O](https://github.com/TencentAILabHealthcare/H2O)

### 1. 论文的核心问题与整体含义
*   **研究动机**：空间组学技术（如 ST 和 SP）虽然能提供高分辨率的分子图谱，但成本极高、技术复杂，且难以应用于临床中大量存在的福尔马林固定石蜡包埋（FFPE）存档样本。
*   **核心问题**：如何利用广泛可得、成本低廉的 H&E 染色图像，通过 AI 模型准确预测其背后的分子异质性，从而弥合形态学与分子生物学之间的鸿沟。

### 2. 论文提出的方法论
H2O 采用了一种**跨模态对比学习框架**，将组织病理学特征锚定在高维分子空间中。
*   **核心思想**：利用预训练的单细胞/空间转录组基础模型（如 scGPT）作为“教师”，引导图像基础模型（ViT）学习具有分子语义的形态特征。
*   **关键技术细节**：
    1.  **图像编码器**：基于 DINOv2 预训练的 ViT，并在大规模 FFPE 和新鲜冷冻组织数据集上进一步微调。
    2.  **组学编码器**：使用在 130 万个空间点上微调过的 scGPT 模型，捕捉基因间的依赖关系。
    3.  **对比学习对齐**：通过 CLIP 风格的对比损失函数，使图像嵌入与组学嵌入在潜在空间中对齐。
    4.  **上下文感知预测**：引入邻域补丁（Neighbor patches）聚合机制和 **FiLM（特征线性调制）层**。FiLM 层根据空间组学平台的“点直径”（Spot diameter）动态调整特征，解决了不同平台分辨率不一的问题。
    5.  **多模态解码器**：基于对齐后的特征，通过轻量级 MLP 解码器预测基因表达或蛋白质丰度。

### 3. 实验设计
*   **数据集**：
    *   **预训练**：使用 TCGA、GTEx 及内部乳腺癌数据集（共 4.5 万个样本，5400 万个图像块）。
    *   **对齐训练**：HEST-1k 数据集（涵盖 25 种器官，130 万个配对的 H&E-ST 样本点）。
    *   **独立验证**：HTSA（人类胸腺发育）、OpenST（3D 转移性淋巴结）、HTAPP（乳腺癌多组学）。
*   **Benchmark 与对比方法**：
    *   在 ccRCC（肾癌）和 PRAD（前列腺癌）任务上进行基准测试。
    *   **对比方法**：HisToGene、BLEEP、DeepPT 和 OmiCLIP。
    *   **评估指标**：Pearson 相关系数 (PCC)、Spearman 秩相关系数 (SRCC)、CCC 和 RMSE。

### 4. 资源与算力
*   论文中**未明确说明**具体的 GPU 型号、数量或总训练时长。但考虑到其预训练数据集包含 5400 万个图像块，且使用了 DINOv2 和 scGPT 等大型基础模型，推测其训练过程需要大规模 GPU 集群（如 A100 或 H100 级别）的支持。

### 5. 实验数量与充分性
*   **实验规模**：论文进行了多维度的验证，包括跨癌症类型的预测、跨数据集验证、消融实验（验证邻域信息和 FiLM 的作用）。
*   **充分性**：实验设计非常全面，不仅涵盖了 2D 预测，还扩展到了 **3D 组织重建**、**发育轨迹推断**以及**蛋白质组预测**。
*   **客观性**：通过在完全独立的外部数据集（如 IDCLymphNode）上进行测试，证明了模型的泛化能力，实验对比相对公平。

### 6. 论文的主要结论与发现
*   **性能领先**：H2O 在所有测试的癌症基准数据集上均显著优于现有的最先进模型（SOTA）。
*   **生物学发现**：模型能够直接从 H&E 图像中恢复 **MIF-CD74/CD44** 等关键的细胞间通讯信号轴。
*   **跨领域应用**：在人类胸腺发育研究中，H2O 准确捕捉到了 CD19 和 SPP1 等基因随年龄变化的表达趋势；在 3D 重建中，清晰地描绘了肿瘤侵袭前沿的基质重塑。
*   **多组学互补**：证明了预测的转录组和蛋白质组信息具有互补性，联合分析能更精准地识别肿瘤亚区。

### 7. 优点
*   **通用性强**：不局限于特定器官，是一个泛组织的基础模型。
*   **分辨率感知**：通过 FiLM 模块巧妙解决了空间组学技术中常见的平台差异和分辨率不一致问题。
*   **功能深度**：不仅能预测基因数值，还能支持细胞聚类、细胞通讯分析等深层生物学任务。
*   **3D 潜力**：展示了将常规切片转化为 3D 分子图谱的低成本路径。

### 8. 不足与局限
*   **稀有组织覆盖**：尽管数据集很大，但对于极罕见组织或特定病理状态的覆盖可能仍显不足。
*   **非真正单细胞分辨率**：目前的预测基于固定大小的图像块（Patch），虽然引入了邻域上下文，但可能无法完全捕捉单个细胞水平的极端异质性。
*   **蛋白质组预测限制**：相比转录组，蛋白质组预测目前依赖于较轻量级的 MLP，缺乏像 scGPT 那样大规模预训练的蛋白质组编码器支持。
*   **预测而非生成**：目前主要是一个判别/预测框架，未来若结合生成式模型（Generative AI）可能会产生更连贯的全片图谱。

（完）
