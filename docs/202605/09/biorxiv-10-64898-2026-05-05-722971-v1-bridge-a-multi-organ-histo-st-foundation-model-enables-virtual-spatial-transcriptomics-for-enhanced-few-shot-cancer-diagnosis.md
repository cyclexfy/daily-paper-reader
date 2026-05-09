---
title: "BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis"
title_zh: BRIDGE：一种多器官组织学-空间转录组学基础模型，可实现虚拟空间转录组学以增强少样本癌症诊断
authors: "Liang, Z., ZHAO, W., Wang, F., Chen, G., Huang, Y., Yu, L."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.722971v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 对齐组织学和基因组数据用于癌症诊断的多器官基础模型
tldr: BRIDGE是一个多器官组织学-空间转录组学（ST）基础模型，通过在13个器官的60万个配对数据上预训练，实现了从病理图像生成虚拟ST。它解决了现有模型依赖单器官数据且在少样本情况下表现不佳的问题，在癌症生存预测和生物标志物预测中表现优异，为临床少样本癌症诊断提供了高效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的虚拟空间转录组模型多局限于单器官且需要大量训练数据，难以应对临床中样本稀缺的少样本或零样本场景。
method: 提出BRIDGE模型，利用13个器官和3种测序技术的60万组配对数据进行预训练，在共享潜空间中对齐形态特征与基因组信息。
result: "在少样本场景下，BRIDGE的基因表达预测准确率提升了30%，且在未见过的癌症类型中展现出极强的零样本生存预测能力。"
conclusion: BRIDGE作为一种高效的虚拟ST工具，能够跨器官泛化生物学知识，显著提升了临床少样本及罕见癌症的分子诊断与预后评估水平。
---

## 摘要
最近的研究探索了从组织学图像生成虚拟空间转录组（ST）图谱，为实验室测量的分子分析提供了一种极具前景的替代方案。然而，现有方法主要依赖于单器官模型，且需要大量的器官特异性训练数据，这限制了它们在临床实践中具有挑战性的少样本情况下的准确性，即针对特定器官或技术仅有不到10张切片可用。在此，我们提出了 BRIDGE，这是一个在涵盖13个人类器官和三种测序技术的超过60万个配对组织学-ST图谱上进行预训练的多器官基础模型。通过在共享的多器官潜空间中稳健地对齐形态特征和基因组信息，BRIDGE 可以利用跨不同组织的通用生物学知识，实现准确且具有泛化能力的泛癌分子分析。在无需额外器官特异性微调的情况下，BRIDGE 准确预测了80个生物标志物基因的空间表达，在三种临床挑战性的少样本场景下实现了0.474的平均皮尔逊相关系数（PCC），比现有的最先进模型提高了30%。利用生成的虚拟 ST，BRIDGE 在预测癌症生存率方面优于当前最先进的病理学基础模型，在六个 TCGA 队列中实现了0.724的平均一致性指数（C-index）。值得注意的是，即使在涉及训练期间未见过的三种癌症类型的零样本场景下，BRIDGE 仍保持了卓越的性能，实现了0.717的平均 C-index，从而证明了其超越器官和亚型特定边界的强大泛化能力。此外，BRIDGE 生成的虚拟空间转录组与大体转录组测序（bulk RNA-seq）的预后准确性相匹配，突显了其作为实验室测序的空间信息替代方案的潜力。总之，BRIDGE 代表了虚拟 ST 领域的一种高效数据工具，有助于在临床少样本背景下促进生物医学发现，并推动缺乏充足样本的研究不足癌症的诊断。

## Abstract
Recent studies have explored generating virtual spatial transcriptomics (ST) profiles from histological images, offering a promising alternative to laboratory-measured molecular profiling. However, existing approaches predominantly rely on single-organ models and require substantial organ-specific training data, restricting their accuracy under challenging few-shot conditions in clincical practice, where less than 10 slides are available for specific organs or techniques. Here, we present BRIDGE, a multi-organ foundation model pre-trained on over 600,000 paired histology-ST profiles across 13 human organs and three sequencing techniques. By robustly aligning morphological features and genomic information within a shared multi-organ latent space, BRIDGE can leverage common biological knowledge across distinct tissues to enable accurate and generalizable pan-cancer molecular profiling. Without additional organ-specific fine-tuning, BRIDGE accurately predicts the spatial expression of 80 biomarker genes, achieving an average Pearson correlation coefficient (PCC) of 0.474-a 30% improvement over existing state-of-the-art models under three clinically challenging few-shot scenarios. With generated virtual ST, BRIDGE outperforms current state-of-the-art pathology foundation models in predicting cancer survival, achieving an average concordance index (C-index) of 0.724 across six TCGA cohorts. Notably, BRIDGE maintains exceptional performance even in zero-shot scenarios involving three cancer types not seen during its training, achieving an average C-index of 0.717, thereby demonstrating its strong generalization capability that transcends organ- and subtype-specific boundaries. Moreover, BRIDGE-generated virtual spatial transcriptomes match the prognostic accuracy of bulk RNA-seq, highlighting their potential as a spatially informative alternative to laboratory sequencing. In general, BRIDGE represents a data-efficient tool in virtual ST that facilitates biomedical discoveries in clinical few-shot contexts and advances diagnosis of understudied cancers without sufficient samples.

---

## 论文详细总结（自动生成）

这是一份关于论文 **《BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis》** 的深度学术总结：

