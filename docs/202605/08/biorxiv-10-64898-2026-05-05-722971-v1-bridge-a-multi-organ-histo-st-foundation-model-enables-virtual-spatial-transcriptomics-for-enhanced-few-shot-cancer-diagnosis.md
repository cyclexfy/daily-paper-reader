---
title: "BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis"
title_zh: BRIDGE：一种多器官组织学-空间转录组学基础模型，可实现虚拟空间转录组学以增强少样本癌症诊断
authors: "Liang, Z., ZHAO, W., Wang, F., Chen, G., Huang, Y., Yu, L."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.722971v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 对齐组织学和基因组学用于癌症诊断的多器官基础模型
tldr: BRIDGE是一个用于虚拟空间转录组学和少样本癌症诊断的基础模型。
source: biorxiv
selection_source: fresh_fetch
motivation: 对齐组织学和基因组学用于癌症诊断的多器官基础模型。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## 摘要
最近的研究探索了从组织学图像生成虚拟空间转录组学（ST）图谱，为实验室测量的分子分析提供了一种有前景的替代方案。然而，现有方法主要依赖于单器官模型，且需要大量的器官特异性训练数据，这限制了其在临床实践中具有挑战性的少样本情况下的准确性（即特定器官或技术可用的切片少于10张）。在此，我们提出了 BRIDGE，这是一个在涵盖 13 个人类器官和三种测序技术的超过 600,000 个配对组织学-ST 图谱上预训练的多器官基础模型。通过在共享的多器官潜空间中稳健地对齐形态特征和基因组信息，BRIDGE 可以利用不同组织间的共同生物学知识，实现准确且可泛化的泛癌分子分析。在无需额外器官特异性微调的情况下，BRIDGE 准确预测了 80 个生物标志物基因的空间表达，平均皮尔逊相关系数（PCC）达到 0.474，在三种临床挑战性的少样本场景下比现有最先进模型提高了 30%。利用生成的虚拟 ST，BRIDGE 在预测癌症生存率方面优于当前最先进的病理学基础模型，在六个 TCGA 队列中实现了 0.724 的平均一致性指数（C-index）。值得注意的是，即使在涉及训练期间未见过的三种癌症类型的零样本场景中，BRIDGE 仍保持了卓越的性能，平均 C-index 达到 0.717，从而证明了其超越器官和亚型特定边界的强大泛化能力。此外，BRIDGE 生成的虚拟空间转录组与批量 RNA 测序（bulk RNA-seq）的预后准确性相匹配，突显了其作为实验室测序的空间信息替代方案的潜力。总的来说，BRIDGE 代表了虚拟 ST 领域的一种高效数据工具，有助于临床少样本背景下的生物医学发现，并推进了缺乏充足样本的未充分研究癌症的诊断。

## Abstract
Recent studies have explored generating virtual spatial transcriptomics (ST) profiles from histological images, offering a promising alternative to laboratory-measured molecular profiling. However, existing approaches predominantly rely on single-organ models and require substantial organ-specific training data, restricting their accuracy under challenging few-shot conditions in clincical practice, where less than 10 slides are available for specific organs or techniques. Here, we present BRIDGE, a multi-organ foundation model pre-trained on over 600,000 paired histology-ST profiles across 13 human organs and three sequencing techniques. By robustly aligning morphological features and genomic information within a shared multi-organ latent space, BRIDGE can leverage common biological knowledge across distinct tissues to enable accurate and generalizable pan-cancer molecular profiling. Without additional organ-specific fine-tuning, BRIDGE accurately predicts the spatial expression of 80 biomarker genes, achieving an average Pearson correlation coefficient (PCC) of 0.474-a 30% improvement over existing state-of-the-art models under three clinically challenging few-shot scenarios. With generated virtual ST, BRIDGE outperforms current state-of-the-art pathology foundation models in predicting cancer survival, achieving an average concordance index (C-index) of 0.724 across six TCGA cohorts. Notably, BRIDGE maintains exceptional performance even in zero-shot scenarios involving three cancer types not seen during its training, achieving an average C-index of 0.717, thereby demonstrating its strong generalization capability that transcends organ- and subtype-specific boundaries. Moreover, BRIDGE-generated virtual spatial transcriptomes match the prognostic accuracy of bulk RNA-seq, highlighting their potential as a spatially informative alternative to laboratory sequencing. In general, BRIDGE represents a data-efficient tool in virtual ST that facilitates biomedical discoveries in clinical few-shot contexts and advances diagnosis of understudied cancers without sufficient samples.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **BRIDGE** 的多器官组织学-空间转录组学（Histo-ST）基础模型，旨在通过常规组织学切片生成虚拟的空间转录组图谱，从而辅助癌症诊断和预后分析。

以下是对该论文的结构化总结：

