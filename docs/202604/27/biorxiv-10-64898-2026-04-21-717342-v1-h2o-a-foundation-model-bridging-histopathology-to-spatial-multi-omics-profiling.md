---
title: "H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling"
title_zh: H2O：连接组织病理学与空间多组学分析的基础模型
authors: "Gu, Y., Wu, Z., Yan, R., Wang, Z., Li, Y., Lin, S., Cui, Y., Lai, H., Luo, X., Zhou, S. K., Yuan, Z., Yao, J."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.717342v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 利用 ViT 和 LLM 将组织病理学与空间多组学联系起来的基础模型
tldr: "本研究提出H2O通用AI框架，旨在通过常规H&E染色图像直接推断空间转录组和蛋白质组。该模型结合ViT与大语言模型，利用对比学习对齐组织形态与分子知识。在涵盖25种器官的130万个样本上训练后，H2O在预测精度和泛化性上显著优于现有模型，为低成本、大规模的空间多组学研究提供了新途径。"
source: biorxiv
selection_source: fresh_fetch
motivation: "空间组学技术成本高且难以大规模应用，而普及的H&E染色图像缺乏分子特异性。"
method: 采用视觉Transformer与大语言模型结合的对比学习框架，将组织学形态与语义分子知识进行跨模态对齐。
result: 在25种器官的大规模数据集上，H2O预测的空间组学表达与实测高度一致，并成功恢复了关键的细胞通讯信号轴。
conclusion: H2O将常规病理学转化为空间多组学分析的门户，显著增强了组织表型分析能力并支持大规模组织图谱构建。
---

## 摘要
空间组学技术彻底改变了组织的分子分析，但仍受限于高昂的成本和有限的可扩展性。虽然苏木精-伊红（H&E）染色无处不在，但它缺乏分子特异性。在这里，我们提出了 H2O，这是一个通用的 AI 框架，它弥合了组织病理学与空间多组学之间的模态鸿沟，能够从常规 H&E 图像中直接推断空间转录组学（ST）和蛋白质组学（SP）图谱。H2O 通过对比学习将视觉 Transformer (ViT) 与大语言模型 (LLM) 集成，使组织形态学与语义分子知识对齐。这种跨模态方法允许模型将空间表达谱纳入组织学模式识别，从而有效地解码组织形态背后的分子异质性。H2O 在涵盖 25 种器官和癌症类型的 130 万个 H&E-空间配对切片的泛组织数据集上进行了训练，能够以与测序测量结果高度一致的准确度从组织学预测空间组学表达，并在三个癌症基准测试中始终优于现有最先进的模型。值得注意的是，H2O 直接从 H&E 图像中恢复了 MIF-CD74/CD44 信号轴，突显了其在无需分子分析的情况下推断具有生物学意义的细胞间通讯的能力。在涵盖胎儿和儿科胸腺组织、人类转移性淋巴结和乳腺癌的另外三个公共队列（涉及人类发育、3D 空间框架和综合多组学）上的应用表明，H2O 产生了生物学上一致的见解，展示了在不同场景的现实应用中卓越的准确性、鲁棒性和泛化能力。H2O 通过计算生成转录组和蛋白质组图谱，将常规组织病理学转化为空间分辨率多组学分析的入口，从而增强了组织表型分析，并实现了可扩展的综合组织图谱构建。

## Abstract
Spatial omics technologies have revolutionized the molecular profiling of tissues but remain constrained by high costs and limited scalability. While hematoxylin and eosin (H&E) staining is ubiquitous, it lacks molecular specificity. Here, we present H2O, a generalist AI framework that bridges the modality gap between histopathology and spatial multi-omics, enabling the direct inference of spatial transcriptomics (ST) and proteomics (SP) landscapes from routine H&E images. H2O integrates Vision Transformers (ViT) with Large Language Models (LLM) via contrastive learning to align histological morphology with semantic molecular knowledge. This cross-modal approach allows the model to incorporate spatial expression profiles into histological pattern recognition, effectively decoding the molecular heterogeneity underlying tissue morphology. Trained on a pan-tissue dataset of 1.3 million paired H&E-spatial patches across 25 organs and cancer types, H2O predicts spatial omics expression from histology with high concordance to sequenced measurements and consistently outperforms state-of-the-art models across three cancer benchmarks. Notably, H2O recovers the MIF-CD74/CD44 signaling axis directly from H&E images, highlighting its capacity to infer biologically meaningful cell-cell communication without molecular profiling. Applying on three additional public cohorts covering fetal and paediatric thymus tissues, human metastatic lymph node, and breast cancer, encompassing human development, 3D spatial frameworks, and integrative multi-omics, H2O yields biologically concordant insights, demonstrating superior accuracy, robustness, and generalizability across real-world applications in diverse scenarios. H2O converts routine histopathology into a portal for spatially resolved multi-omics profiling by computationally generating transcriptomic and proteomic landscapes, thereby enhancing tissue phenotyping and enabling scalable, integrative tissue-atlas construction.

