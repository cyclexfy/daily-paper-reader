---
title: "BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis"
authors: "Liang, Z., ZHAO, W., Wang, F., Chen, G., Huang, Y., Yu, L."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.722971v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 对齐组织学和基因组数据用于癌症诊断的基础模型
tldr: 针对现有虚拟空间转录组（ST）模型依赖单器官数据且在少样本临床场景下表现不佳的问题，本文提出了BRIDGE。这是一个在13个器官、60万对组织-ST数据上预训练的多器官基础模型。通过在共享潜空间对齐形态与基因信息，BRIDGE在少样本和零样本癌症诊断及生存预测中表现卓越，为研究样本稀缺的癌症提供了高效的分子分析工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的虚拟空间转录组模型通常局限于单器官且需要大量训练数据，难以应对临床中样本稀缺的少样本挑战。
method: 提出BRIDGE多器官基础模型，通过在13个器官的60万对组织-ST数据上进行预训练，实现了形态特征与基因信息的跨器官对齐。
result: "BRIDGE在少样本场景下将基因表达预测准确率提升了30%，并在零样本癌症生存预测中达到了0.717的平均一致性指数。"
conclusion: BRIDGE证明了多器官预训练能显著提升虚拟空间转录组的泛化能力，为临床少样本癌症诊断和生物医学发现提供了强有力的支持。
---

## Abstract
Recent studies have explored generating virtual spatial transcriptomics (ST) profiles from histological images, offering a promising alternative to laboratory-measured molecular profiling. However, existing approaches predominantly rely on single-organ models and require sub-stantial organ-specific training data, restricting their accuracy under challenging few-shot conditions in clincical practice, where less than 10 slides are available for specific organs or techniques. Here, we present BRIDGE, a multi-organ foundation model pre-trained on over 600,000 paired histology-ST profiles across 13 human organs and three sequencing techniques. By robustly aligning morphological features and genomic information within a shared multi-organ latent space, BRIDGE can leverage common biological knowledge across distinct tissues to enable accurate and generalizable pan-cancer molecular profiling. Without additional organ-specific fine-tuning, BRIDGE accurately predicts the spatial expression of 80 biomarker genes, achieving an average Pearson correlation coefficient (PCC) of 0.474--a 30% improvement over existing state-of-the-art models under three clinically challenging few-shot scenarios. With generated virtual ST, BRIDGE outperforms current state-of-the-art pathology foundation models in predicting cancer survival, achieving an average concordance index (C-index) of 0.724 across six TCGA cohorts. Notably, BRIDGE maintains exceptional performance even in zero-shot scenarios involving three cancer types not seen during its training, achieving an average C-index of 0.717, thereby demonstrating its strong generalization capability that transcends organ- and subtype-specific boundaries. Moreover, BRIDGE-generated virtual spatial transcriptomes match the prognostic accuracy of bulk RNA-seq, highlighting their potential as a spatially informative alternative to laboratory sequencing. In general, BRIDGE represents a data-efficient tool in virtual ST that facilitates biomedical discoveries in clinical few-shot contexts and advances diagnosis of understudied cancers without sufficient samples.

---

## 论文详细总结（自动生成）

这是一份关于论文 **《BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis》** 的结构化深入总结：

