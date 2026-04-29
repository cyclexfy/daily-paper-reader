---
title: "H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling"
title_zh: H2O：连接组织病理学与空间多组学分析的基础模型
authors: "Gu, Y., Wu, Z., Yan, R., Wang, Z., Li, Y., Lin, S., Cui, Y., Lai, H., Luo, X., Zhou, S. K., Yuan, Z., Yao, J."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.717342v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 连接组织病理学与空间多组学的基座模型，利用ViT与LLM对齐
tldr: "H2O是一个连接组织病理学与空间多组学的通用AI框架。针对空间组学成本高、扩展性差的问题，该模型通过对比学习整合视觉Transformer与大语言模型，从常规H&E染色图像中直接推断空间转录组和蛋白质组分布。在130万个跨25种器官的样本上训练，H2O在预测精度和泛化性上超越现有模型，为大规模、低成本的组织表型分析和图谱构建提供了新途径。"
source: biorxiv
selection_source: fresh_fetch
motivation: "空间组学技术成本高昂且难以大规模应用，而普及的H&E染色图像缺乏分子特异性，需要一种能从形态学推断分子特征的工具。"
method: 提出H2O框架，利用对比学习将视觉Transformer与大语言模型结合，实现组织形态与语义分子知识的跨模态对齐。
result: 在包含25种器官的130万个配对样本上表现优异，能准确预测空间组学表达并成功恢复关键的细胞间通讯信号轴。
conclusion: H2O将常规病理切片转化为空间多组学分析的入口，显著提升了组织表型分析的效率和可扩展性。
---

## 摘要
空间组学技术彻底改变了组织的分子分析，但仍受限于高昂的成本和有限的可扩展性。虽然苏木精-伊红（H&E）染色应用广泛，但其缺乏分子特异性。在此，我们提出了 H2O（Histopathology to Omics），这是一个通用的人工智能框架，旨在弥合组织病理学与空间多组学之间的模态差距，从而能够从常规 H&E 图像中直接推断空间转录组学（ST）和蛋白质组学（SP）图谱。H2O 通过对比学习将视觉 Transformer（ViT）与大语言模型（LLM）相结合，使组织形态学与语义分子知识实现对齐。这种跨模态方法使模型能够将空间表达谱整合到组织学模式识别中，从而有效解码组织形态背后的分子异质性。H2O 在涵盖 25 种器官和癌症类型的 130 万个 H&E-空间配对切片的泛组织数据集上进行了训练，其从组织学预测空间组学表达的结果与测序测量值高度一致，并在三个癌症基准测试中持续优于现有最先进模型。值得注意的是，H2O 直接从 H&E 图像中恢复了 MIF-CD74/CD44 信号轴，突显了其在无需分子分析的情况下推断具有生物学意义的细胞间通讯的能力。通过在涵盖胎儿及儿科胸腺组织、人类转移性淋巴结和乳腺癌（涉及人类发育、3D 空间框架和综合多组学）的另外三个公共队列上的应用，H2O 产生了生物学一致的见解，证明了其在不同现实应用场景中卓越的准确性、鲁棒性和泛化能力。H2O 通过计算生成转录组和蛋白质组图谱，将常规组织病理学转化为空间分辨率多组学分析的入口，从而增强了组织表型分析，并实现了可扩展的综合组织图谱构建。

## Abstract
Spatial omics technologies have revolutionized the molecular profiling of tissues but remain constrained by high costs and limited scalability. While hematoxylin and eosin (H&E) staining is ubiquitous, it lacks molecular specificity. Here, we present H2O (Histopathology to Omics), a generalist AI framework that bridges the modality gap between histopathology and spatial multi-omics, enabling the direct inference of spatial transcriptomics (ST) and proteomics (SP) landscapes from routine H&E images. H2O integrates Vision Transformers (ViT) with Large Language Models (LLM) via contrastive learning to align histological morphology with semantic molecular knowledge. This cross-modal approach allows the model to incorporate spatial expression profiles into histological pattern recognition, effectively decoding the molecular heterogeneity underlying tissue morphology. Trained on a pan-tissue dataset of 1.3 million paired H&E-spatial patches across 25 organs and cancer types, H2O predicts spatial omics expression from histology with high concordance to sequenced measurements and consistently outperforms state-of-the-art models across three cancer benchmarks. Notably, H2O recovers the MIF-CD74/CD44 signaling axis directly from H&E images, highlighting its capacity to infer biologically meaningful cell-cell communication without molecular profiling. Applying on three additional public cohorts covering fetal and paediatric thymus tissues, human metastatic lymph node, and breast cancer, encompassing human development, 3D spatial frameworks, and integrative multi-omics, H2O yields biologically concordant insights, demonstrating superior accuracy, robustness, and generalizability across real-world applications in diverse scenarios. H2O converts routine histopathology into a portal for spatially resolved multi-omics profiling by computationally generating transcriptomic and proteomic landscapes, thereby enhancing tissue phenotyping and enabling scalable, integrative tissue-atlas construction.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **H2O (Histopathology to Omics)** 的基础模型，旨在通过人工智能技术将常规的组织病理学 H&E 图像转化为高维的空间多组学信息。

