---
title: "H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling"
title_zh: H2O：连接组织病理学与空间多组学分析的基础模型
authors: "Gu, Y., Wu, Z., Yan, R., Wang, Z., Li, Y., Lin, S., Cui, Y., Lai, H., Luo, X., Zhou, S. K., Yuan, Z., Yao, J."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.717342v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 连接组织病理学与空间多组学的基座模型
tldr: "H2O是一个利用ViT和LLM对齐从H&E图像推断空间组学的基座模型。"
source: biorxiv
selection_source: fresh_fetch
motivation: 连接组织病理学与空间多组学的基座模型。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## 摘要
空间组学技术彻底改变了组织的分子分析，但仍受限于高昂的成本和有限的可扩展性。虽然苏木精-伊红（H&E）染色无处不在，但它缺乏分子特异性。在此，我们提出了 H2O（Histopathology to Omics），这是一个通用的 AI 框架，它弥合了组织病理学与空间多组学之间的模态差距，能够从常规 H&E 图像中直接推断空间转录组学（ST）和蛋白质组学（SP）图谱。H2O 通过对比学习将视觉 Transformer（ViT）与大语言模型（LLM）集成，以使组织学形态与语义分子知识对齐。这种跨模态方法允许模型将空间表达谱纳入组织学模式识别中，从而有效地解码组织形态背后的分子异质性。H2O 在涵盖 25 个器官和癌症类型的 130 万个 H&E-空间配对切片的泛组织数据集上进行了训练，其从组织学预测的空间组学表达与测序测量结果高度一致，并在三个癌症基准测试中始终优于现有最先进的模型。值得注意的是，H2O 直接从 H&E 图像中恢复了 MIF-CD74/CD44 信号轴，突显了其在无需分子分析的情况下推断具有生物学意义的细胞间通讯的能力。在涵盖胎儿和儿科胸腺组织、人类转移性淋巴结和乳腺癌的另外三个公共队列（涉及人类发育、3D 空间框架和综合多组学）上的应用表明，H2O 产生了生物学上一致的见解，证明了其在不同场景的实际应用中具有卓越的准确性、鲁棒性和泛化性。H2O 通过计算生成转录组和蛋白质组图谱，将常规组织病理学转化为空间分辨率多组学分析的入口，从而增强了组织表型分析，并实现了可扩展的、综合性的组织图谱构建。

## Abstract
Spatial omics technologies have revolutionized the molecular profiling of tissues but remain constrained by high costs and limited scalability. While hematoxylin and eosin (H&E) staining is ubiquitous, it lacks molecular specificity. Here, we present H2O (Histopathology to Omics), a generalist AI framework that bridges the modality gap between histopathology and spatial multi-omics, enabling the direct inference of spatial transcriptomics (ST) and proteomics (SP) landscapes from routine H&E images. H2O integrates Vision Transformers (ViT) with Large Language Models (LLM) via contrastive learning to align histological morphology with semantic molecular knowledge. This cross-modal approach allows the model to incorporate spatial expression profiles into histological pattern recognition, effectively decoding the molecular heterogeneity underlying tissue morphology. Trained on a pan-tissue dataset of 1.3 million paired H&E-spatial patches across 25 organs and cancer types, H2O predicts spatial omics expression from histology with high concordance to sequenced measurements and consistently outperforms state-of-the-art models across three cancer benchmarks. Notably, H2O recovers the MIF-CD74/CD44 signaling axis directly from H&E images, highlighting its capacity to infer biologically meaningful cell-cell communication without molecular profiling. Applying on three additional public cohorts covering fetal and paediatric thymus tissues, human metastatic lymph node, and breast cancer, encompassing human development, 3D spatial frameworks, and integrative multi-omics, H2O yields biologically concordant insights, demonstrating superior accuracy, robustness, and generalizability across real-world applications in diverse scenarios. H2O converts routine histopathology into a portal for spatially resolved multi-omics profiling by computationally generating transcriptomic and proteomic landscapes, thereby enhancing tissue phenotyping and enabling scalable, integrative tissue-atlas construction.

---

## 论文详细总结（自动生成）

这是一份关于论文《H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling》的深度结构化总结：