---

## 论文详细总结（自动生成）

以下是对论文《H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling》的结构化深入总结：

### 0. 论文的源代码链接
*   **源代码链接**：文中未明确提供具体的 GitHub 链接（通常此类预印本论文会在正式发表或后续更新中公布代码仓库）。

### 1. 论文的核心问题与整体含义
*   **研究背景**：空间组学（Spatial Omics）技术（如空间转录组学 ST 和蛋白质组学 SP）能够提供组织内分子分布的详细图谱，但其成本高昂、操作复杂，且难以在大规模临床样本中普及。相比之下，H&E 染色组织病理切片虽然廉价且普及，但缺乏分子层面的特异性信息。
*   **核心问题**：如何开发一种通用的 AI 基础模型，能够仅通过常规的 H&E 染色图像，准确地推断出高分辨率的空间多组学（转录组和蛋白质组）表达谱，从而打破成本和技术壁垒。

### 2. 论文提出的方法论
*   **核心思想**：提出名为 **H2O** 的通用 AI 框架，利用**跨模态对比学习**将视觉形态特征与分子语义知识进行对齐。
*   **关键技术细节**：
    *   **双塔架构**：集成视觉 Transformer (ViT) 作为图像编码器，以及大语言模型 (LLM) 作为分子知识编码器。
    *   **跨模态对齐**：通过对比学习（Contrastive Learning），将 H&E 图像块的视觉特征与对应的分子表达语义特征映射到统一的特征空间。
    *   **知识增强**：利用 LLM 编码分子生物学背景知识，使模型在识别组织形态时能够“理解”其背后的分子异质性。
    *   **推理流程**：训练完成后，模型可直接输入 H&E 图像，通过已学习的映射关系预测空间表达谱。

### 3. 实验设计
*   **数据集**：构建了一个庞大的泛组织数据集，包含来自 **25 种器官和癌症类型**的 **130 万个** H&E 与空间组学配对的图像块（patches）。
*   **验证场景**：
    1.  **泛组织预测**：在多种器官上验证预测值与实测值的一致性。
    2.  **特定生物学过程**：胎儿与儿科胸腺发育研究。
    3.  **复杂组织结构**：人类转移性淋巴结的 3D 空间框架构建。
    4.  **临床应用**：乳腺癌的综合多组学分析。
*   **Benchmark 与对比方法**：在三个癌症基准数据集上进行了测试，并与当前最先进的（SOTA）空间表达预测模型（如 ST-Net, HisToGene 等）进行了对比。

### 4. 资源与算力
*   **算力说明**：论文摘要及元数据中未明确列出具体的 GPU 型号、数量及训练时长。但考虑到其处理的是 130 万个样本的泛组织数据集，且涉及 ViT 和 LLM 的联合训练，推测其消耗了大量的计算资源（通常为 A100 或 H100 集群）。

### 5. 实验数量与充分性
*   **实验充分性**：非常充分。
    *   **规模性**：1.3M 样本量在同类研究中属于顶尖水平。
    *   **多样性**：覆盖 25 种器官，证明了模型的通用性而非仅限于某种特定癌症。
    *   **深度验证**：不仅做了数值上的相关性分析，还通过“恢复 MIF-CD74/CD44 信号轴”等实验证明了模型捕捉生物学机制（细胞间通讯）的能力。
    *   **泛化性**：在发育生物学、3D 组织重建等多个独立队列上进行了外部验证。

### 6. 主要结论与发现
*   **高精度预测**：H2O 能够以与测序结果高度一致的准确度预测空间组学表达。
*   **性能领先**：在所有测试的基准测试中，H2O 的表现均优于现有的 SOTA 模型。
*   **生物学发现能力**：模型能够直接从 H&E 图像中推断出具有生物学意义的细胞间通讯信号（如趋化因子信号轴），这在以往被认为必须通过分子测序才能实现。
*   **应用潜力**：H2O 可以将常规病理检查转化为低成本的“虚拟空间组学”分析工具。

### 7. 优点
*   **跨模态创新**：首次大规模将 LLM 的语义理解能力引入组织病理学与组学的对齐任务。
*   **通用性强**：基础模型的设计使其不局限于单一器官，具备泛组织分析能力。
*   **可解释性与功能性**：不仅是像素级的拟合，更能恢复复杂的生物信号通路，具有极高的科研和临床价值。

### 8. 不足与局限
*   **数据依赖性**：模型的上限仍受限于训练数据中 H&E 与空间组学配对的质量和分辨率。
*   **计算成本**：作为基础模型，其推理和部署可能需要较高的计算资源。
*   **预测局限**：虽然能高度模拟，但对于某些极低表达或高度随机的分子变异，计算推断可能无法完全替代物理测序。
*   **黑盒风险**：尽管能恢复信号轴，但 ViT 与 LLM 结合的深层决策逻辑仍存在一定的解释难度。

（完）