### 0. 论文的源代码链接
*   [https://github.com/TencentAILabHealthcare/H2O](https://github.com/TencentAILabHealthcare/H2O)

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：空间组学技术（如空间转录组 ST 和蛋白质组 SP）虽然能提供精细的分子图谱，但成本极高、技术复杂，且难以应用于临床常见的福尔马林固定石蜡包埋（FFPE）存档样本。而 H&E 染色图像虽然普及且廉价，但缺乏分子特异性。
*   **研究动机**：开发一个通用的 AI 框架，通过学习 H&E 图像形态与分子表达之间的关联，实现从常规病理切片直接推断空间分子景观，从而降低组学分析门槛，助力大规模组织图谱构建。

### 2. 论文提出的方法论
H2O 采用了一种跨模态对齐的对比学习框架，核心思想是将视觉特征锚定在分子语义空间中。
*   **核心思想**：利用视觉 Transformer (ViT) 提取图像特征，利用大语言模型 (LLM) 架构的单细胞基础模型（如 scGPT）提取分子特征，通过对比学习使两者在潜空间对齐。
*   **关键技术细节**：
    *   **图像编码器**：基于 DINOv2 预训练的 ViT，并引入了**邻域上下文聚合**（通过 1D 卷积整合周围 8 个 patch 的信息）和**直径条件 FiLM 模块**（根据不同平台的点位直径动态调整特征）。
    *   **组学编码器**：使用在 130 万个空间点位上微调过的 scGPT-FT，将基因表达转化为语义嵌入。
    *   **训练流程**：
        1.  **对比学习阶段**：最大化配对 H&E 图像嵌入与组学嵌入的相似度。
        2.  **解码预测阶段**：基于对齐后的嵌入，通过多层感知机 (MLP) 解码器预测具体的基因或蛋白质表达水平。
    *   **公式逻辑**：总损失函数 $L_{total} = \alpha \cdot L_{con} + \beta \cdot L_{rec}$，结合了对比损失（对齐模态）和重建损失（确保预测精度）。

### 3. 实验设计
*   **数据集**：
    *   **训练集**：HEST-1k（包含 25 种器官、1229 个配对样本、130 万个点位）；此外使用 TCGA 和 GTEx 的 4.5 万个样本进行图像基础模型预训练。
    *   **验证/测试集**：HEST-1k 的预留样本（ccRCC 肾癌、PRAD 前列腺癌）、IDCLymphNode（外部验证）、HTSA（人类胸腺发育图谱）、OpenST（3D 转移性淋巴结）、HTAPP（乳腺癌多组学）。
*   **Benchmark 与对比方法**：
    *   对比了 **HisToGene**、**BLEEP**、**DeepPT** 和 **OmiCLIP** 等最先进的图像转录组预测模型。
    *   评估指标包括 Pearson 相关系数 (PCC)、Spearman 相关系数 (SRCC)、一致性相关系数 (CCC) 和均方根误差 (RMSE)。

### 4. 资源与算力
*   论文中**未明确说明**具体的 GPU 型号、数量及总训练时长。但考虑到其训练数据量（5400 万个图像块、130 万个组学配对点位）以及使用了 DINOv2 和 scGPT 等大型基础模型，推测需要大规模 GPU 集群（如 A100 或 H100 级别）支持。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了从 2D 预测到 3D 重建，从转录组到蛋白质组，从肿瘤诊断到胚胎发育的多个维度。
*   **充分性与客观性**：
    *   进行了跨数据集验证（External Validation），证明了模型的泛化能力。
    *   进行了消融实验（如邻域上下文、FiLM 模块的作用验证）。
    *   实验设计较为公平，在相同的 Benchmark 下与多种 SOTA 方法进行了量化对比。

### 6. 主要结论与发现
*   **性能卓越**：H2O 在多个癌症数据集上的预测精度（PCC/SRCC）显著优于现有模型。
*   **生物学发现能力**：模型能准确恢复关键的细胞间通讯信号轴（如 MIF-CD74/CD44），这在仅靠形态学分析时是无法实现的。
*   **多维应用**：
    *   **3D 重建**：成功构建了淋巴结转移的 3D 分子浸润前沿。
    *   **发育轨迹**：在胸腺发育数据中捕捉到了符合生物学常识的基因表达随时间变化的趋势（如 CD19 的产后激活）。
    *   **多组学整合**：证明了预测的转录组和蛋白质组具有互补性，能更精细地划分肿瘤亚区。

### 7. 优点（亮点）
*   **跨模态对齐**：首次系统性地将组学基础模型（scGPT）的知识迁移到病理图像模型中。
*   **平台适应性**：通过直径条件学习（FiLM），解决了不同空间组学平台（如 Visium, Xenium, Visium HD）分辨率不一的难题。
*   **通用性强**：不局限于特定器官或癌症，展现了“泛组织”基础模型的潜力。

### 8. 不足与局限
*   **稀有组织覆盖**：尽管训练集很大，但对于极罕见组织或特定病理状态的覆盖可能仍显不足。
*   **非生成式模型**：目前主要是一个预测框架，尚未实现全切片尺度的端到端生成。
*   **分辨率限制**：目前的预测基于 Patch（224x224 像素），虽然引入了上下文，但尚未达到真正的单细胞物理分辨率。
*   **蛋白质组预测限制**：蛋白质组预测部分缺乏像转录组那样的大规模预训练编码器支持，目前依赖于较轻量级的 MLP。

（完）