### 0. 论文的源代码链接
*   **GitHub 链接：** [https://github.com/tracy666/BRIDGE](https://github.com/tracy666/BRIDGE)

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题：** 现有的“虚拟空间转录组（Virtual ST）”技术（即从组织学图像预测基因表达）大多依赖于**单器官模型**，且需要大量的器官特异性训练数据。在临床实践中，针对特定器官或新技术的样本往往非常稀缺（少样本场景，少于10张切片），导致现有模型泛化能力差、预测准确度低。
*   **研究背景：** 空间转录组（ST）虽能提供分子层面的高分辨率信息，但成本高昂且操作复杂。通过深度学习从常规 H&E 染色切片中推断基因表达具有巨大的临床价值，但如何克服数据稀缺性和跨器官的生物学差异是当前的主要瓶颈。

### 2. 论文提出的方法论
BRIDGE 提出了一个**双模态多器官基础模型**框架，核心思想是通过大规模异质数据预训练，在共享潜空间内对齐形态学特征与基因组信息。
*   **核心架构：**
    *   **图像编码器（Visual Encoder）：** 采用 DenseNet-121（ImageNet 预训练），将组织图像块编码为视觉嵌入。
    *   **基因组编码器（Genome Encoder）：** 采用 TabNet，专门处理表格形式的基因表达数据。
    *   **解码器：** 包含基因预测头（从视觉特征预测表达）和重建头（增强特征鲁棒性）。
*   **关键技术细节（三位一体损失函数）：**
    1.  **对比损失（Contrastive Loss）：** 使用 InfoNCE 损失，将视觉和基因模态对齐到统一的潜空间。
    2.  **生成损失（Generative Loss）：** 通过 MSE 损失直接优化从图像到基因表达的预测精度。
    3.  **重建损失（Reconstruction Loss）：** 借鉴掩码语言模型（MLM）思路，随机掩码 25% 的基因数据并尝试重建，以保持基因组信息的保真度。
*   **推理模式：** 支持**直接预测**（从图像推断表达）和**基于检索的推理**（在参考库中匹配最相似的基因谱）。

### 3. 实验设计
*   **数据集：**
    *   **BIG-600K：** 作者构建的大规模数据集，包含来自 13 个器官、超过 60 万个配对的组织-ST 斑点（Spots）。
    *   **TCGA 队列：** 涵盖 6 种癌症类型（BLCA, ESCA, STAD, BRCA-TNBC, BRCA-HER2+, LUAD），用于下游生存分析验证。
*   **实验场景：**
    1.  **少样本场景：** 低数据量（如鼻咽癌、卵巢癌仅 2 张切片）、技术变异（10X Visium 与旧 ST 技术混杂）、多实验室来源。
    2.  **零样本场景：** 在训练中完全未见过的癌症类型（如膀胱癌、食管癌、胃癌）。
*   **Benchmark 与对比方法：**
    *   **ST 预测模型：** ST-Net, DeepSpaCE, Hist2ST, THItoGene 等。
    *   **检索模型：** BLEEP。
    *   **病理基础模型：** UNI, CONCH, CTransPath, PLIP, HIPT 等。

### 4. 资源与算力
*   **硬件：** 使用了 **8 块 NVIDIA GeForce RTX 3090 GPU**。
*   **训练时长：** 
    *   单器官模型训练约 20 个 Epoch。
    *   多器官基础模型（BRIDGE）在 50 万对数据上训练，共运行 50 个 Epoch。
*   **超参数：** Batch Size 为 384，采用梯度累积（Step=2）和余弦退火学习率调度。

### 5. 实验数量与充分性
*   **实验规模：** 论文进行了多维度的广泛实验，包括：
    *   7 个器官的少样本预测对比。
    *   10 个器官的大规模多器官评估（16 张测试切片，约 10 万个斑点）。
    *   4 种不同配置的检索池实验（跨器官、跨模态 scRNA-seq 等）。
    *   6 个 TCGA 队列的生存分析（包含零样本和少样本评估）。
    *   消融实验及细胞聚类分析（ARI/FMI 指标）。
*   **评价：** 实验设计非常充分且严谨。通过引入“零样本”癌症类型测试，客观地证明了模型的泛化边界，对比基准涵盖了目前最先进的病理大模型，具有很高的说服力。

### 6. 论文的主要结论与发现
*   **性能飞跃：** 在少样本场景下，BRIDGE 的平均皮尔逊相关系数（PCC）达到 0.474，比现有最强模型提升了 **30%**。
*   **零样本泛化：** 在未见过的癌症类型中，BRIDGE 的生存预测平均 C-index 达到 **0.717**，显示出强大的跨器官知识迁移能力。
*   **超越视觉大模型：** 尽管参数量（19.6M）远小于 UNI（303M），但 BRIDGE 在生存预测任务上表现更优，证明了**显式引入基因组知识**比单纯增加图像预训练量更有效。
*   **媲美金标准：** BRIDGE 生成的虚拟 ST 在预后准确性上匹配甚至超过了实验室测量的 **Bulk RNA-seq**。

### 7. 优点
*   **数据效率极高：** 通过多器官联合学习，解决了单器官数据不足的痛点。
*   **双模态深度融合：** 不仅是简单的特征拼接，而是通过对比和生成任务实现了模态间的语义对齐。
*   **临床实用性强：** 支持从 scRNA-seq 参考库检索，能够生成比原始 ST 成本更低、分辨率更高的虚拟谱图。
*   **泛化性强：** 能够处理不同测序技术（10X vs ST）带来的批次效应。

### 8. 不足与局限
*   **数据依赖性：** 虽然缓解了少样本问题，但对于完全差异化的非人类样本或极特殊的染色工艺，其表现尚未验证。
*   **检索限制：** 目前受限于配对数据的缺失，尚未能充分验证“供体匹配”的 ST-scRNA-seq 检索效果。
*   **解释性挑战：** 尽管模型能准确预测基因空间分布，但视觉特征与特定基因表达之间的生物学因果联系仍需进一步的湿实验验证。

（完）