### 0. 论文源代码链接
*   **GitHub 链接**：[https://github.com/TencentAILabHealthcare/H2O](https://github.com/TencentAILabHealthcare/H2O)

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何弥合常规组织病理学（H&E 染色）与高成本、低通量的空间多组学（转录组 ST 和蛋白质组 SP）之间的鸿沟。
*   **背景**：H&E 图像在临床中极其普遍但缺乏分子特异性；而空间组学虽能提供深度的分子异质性信息，但因成本高、技术复杂且对样本要求苛刻（如不兼容 FFPE 存档样本），难以大规模应用。
*   **目标**：开发一个通用的 AI 基础模型，能够直接从常规 H&E 图像中推断出高精度的空间转录组和蛋白质组图谱。

### 2. 方法论
H2O 采用了一种**跨模态对齐**的架构，主要包含以下关键技术：
*   **双基础模型对齐**：
    *   **图像端**：使用基于 DINOv2 预训练的 Vision Transformer (ViT) 作为组织病理学基础模型。
    *   **组学端**：使用基于 scGPT（单细胞大模型）微调后的空间转录组基础模型（scGPT-FT）。
*   **对比学习框架**：通过对比学习（Contrastive Learning）将 H&E 图像特征映射到分子潜在空间，使模型能够学习形态学特征与分子语义知识之间的关联。
*   **关键技术细节**：
    *   **邻域上下文聚合**：利用 1D 卷积整合中心切片周围的 8 个邻域切片信息，捕捉组织微环境。
    *   **直径条件学习（FiLM）**：引入 Feature-wise Linear Modulation (FiLM) 模块，根据不同平台的斑点直径（如 2μm 到 150μm）动态调整特征，解决跨平台分辨率不一致的问题。
    *   **多组学解码器**：在对齐的嵌入空间基础上，通过轻量级 MLP 解码器预测 5000 多个高变基因的表达量。

### 3. 实验设计
*   **数据集**：
    *   **训练集**：使用 TCGA、GTEx 及内部乳腺癌数据集（共 4.5 万个样本，5400 万个切片）训练图像模型；使用 HEST-1k（1229 个配对样本，130 万个数据对）进行跨模态训练。
    *   **验证集**：HEST-1k 的预留测试集（ccRCC 肾癌、PRAD 前列腺癌）、IDCLymphNode（外部验证）。
    *   **应用场景**：HTSA（人类胸腺发育）、OpenST（3D 空间构建）、HTAPP（乳腺癌多组学集成）。
*   **Benchmark 与对比方法**：
    *   对比了 **HisToGene**、**BLEEP**、**DeepPT** 和 **OmiCLIP** 等当前最先进的（SOTA）图像转录组预测模型。
    *   评价指标包括 Pearson 相关系数 (PCC)、Spearman 相关系数 (SRCC)、CCC 和 RMSE。

### 4. 资源与算力
*   **文中说明**：论文未明确列出具体的 GPU 型号、数量或总训练时长。
*   **推测**：考虑到处理了超过 5400 万个图像切片和 130 万个配对数据，且涉及 ViT 和 LLM 的微调，该研究需要大规模的 GPU 集群支持（如 A100 或 H100 级别）。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了 25 个器官和癌症类型，使用了超过 130 万个配对切片。
*   **充分性**：实验设计非常全面。除了基础的预测精度对比，还进行了：
    *   **消融实验**：验证了邻域上下文和 FiLM 模块的有效性。
    *   **生物学功能验证**：包括细胞间通讯（MIF 信号轴）、细胞类型反卷积、发育轨迹分析。
    *   **维度扩展**：从 2D 预测扩展到 3D 组织块构建。
*   **客观性**：使用了多个独立外部数据集进行验证，确保了模型的泛化能力，实验对比相对公平。

### 6. 主要结论与发现
*   **性能卓越**：H2O 在所有癌症基准测试中均显著优于现有 SOTA 模型，预测结果与真实测序高度一致。
*   **发现分子机制**：模型能直接从 H&E 图像中恢复 **MIF-CD74/CD44** 信号轴，这在以往被认为必须通过分子实验才能发现。
*   **跨领域泛化**：在人类胸腺发育研究中，H2O 准确捕捉到了 CD19（出生后激活）和 SPP1（胎儿期高表达）的动态变化。
*   **3D 与多组学集成**：成功构建了转移性淋巴结的 3D 分子图谱，并证明了集成预测的转录组和蛋白质组能比单一模态更精准地识别肿瘤亚区。

### 7. 优点
*   **通用性强**：不局限于特定器官或癌症，是一个真正的“泛组织”基础模型。
*   **知识驱动**：通过引入 scGPT 的先验知识，使图像特征具备了分子语义，而不仅仅是简单的像素回归。
*   **解决平台差异**：FiLM 模块有效解决了空间组学技术中常见的“分辨率/斑点大小”异质性问题。
*   **临床潜力**：为低成本、大规模回顾性研究存档的 FFPE 样本提供了分子分析的可能性。

### 8. 不足与局限
*   **稀有组织覆盖**：尽管数据集很大，但对于极罕见组织或特定病理状态的覆盖可能仍不足。
*   **非生成式模型**：目前 H2O 主要是预测框架，未来若能结合生成式模型（Generative AI）可能生成更完整的全片分子图谱。
*   **细胞分辨率限制**：目前的预测基于固定大小的 Patch（224x224 像素），虽然引入了上下文，但尚未达到真正的单细胞级精度。
*   **蛋白质组预测限制**：相比转录组，蛋白质组预测目前依赖于较轻量的 MLP，缺乏像 scGPT 那样大规模预训练的蛋白质编码器支持。

（完）
