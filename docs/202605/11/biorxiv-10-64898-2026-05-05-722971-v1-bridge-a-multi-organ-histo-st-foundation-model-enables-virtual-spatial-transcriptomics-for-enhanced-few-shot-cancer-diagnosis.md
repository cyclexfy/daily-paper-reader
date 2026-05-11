---
title: "BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis"
title_zh: BRIDGE：一种多器官组织学-空间转录组学基础模型，可实现虚拟空间转录组学以增强少样本癌症诊断
authors: "Liang, Z., ZHAO, W., Wang, F., Chen, G., Huang, Y., Yu, L."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.722971v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 对齐组织学和空间转录组学的多器官基础模型
tldr: BRIDGE是一个多器官组织学-空间转录组学（ST）基础模型，通过在13个器官的60万个配对数据上预训练，实现了跨器官的生物学知识共享。它在极少样本（少于10张切片）甚至零样本情况下，能从病理图像准确生成虚拟ST谱，显著提升了癌症生存预测和生物标志物识别的精度，为临床诊断提供了高效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的虚拟空间转录组模型多依赖单器官数据且需大量样本，难以应对临床中样本稀缺的少样本或零样本诊断场景。
method: 提出BRIDGE模型，利用13个器官和3种测序技术的配对数据进行预训练，在共享潜空间中对齐形态特征与基因组信息。
result: "在少样本场景下基因预测相关性提升30%，生存预测C-index达0.724，且在未见过的癌症类型上表现出极强的零样本泛化能力。"
conclusion: BRIDGE证明了多器官预训练能有效提升虚拟ST的准确性与泛化性，是辅助临床少样本癌症诊断和生物医学发现的强有力工具。
---

## 摘要
最近的研究探索了从组织学图像生成虚拟空间转录组（ST）图谱，为实验室测量的分子分析提供了一种有前景的替代方案。然而，现有方法主要依赖于单器官模型，并需要大量的器官特异性训练数据，这限制了它们在临床实践中具有挑战性的少样本情况下的准确性，即针对特定器官或技术仅有不到10张切片可用。在这里，我们提出了 BRIDGE，这是一个在跨越13个人类器官和三种测序技术的超过60万对组织学-ST图谱上进行预训练的多器官基础模型。通过在共享的多器官潜空间内稳健地对齐形态特征和基因组信息，BRIDGE 可以利用不同组织间的共同生物学知识，实现准确且可泛化的泛癌分子分析。在没有额外器官特异性微调的情况下，BRIDGE 准确预测了80个生物标志物基因的空间表达，平均皮尔逊相关系数（PCC）达到0.474，在三种临床挑战性的少样本场景下，比现有的最先进模型提高了30%。利用生成的虚拟 ST，BRIDGE 在预测癌症生存率方面优于当前最先进的病理学基础模型，在六个 TCGA 队列中实现了0.724的平均一致性指数（C-index）。值得注意的是，BRIDGE 即使在涉及其训练期间未见过的三种癌症类型的零样本场景下，仍保持了卓越的性能，平均 C-index 达到0.717，从而证明了其超越器官和亚型特定边界的强大泛化能力。此外，BRIDGE 生成的虚拟空间转录组与 bulk RNA-seq 的预后准确性相匹配，突显了其作为实验室测序的空间信息替代方案的潜力。总之，BRIDGE 代表了虚拟 ST 领域的一种高效数据工具，可促进临床少样本背景下的生物医学发现，并推进缺乏充足样本的未充分研究癌症的诊断。

## Abstract
Recent studies have explored generating virtual spatial transcriptomics (ST) profiles from histological images, offering a promising alternative to laboratory-measured molecular profiling. However, existing approaches predominantly rely on single-organ models and require substantial organ-specific training data, restricting their accuracy under challenging few-shot conditions in clincical practice, where less than 10 slides are available for specific organs or techniques. Here, we present BRIDGE, a multi-organ foundation model pre-trained on over 600,000 paired histology-ST profiles across 13 human organs and three sequencing techniques. By robustly aligning morphological features and genomic information within a shared multi-organ latent space, BRIDGE can leverage common biological knowledge across distinct tissues to enable accurate and generalizable pan-cancer molecular profiling. Without additional organ-specific fine-tuning, BRIDGE accurately predicts the spatial expression of 80 biomarker genes, achieving an average Pearson correlation coefficient (PCC) of 0.474-a 30% improvement over existing state-of-the-art models under three clinically challenging few-shot scenarios. With generated virtual ST, BRIDGE outperforms current state-of-the-art pathology foundation models in predicting cancer survival, achieving an average concordance index (C-index) of 0.724 across six TCGA cohorts. Notably, BRIDGE maintains exceptional performance even in zero-shot scenarios involving three cancer types not seen during its training, achieving an average C-index of 0.717, thereby demonstrating its strong generalization capability that transcends organ- and subtype-specific boundaries. Moreover, BRIDGE-generated virtual spatial transcriptomes match the prognostic accuracy of bulk RNA-seq, highlighting their potential as a spatially informative alternative to laboratory sequencing. In general, BRIDGE represents a data-efficient tool in virtual ST that facilitates biomedical discoveries in clinical few-shot contexts and advances diagnosis of understudied cancers without sufficient samples.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **BRIDGE** 的多器官组织学-空间转录组学（Histo-ST）基础模型，旨在通过常规病理切片生成“虚拟”空间转录组谱，从而辅助癌症诊断和预后分析。

