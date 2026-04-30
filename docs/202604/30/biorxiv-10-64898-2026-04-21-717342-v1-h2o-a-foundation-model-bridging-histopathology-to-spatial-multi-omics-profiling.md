---
title: "H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling"
title_zh: H2O：连接组织病理学与空间多组学分析的基础模型
authors: "Gu, Y., Wu, Z., Yan, R., Wang, Z., Li, Y., Lin, S., Cui, Y., Lai, H., Luo, X., Zhou, S. K., Yuan, Z., Yao, J."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.717342v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 利用ViT和LLM连接组织病理学与空间多组学的基础模型
tldr: "空间组学技术成本高且难以大规模应用，而常规H&E染色缺乏分子特异性。本研究提出H2O基础模型，通过对比学习将视觉Transformer与大语言模型结合，实现了从H&E图像直接推断空间转录组和蛋白质组。该模型在25种器官的130万个配对样本上训练，不仅在预测精度上超越现有模型，还能恢复生物信号轴，为低成本、大规模的空间多组学分析提供了新途径。"
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决空间组学技术成本高昂、扩展性受限，以及常规病理切片缺乏分子深度信息的问题。
method: 开发了H2O框架，利用对比学习将视觉Transformer与大语言模型结合，以对齐组织形态学与语义分子知识。
result: 在25种器官的大规模数据集上，H2O的预测结果与实测高度一致，且在多个癌症基准测试中优于现有最先进模型。
conclusion: H2O成功将常规病理图像转化为空间多组学分析的入口，显著提升了组织表型分析的能力和可扩展性。
---

## 摘要
空间组学技术彻底改变了组织的分子分析，但仍受限于高昂的成本和有限的可扩展性。虽然苏木精-伊红（H&E）染色无处不在，但它缺乏分子特异性。在此，我们提出了 H2O（Histopathology to Omics），这是一个通用的 AI 框架，旨在弥合组织病理学与空间多组学之间的模态鸿沟，从而能够从常规 H&E 图像中直接推断空间转录组学（ST）和蛋白质组学（SP）图谱。H2O 通过对比学习将视觉 Transformer（ViT）与大语言模型（LLM）相结合，使组织形态学与语义分子知识对齐。这种跨模态方法允许模型将空间表达谱纳入组织学模式识别中，从而有效地解码组织形态背后的分子异质性。H2O 在涵盖 25 种器官和癌症类型的 130 万个 H&E-空间配对切片的泛组织数据集上进行了训练，其从组织学预测的空间组学表达与测序测量结果高度一致，并在三个癌症基准测试中持续优于现有最先进模型。值得注意的是，H2O 直接从 H&E 图像中恢复了 MIF-CD74/CD44 信号轴，突显了其在无需分子分析的情况下推断具有生物学意义的细胞间通讯的能力。通过在涵盖胎儿和儿科胸腺组织、人类转移性淋巴结和乳腺癌的另外三个公共队列（涉及人类发育、3D 空间框架和综合多组学）上的应用，H2O 产生了生物学上一致的见解，证明了其在不同场景的实际应用中具有卓越的准确性、鲁棒性和泛化能力。H2O 通过计算生成转录组和蛋白质组图谱，将常规组织病理学转化为空间分辨率多组学分析的入口，从而增强了组织表型分析，并实现了可扩展的综合组织图谱构建。

## Abstract
Spatial omics technologies have revolutionized the molecular profiling of tissues but remain constrained by high costs and limited scalability. While hematoxylin and eosin (H&E) staining is ubiquitous, it lacks molecular specificity. Here, we present H2O (Histopathology to Omics), a generalist AI framework that bridges the modality gap between histopathology and spatial multi-omics, enabling the direct inference of spatial transcriptomics (ST) and proteomics (SP) landscapes from routine H&E images. H2O integrates Vision Transformers (ViT) with Large Language Models (LLM) via contrastive learning to align histological morphology with semantic molecular knowledge. This cross-modal approach allows the model to incorporate spatial expression profiles into histological pattern recognition, effectively decoding the molecular heterogeneity underlying tissue morphology. Trained on a pan-tissue dataset of 1.3 million paired H&E-spatial patches across 25 organs and cancer types, H2O predicts spatial omics expression from histology with high concordance to sequenced measurements and consistently outperforms state-of-the-art models across three cancer benchmarks. Notably, H2O recovers the MIF-CD74/CD44 signaling axis directly from H&E images, highlighting its capacity to infer biologically meaningful cell-cell communication without molecular profiling. Applying on three additional public cohorts covering fetal and paediatric thymus tissues, human metastatic lymph node, and breast cancer, encompassing human development, 3D spatial frameworks, and integrative multi-omics, H2O yields biologically concordant insights, demonstrating superior accuracy, robustness, and generalizability across real-world applications in diverse scenarios. H2O converts routine histopathology into a portal for spatially resolved multi-omics profiling by computationally generating transcriptomic and proteomic landscapes, thereby enhancing tissue phenotyping and enabling scalable, integrative tissue-atlas construction.

---

## 论文详细总结（自动生成）

这是一份关于论文《H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling》的结构化深入分析总结：