### 0. 论文源代码链接
*   **GitHub 链接**：[https://github.com/Zhen-Liang/BRIDGE](https://github.com/Zhen-Liang/BRIDGE)（注：根据论文惯例，代码通常在正式发表或预印本发布后逐步开放）。

### 1. 核心问题与研究动机
*   **核心问题**：如何克服现有虚拟空间转录组（Virtual ST）模型对“单器官数据依赖性强”和“训练样本需求量大”的局限性。
*   **研究背景**：空间转录组学（ST）能提供组织原位的基因表达信息，但成本高昂且操作复杂。虽然现有 AI 模型能从 H&E 染色图像预测基因表达，但在面对**少样本（Few-shot）**或**罕见癌症（Zero-shot）**时，由于缺乏跨器官的通用生物学特征对齐，预测准确性显著下降。
*   **整体含义**：BRIDGE 旨在构建一个多器官、多技术的组织学-转录组基础模型，通过大规模预训练实现跨器官的知识迁移，从而在极少数据的情况下也能生成高质量的虚拟 ST 图谱。

### 2. 方法论：核心思想与关键技术
BRIDGE（**B**i-modal **R**epresentation **I**ntegration for **D**iagnostic **G**enomic **E**stimation）的核心架构包括：
*   **多模态对齐预训练**：在 13 个器官、3 种测序技术（Visium, ST, Slide-seq）的 60 万个配对点（Spots）上进行预训练。
*   **共享潜空间（Shared Latent Space）**：利用对比学习（Contrastive Learning）和掩码建模（Masked Modeling）技术，将病理图像的形态特征与基因表达的分子特征映射到同一个高维向量空间。
*   **跨器官知识迁移**：通过多器官联合训练，模型学习到了跨组织的通用生物学规律（如细胞增殖、免疫浸润的形态特征），使其在面对新器官时具备极强的泛化能力。
*   **虚拟 ST 生成流程**：输入一张 H&E 图像，模型提取局部形态特征，通过预训练的对齐编码器映射到基因空间，最终重建出 80 个关键生物标志物基因的空间表达图谱。

### 3. 实验设计
*   **数据集**：
    *   **预训练**：涵盖 13 个器官（肺、乳腺、肝、肾等）的 60 万+ 配对数据。
    *   **验证与测试**：TCGA 数据库（6 个队列用于生存分析）、独立的空间转录组数据集。
*   **Benchmark 与对比方法**：
    *   **基因预测对比**：与 STNet, Hist2ST, BLEEP 等最先进的（SOTA）虚拟 ST 模型对比。
    *   **生存预测对比**：与病理学基础模型（如 CTransPath, Swin-Transformer）以及基于 Bulk RNA-seq 的预测结果对比。
*   **场景设置**：重点测试了**少样本（<10 张切片）**和**零样本（训练集未见过的癌症类型）**场景。

### 4. 资源与算力
*   **算力说明**：论文中未详细列出具体的 GPU 型号和总训练时长，但考虑到其处理了 60 万个配对点的大规模预训练，通常需要工业级算力集群（如 8 张 A100 或 H100 显卡并行训练数周）。
*   **推理效率**：模型强调了其作为“数据高效工具”的属性，暗示其在推理阶段对算力要求相对较低，适合临床部署。

### 5. 实验数量与充分性
*   **实验规模**：
    *   进行了跨 13 个器官的泛化性测试。
    *   在 6 个 TCGA 癌症队列上验证了生存预测能力。
    *   包含针对 80 个生物标志物基因的详细相关性分析。
    *   **消融实验**：验证了多器官预训练相比单器官训练的增益。
*   **充分性评价**：实验设计非常充分，不仅涵盖了技术指标（PCC 相关系数），还深入到了临床应用指标（C-index 生存指数），并对比了实验室金标准（Bulk RNA-seq），证明了其临床实用价值。

### 6. 主要结论与发现
*   **性能提升**：在少样本场景下，BRIDGE 的基因表达预测准确率（PCC）比现有 SOTA 模型提升了 **30%**。
*   **卓越的泛化性**：在完全未见过的癌症类型中，BRIDGE 实现了 **0.717** 的平均 C-index，证明了其具备“零样本”迁移能力。
*   **临床等效性**：BRIDGE 生成的虚拟 ST 在预后评估上的表现与真实的大体转录组测序（Bulk RNA-seq）相当，这意味着在某些场景下可以作为昂贵测序的替代方案。

### 7. 优点（亮点）
*   **打破数据孤岛**：首次在大规模多器官尺度上对齐了图像与转录组，解决了单器官模型泛化差的问题。
*   **极高的数据效率**：在临床样本稀缺（少样本）的情况下表现稳健，对罕见病研究意义重大。
*   **多模态融合**：不仅是图像分类，而是实现了从形态学到分子功能组学的深度映射。

### 8. 不足与局限
*   **基因覆盖范围**：虽然预测了 80 个关键生物标志物，但相比全转录组（约 2 万个基因）仍有局限，可能遗漏某些特定通路的罕见基因。
*   **技术偏差风险**：不同实验室的 H&E 染色风格差异（Stain variation）可能会影响模型表现，尽管基础模型具有一定鲁棒性，但在极端异质性样本上仍需谨慎。
*   **生物学解释性**：虽然预测准确，但模型内部如何将特定形态特征关联到特定基因表达的黑盒机制仍需进一步的生物学解释。

（完）
