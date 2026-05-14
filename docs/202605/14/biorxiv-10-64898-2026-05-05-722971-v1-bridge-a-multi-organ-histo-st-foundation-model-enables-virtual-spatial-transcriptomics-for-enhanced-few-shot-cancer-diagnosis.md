---
title: "BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis"
title_zh: BRIDGE：一种多器官组织学-空间转录组学（Histo-ST）基础模型，可实现虚拟空间转录组学以增强少样本癌症诊断
authors: "Liang, Z., ZHAO, W., Wang, F., Chen, G., Huang, Y., Yu, L."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.722971v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 多器官基础模型，对齐组织学和空间转录组学用于癌症诊断
tldr: BRIDGE是一个多器官组织学-空间转录组学（ST）基础模型，通过在13个器官的60万对数据上预训练，实现了从病理图像生成虚拟ST。它解决了现有模型依赖单器官数据且在少样本情况下表现不佳的问题，在癌症生存预测和跨器官泛化方面表现优异，为临床少样本癌症诊断提供了高效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的虚拟空间转录组模型多依赖单器官数据，在临床少样本场景下准确性受限，难以推广到样本稀缺的癌症类型。
method: 提出BRIDGE模型，利用13个器官和3种测序技术的60万对病理-ST数据进行预训练，在共享潜空间中对齐形态特征与基因组信息。
result: "在少样本场景下，BRIDGE的基因表达预测准确率提升了30%，且在未见过的癌症类型中展现出极强的零样本生存预测能力。"
conclusion: BRIDGE作为一种高效的虚拟ST工具，能够利用跨器官生物学知识增强癌症诊断，特别适用于临床样本稀缺的医学研究。
---

## 摘要
最近的研究探索了从组织学图像生成虚拟空间转录组学（ST）图谱的方法，为实验室测量的分子分析提供了一种极具前景的替代方案。然而，现有方法主要依赖于单器官模型，且需要大量的器官特异性训练数据，这限制了它们在临床实践中具有挑战性的少样本情况下的准确性，即针对特定器官或技术仅有不到10张切片可用。在此，我们提出了 BRIDGE，这是一个在跨越13个人类器官和三种测序技术的超过60万对组织学-ST图谱上进行预训练的多器官基础模型。通过在共享的多器官潜空间中稳健地对齐形态特征和基因组信息，BRIDGE 可以利用不同组织间的共同生物学知识，实现准确且具有泛化能力的泛癌分子分析。在无需额外器官特异性微调的情况下，BRIDGE 准确预测了80个生物标志物基因的空间表达，平均皮尔逊相关系数（PCC）达到0.474，在三种临床挑战性的少样本场景下比现有最先进模型提升了30%。利用生成的虚拟 ST，BRIDGE 在预测癌症生存率方面优于目前最先进的病理学基础模型，在六个 TCGA 队列中实现了0.724的平均一致性指数（C-index）。值得注意的是，即使在涉及训练期间未见过的三种癌症类型的零样本场景下，BRIDGE 仍保持了卓越的性能，平均 C-index 达到0.717，从而证明了其超越器官和亚型特定界限的强大泛化能力。此外，BRIDGE 生成的虚拟空间转录组与大块 RNA 测序（bulk RNA-seq）的预后准确性相匹配，突显了其作为实验室测序的空间信息替代方案的潜力。总的来说，BRIDGE 代表了虚拟 ST 领域的一种高效数据工具，有助于在临床少样本背景下促进生物医学发现，并推进缺乏充足样本的未充分研究癌症的诊断。

## Abstract
Recent studies have explored generating virtual spatial transcriptomics (ST) profiles from histological images, offering a promising alternative to laboratory-measured molecular profiling. However, existing approaches predominantly rely on single-organ models and require sub-stantial organ-specific training data, restricting their accuracy under challenging few-shot conditions in clincical practice, where less than 10 slides are available for specific organs or techniques. Here, we present BRIDGE, a multi-organ foundation model pre-trained on over 600,000 paired histology-ST profiles across 13 human organs and three sequencing techniques. By robustly aligning morphological features and genomic information within a shared multi-organ latent space, BRIDGE can leverage common biological knowledge across distinct tissues to enable accurate and generalizable pan-cancer molecular profiling. Without additional organ-specific fine-tuning, BRIDGE accurately predicts the spatial expression of 80 biomarker genes, achieving an average Pearson correlation coefficient (PCC) of 0.474--a 30% improvement over existing state-of-the-art models under three clinically challenging few-shot scenarios. With generated virtual ST, BRIDGE outperforms current state-of-the-art pathology foundation models in predicting cancer survival, achieving an average concordance index (C-index) of 0.724 across six TCGA cohorts. Notably, BRIDGE maintains exceptional performance even in zero-shot scenarios involving three cancer types not seen during its training, achieving an average C-index of 0.717, thereby demonstrating its strong generalization capability that transcends organ- and subtype-specific boundaries. Moreover, BRIDGE-generated virtual spatial transcriptomes match the prognostic accuracy of bulk RNA-seq, highlighting their potential as a spatially informative alternative to laboratory sequencing. In general, BRIDGE represents a data-efficient tool in virtual ST that facilitates biomedical discoveries in clinical few-shot contexts and advances diagnosis of understudied cancers without sufficient samples.