### 0. 论文的源代码链接
*   **GitHub 链接**：[https://github.com/TencentAILabHealthcare/H2O](https://github.com/TencentAILabHealthcare/H2O)

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何弥合常规组织病理学（H&E 染色）与高维空间多组学（转录组 ST 和蛋白质组 SP）之间的模态鸿沟。
*   **研究动机**：
    *   **技术局限**：空间组学技术虽然能提供分子层面的深度见解，但成本高昂、技术复杂，且难以应用于临床常见的福尔马林固定石蜡包埋（FFPE）存档样本。
    *   **信息缺失**：常规 H&E 图像虽然易于获取，但缺乏分子特异性，无法直接反映驱动疾病进展的分子异质性。
    *   **模型孤立**：现有的视觉基础模型缺乏生化背景，而组学基础模型缺乏空间形态学支撑。

### 2. 论文提出的方法论
H2O 是一个通用的 AI 框架，通过对比学习将组织形态学特征锚定到高维分子空间。
*   **核心思想**：利用预训练的单细胞基础模型（scGPT）作为“教师”，引导图像基础模型学习分子相关的形态特征。
*   **关键技术细节**：
    1.  **两阶段训练**：
        *   **第一阶段**：在 5400 万个 H&E 图像块（来自 TCGA 和 GTEx）上训练基于 DINOv2 的图像基础模型。
        *   **第二阶段**：使用 HEST-1k 数据集，通过对比学习（Contrastive Learning）将图像编码器与微调后的 scGPT（空间转录组基础模型）对齐。
    2.  **邻域上下文聚合**：通过 1D 卷积聚合中心切片周围的 8 个邻域切片特征，捕捉血管生态位或免疫梯度等宏观组织架构。
    3.  **直径条件学习（FiLM）**：引入特征线性调制（FiLM）层，根据不同平台的点位直径（如 2μm 到 150μm）动态调整特征，增强跨平台泛化能力。
    4.  **损失函数**：结合了对比损失（$L_{con}$，对齐模态）和重建损失（$L_{rec}$，预测表达量）。

### 3. 实验设计
*   **数据集**：
    *   **预训练**：TCGA（32 种癌症）、GTEx（40 种组织）及内部乳腺癌数据。
    *   **对齐与测试**：HEST-1k（包含 25 种器官、130 万个配对点位）。
    *   **独立验证集**：HTSA（人类胸腺发育）、OpenST（3D 转移性淋巴结）、HTAPP（乳腺癌多组学）。
*   **Benchmark 任务**：在 ccRCC（肾癌）和 PRAD（前列腺癌）数据集上预测 5033 个高变基因。
*   **对比方法**：HisToGene、BLEEP、DeepPT、OmiCLIP。

### 4. 资源与算力
*   **数据规模**：使用了 44,992 个样本的 54,435,706 个图像块进行图像 FM 训练。
*   **算力说明**：文中**未明确说明**具体的 GPU 型号、数量及训练总时长。但考虑到 54M 图像块的 DINOv2 训练规模，通常需要大规模 GPU 集群（如 A100/H100 阵列）支持。

### 5. 实验数量与充分性
*   **实验规模**：非常充分。
    *   **广度**：覆盖了 25 种器官和多种癌症类型。
    *   **深度**：不仅做了基因表达预测，还深入到了细胞间通讯（MIF 信号轴）、发育轨迹（胎儿到儿科胸腺）、3D 组织重建以及转录组-蛋白质组的联合分析。
    *   **消融实验**：对邻域上下文、FiLM 模块等关键组件进行了消融验证。
*   **客观性**：使用了严格扣除的测试集和完全独立的外部验证集，对比了多种 SOTA 模型，评价指标包括 PCC、SRCC、CCC 和 RMSE，较为全面客观。

### 6. 论文的主要结论与发现
*   **预测精度**：H2O 在所有基准测试中均显著优于现有模型，能够高保真地恢复空间表达模式。
*   **生物学发现**：
    *   **信号轴恢复**：仅凭 H&E 图像即可恢复 MIF-CD74/CD44 信号轴，证明模型捕捉到了功能性信号网络。
    *   **发育轨迹**：准确捕捉了胸腺发育中 CD19 的产后激活和 SPP1 的胎儿-病理转变。
    *   **3D 建模**：成功构建了淋巴结转移的 3D 分子图谱，揭示了 CAFs 和巨噬细胞在侵袭前沿的动态。
    *   **多组学整合**：通过联合预测 ST 和 SP，识别出了单模态分析中被掩盖的肿瘤亚区。

### 7. 优点（亮点）
*   **引入组学先验**：不同于以往简单的回归模型，H2O 利用了 LLM（scGPT）中蕴含的生物学知识。
*   **跨尺度感知**：通过 FiLM 解决了不同空间组学平台分辨率不一的难题。
*   **多维度应用**：证明了模型在 3D 重建和时间序列（发育）分析中的强大泛化能力。
*   **临床潜力**：为低成本、大规模地从存档 H&E 切片中挖掘分子信息提供了可行路径。

### 8. 不足与局限
*   **稀有组织覆盖**：尽管数据集很大，但对于极罕见组织或特定病理状态的覆盖可能仍有不足。
*   **非生成式模型**：目前主要是一个预测框架，未来若能结合生成模型（Generative AI）可能生成更完整的全片分子图谱。
*   **分辨率限制**：预测基于 224x224 的图像块，虽然引入了邻域信息，但尚未达到真正的单细胞物理分辨率。
*   **蛋白质组预测限制**：相比转录组，蛋白质组预测缺乏大规模预训练编码器的支持，目前依赖于较轻量级的 MLP，精度提升空间仍存。

（完）