### 0. 论文源代码链接
*   **GitHub 链接**：[https://github.com/tracy666/BRIDGE](https://github.com/tracy666/BRIDGE)
*   **数据集链接**：预处理后的 BIG-600K 数据集已发布在 Mendeley Data。

### 1. 论文的核心问题与整体含义
*   **研究动机**：空间转录组学（ST）能提供分子层面的空间信息，但成本高昂、技术复杂且数据稀缺。虽然已有研究尝试从组织学图像预测基因表达，但现有模型多为“单器官”模型，严重依赖特定器官的大规模训练数据。
*   **核心问题**：在临床实践中，特定器官或新技术的切片往往极少（少于10张，即少样本场景），现有模型在这些场景下泛化性差、准确度低，且难以应对不同实验室间的批次效应。
*   **整体含义**：BRIDGE 通过构建大规模多器官数据集并采用双模态对齐技术，利用跨组织的共同生物学知识，解决了少样本和零样本（未见器官）下的虚拟 ST 生成难题。

### 2. 论文提出的方法论
*   **核心思想**：将组织学图像的形态特征与空间转录组的基因组信息对齐到一个共享的多器官潜空间（Latent Space）中。
*   **关键技术细节**：
    *   **三位一体的学习目标**：同时优化对比损失（Contrastive Loss，对齐模态）、生成损失（Generative Loss，直接预测基因表达）和重建损失（Reconstruction Loss，保持基因信息保真度）。
    *   **双模态架构**：
        *   **视觉编码器**：使用在 ImageNet 上预训练的 DenseNet-121 提取图像块特征。
        *   **基因组编码器**：使用 TabNet 处理表格化的基因表达数据，并引入掩码语言模型（MLM）策略，随机掩盖 25% 的非零基因值以增强鲁棒性。
    *   **推理模式**：支持“直接预测”和“基于检索的推理”两种模式。检索模式允许从 scRNA-seq 或其他 ST 参考库中匹配最相似的基因图谱。

### 3. 实验设计
*   **数据集**：构建了 **BIG-600K** 数据集，包含来自 13 个人类器官、3 种测序技术的 60 多万个配对点。
*   **评估场景**：
    1.  **少样本场景**：低数据量（如鼻咽、卵巢）、技术变异（10X Visium 与旧 ST 技术混杂）、来源混合（多实验室批次效应）。
    2.  **零样本场景**：在完全未见过的癌症类型（膀胱癌、食管癌、胃癌）上进行生存分析。
*   **Benchmark 与对比方法**：
    *   **ST 预测对比**：ST-Net, DeepSpaCE, Hist2ST, THItoGene, BLEEP 等。
    *   **生存分析对比**：SOTA 病理基础模型（UNI, CONCH, CTransPath, PLIP, DINOv2, HIPT）以及实验测量的 Bulk RNA-seq。

### 4. 资源与算力
*   **硬件**：使用了 **8 台 NVIDIA GeForce RTX 3090 GPU**。
*   **训练细节**：
    *   多器官模型训练了 50 个 epoch（每 epoch 约 50 万对数据）。
    *   单器官模型训练了 20 个 epoch。
    *   采用了梯度累积（step=2）、线性预热和余弦退火学习率调度。

### 5. 实验数量与充分性
*   **实验规模**：论文涵盖了 13 个器官的预测实验、6 个 TCGA 癌症队列的生存分析、4 种不同配置的检索实验，以及细胞聚类性能对比。
*   **充分性与公平性**：实验设计非常详尽，不仅对比了同类 ST 预测模型，还跨界对比了参数量大得多的通用病理基础模型（如 UNI）。通过留出法（Leave-one-out）和零样本测试，客观地验证了模型的泛化能力。

### 6. 论文的主要结论与发现
*   **性能飞跃**：在少样本场景下，BRIDGE 的预测准确率（PCC）比现有 SOTA 提升了 **30%**。
*   **预后能力**：在生存预测任务中，BRIDGE 的平均 C-index 达到 0.724，优于 UNI 等超大规模视觉基础模型。
*   **零样本泛化**：在未见过的癌症类型上，BRIDGE 依然表现稳健（C-index 0.717），证明其学习到了跨器官的通用分子-形态关联。
*   **替代潜力**：BRIDGE 生成的虚拟 ST 在预后准确性上能与昂贵的 Bulk RNA-seq 相媲美，且额外提供了空间上下文信息。

### 7. 优点（亮点）
*   **多器官协同**：打破了单器官建模的局限，证明了跨器官预训练能显著提升模型在数据稀缺领域的表现。
*   **双模态融合**：结合了对比学习和生成式学习，既能对齐模态，又能保证预测的绝对数值准确。
*   **临床实用性**：模型参数量相对较小（19.6M），但效率极高，显著降低了临床采用空间基因组信息的门槛。
*   **跨模态检索**：成功实现了从组织学图像到单细胞 RNA-seq（scRNA-seq）数据的检索，开启了高分辨率虚拟 ST 的新可能。

### 8. 不足与局限
*   **数据依赖性**：虽然是多器官模型，但其性能仍受限于 BIG-600K 中包含的器官种类，对于解剖学差异极大的罕见组织可能仍需微调。
*   **空间分辨率限制**：受限于目前主流 ST 技术（如 Visium）的 spot 分辨率，模型在单细胞水平的精确形态-基因映射上仍有提升空间。
*   **验证范围**：生存分析主要基于 TCGA 队列，未来需在更多独立临床中心的数据集上验证其外部一致性。

（完）