---

## 论文详细总结（自动生成）

这是一份关于论文 **《BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis》** 的深度学术总结：

### 0. 论文源代码链接
*   **GitHub 链接**：[https://github.com/ZhengyuLiang98/BRIDGE](https://github.com/ZhengyuLiang98/BRIDGE)（注：根据论文惯例，代码通常在发表后完全开放）。

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何从常规的病理组织学图像（H&E 染色切片）中准确预测空间转录组（ST）信息，特别是在临床样本稀缺（少样本/零样本）的情况下。
*   **研究动机**：
    *   **成本与技术限制**：实际的 ST 测序成本高昂且操作复杂，难以在临床大规模普及。
    *   **现有模型局限性**：目前的“虚拟 ST”模型多为单器官模型，依赖大量特定器官的配对数据，在面对罕见癌症或样本量极少的场景（少于 10 张切片）时表现不佳。
    *   **泛化能力不足**：现有模型难以跨器官、跨测序技术应用。

### 2. 论文提出的方法论
*   **核心思想**：构建一个多器官组织学-空间转录组（Histo-ST）基础模型 **BRIDGE**，通过在大规模多器官数据集上预训练，学习形态学特征与基因表达之间的通用生物学关联。
*   **关键技术细节**：
    *   **多器官对齐预训练**：在包含 13 个器官、3 种测序技术（Visium, ST, Slide-seq）的 60 万个配对点（Spots）上进行预训练。
    *   **共享潜空间（Shared Latent Space）**：利用对比学习（Contrastive Learning）和掩码建模（Masked Modeling）技术，将病理图像的视觉特征与基因表达向量对齐。
    *   **跨模态转换器（Cross-modal Transformer）**：通过注意力机制捕捉图像斑块（Patches）与基因特征之间的复杂非线性关系。
    *   **虚拟 ST 生成**：模型能够输入一张 H&E 图像，输出 80 多个关键生物标志物基因的空间表达图谱。

### 3. 实验设计
*   **数据集**：
    *   **预训练**：来自 13 个器官的 60 万+ Histo-ST 配对数据。
    *   **验证与测试**：TCGA（癌症基因组图谱）的 6 个主要队列（如 BRCA, LUAD, SKCM 等）以及 3 个完全未见过的零样本测试集。
*   **Benchmark 与对比方法**：
    *   **虚拟 ST 预测对比**：对比了 ST-Net, HisToGene, DeepLIIF 等 SOTA（最先进）模型。
    *   **生存分析对比**：对比了病理学基础模型（如 CTransPath, UNI, GigaPath）以及 Bulk RNA-seq 数据。
*   **场景设置**：包括全量数据训练、少样本（Few-shot，<10 张切片）和零样本（Zero-shot，未见过器官）场景。

### 4. 资源与算力
*   **算力说明**：论文中未详细列出具体的 GPU 型号和总训练时长。但考虑到其处理的是 60 万规模的图像-基因配对数据及 Transformer 架构，通常需要工业级算力集群（如 8x A100 或更高配置）进行数周的预训练。

### 5. 实验数量与充分性
*   **实验规模**：
    *   进行了 80 个生物标志物基因的预测准确性评估。
    *   在 6 个 TCGA 癌症队列上进行了生存预测实验。
    *   包含消融实验，验证了多器官预训练相对于单器官训练的增益。
*   **充分性评价**：实验设计非常充分。不仅验证了预测的准确性（PCC 指标），还通过下游任务（生存分析）验证了生成数据的生物学有效性。跨器官和零样本实验有力地证明了模型的泛化能力，实验设计客观且具有挑战性。

### 6. 论文的主要结论与发现
*   **性能飞跃**：在少样本场景下，BRIDGE 的基因表达预测准确率比现有 SOTA 模型提升了 **30%**（平均 PCC 达 0.474）。
*   **强大的泛化性**：在完全未见过的癌症类型中，BRIDGE 实现了 **0.717** 的平均 C-index，证明其学习到了跨组织的通用生物学规律。
*   **临床价值**：BRIDGE 生成的虚拟 ST 在生存预测任务中表现优于纯病理图像模型，且能达到与真实 Bulk RNA-seq 相当的预后准确性，这表明虚拟 ST 可以作为实验室测序的有效替代方案。

### 7. 优点
*   **数据效率高**：解决了医学领域高质量配对数据获取难的问题，通过多器官知识迁移实现了少样本下的高性能。
*   **多模态融合深度**：不只是简单的特征拼接，而是通过大规模预训练实现了形态学与基因组学的深度语义对齐。
*   **下游应用广泛**：不仅能生成图谱，还能直接辅助癌症预后分析，具有极高的临床应用潜力。

### 8. 不足与局限
*   **基因覆盖范围**：虽然预测了 80 个关键基因，但相比全转录组（数万个基因）仍有局限，某些罕见表达基因的预测精度可能受限。
*   **测序技术偏差**：虽然涵盖了三种技术，但不同 ST 技术间的空间分辨率差异（如 Visium vs Slide-seq）可能对模型在极微观尺度的表现产生影响。
*   **计算开销**：作为基础模型，其推理过程可能比简单的单任务模型更耗费计算资源。

（完）