### 0. 源代码链接
*   **GitHub:** [https://github.com/tracy666/BRIDGE](https://github.com/tracy666/BRIDGE)

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题：** 空间转录组学（ST）虽然能提供分子层面的高分辨率信息，但成本高昂、技术复杂且难以大规模获取。现有的“图像转基因表达”模型大多针对单一器官，且需要大量器官特异性数据进行训练，导致其在临床常见的**少样本（Few-shot）**场景（如罕见病、样本稀缺器官）中泛化能力差、准确度低。
*   **研究动机：** 开发一个能够跨器官学习生物学共性的基础模型，利用大规模多器官数据预训练，实现在极少样本甚至**零样本（Zero-shot）**情况下的高精度虚拟 ST 生成。

### 2. 论文提出的方法论
*   **核心思想：** 构建一个双模态（Bi-modal）架构，通过对比学习、生成学习和重建学习三种目标的联合优化，在共享的潜空间中对齐组织形态特征与基因组信息。
*   **关键技术细节：**
    *   **视觉编码器（Visual Encoder）：** 采用 DenseNet-121（ImageNet 预训练），将 224x224 的病理图像块编码为视觉嵌入。
    *   **基因组编码器（Genome Encoder）：** 采用 TabNet，专门处理表格形式的基因表达数据，并引入掩码机制（Masked Modeling）增强鲁棒性。
    *   **联合损失函数：**
        1.  **对比损失（Contrastive Loss）：** 使用 InfoNCE 损失对齐图像和基因的嵌入向量。
        2.  **生成损失（Generative Loss）：** 使用 MSE 损失，强制视觉特征直接预测基因表达。
        3.  **重建损失（Reconstruction Loss）：** 类似于掩码语言模型（MLM），重建被遮盖的基因表达值。
        4.  **模态特定监督：** 引入图像增强对比学习（SimCLR 思路）和基因自监督学习。
*   **推理模式：** 支持“直接预测”和“基于检索的推理”（从参考库中检索最相似的分子谱）。

### 3. 实验设计
*   **数据集：** 自建 **BIG-600K** 数据集，包含来自 13 个器官、3 种测序技术的超过 60 万个配对的组织学-ST 点位。
*   **测试场景：**
    *   **少样本场景：** 低数据量（如鼻咽、卵巢）、技术差异（10X vs 老技术）、多实验室来源（批次效应）。
    *   **零样本场景：** 在完全未见过的癌症类型（膀胱癌、食管癌、胃癌）上进行生存预测。
*   **Benchmark 与对比方法：**
    *   **基因预测：** ST-Net, DeepSpaCE, Hist2ST, THItoGene 等。
    *   **检索任务：** BLEEP。
    *   **生存预测：** 顶级病理基础模型（UNI, CONCH, CTransPath, HIPT 等）以及实验测量的 Bulk RNA-seq。

### 4. 资源与算力
*   **算力设备：** 使用了 **8 块 NVIDIA GeForce RTX 3090 GPU**。
*   **训练细节：** 总 Batch size 为 384，采用梯度累积（step=2）。单器官模型训练 20 epochs，多器官基础模型训练 **50 epochs**。

### 5. 实验数量与充分性
*   **实验规模：** 论文在 7 个器官的少样本场景、16 张切片的多器官评估集、以及 6 个大型 TCGA 癌症队列上进行了广泛测试。
*   **充分性：** 实验设计非常全面，不仅对比了传统的 ST 预测模型，还挑战了参数量远大于自身的病理视觉基础模型（如 UNI）。通过消融实验和多种检索配置（单细胞、多器官等）验证了模型的稳健性。实验涵盖了从分子表达预测到下游临床生存分析的全流程，客观性较强。

### 6. 主要结论与发现
*   **性能飞跃：** 在少样本场景下，BRIDGE 的基因预测准确率（PCC）比现有 SOTA 提升了 **30%**。
*   **零样本泛化：** 即使在训练中未见过的癌症类型上，BRIDGE 的生存预测 C-index 仍达到 0.717，证明其学习到了跨器官的通用生物学规律。
*   **超越视觉模型：** 尽管参数量仅为 19.6M（远小于 UNI 的 303M），但由于引入了基因组知识，其生存预测表现优于纯视觉基础模型。
*   **替代潜力：** BRIDGE 生成的虚拟 ST 在预后分析上的表现与昂贵的 Bulk RNA-seq 相当，甚至在某些亚型（如 TNBC）上更优。

### 7. 优点
*   **数据效率：** 解决了 ST 数据获取难的问题，通过多器官联合训练实现了极强的少样本学习能力。
*   **多模态融合：** 不同于纯视觉模型，BRIDGE 显式地将基因表达作为监督信号，使其特征更具生物学解释性。
*   **跨模态检索：** 成功实现了从组织图像到单细胞 RNA-seq 数据的跨模态检索，开启了高分辨率虚拟 ST 的新路径。

### 8. 不足与局限
*   **空间分辨率限制：** 受限于训练数据（主要是 10X Visium），其生成的虚拟 ST 分辨率仍停留在 55μm 级别，尚未达到真正的单细胞空间分辨率。
*   **数据偏差：** 虽然涵盖了 13 个器官，但对于某些极罕见组织或特定病理状态的覆盖可能仍有不足。
*   **临床落地：** 目前主要在 TCGA 等回顾性数据集上验证，在真实临床前瞻性诊断中的表现仍需进一步观察。

（完）
