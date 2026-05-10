---
title: "BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis"
title_zh: BRIDGE：一种多器官组织学-空间转录组学基础模型，可实现虚拟空间转录组学以增强少样本癌症诊断
authors: "Liang, Z., ZHAO, W., Wang, F., Chen, G., Huang, Y., Yu, L."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.722971v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 多器官基础模型对齐组织学与基因组数据用于癌症诊断
tldr: BRIDGE是一个多器官组织学-空间转录组学（ST）基础模型，通过在13个器官的60万个配对数据上预训练，实现了跨器官的生物学知识共享。它在极少样本（少于10张切片）甚至零样本情况下，能从病理图像准确生成虚拟ST谱，显著提升了癌症生存预测和生物标志物识别的精度，为临床稀有癌症诊断提供了高效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的虚拟空间转录组模型多局限于单一器官且依赖大量标注数据，难以应对临床中样本稀缺的少样本或零样本诊断场景。
method: 提出BRIDGE模型，利用来自13个器官和3种测序技术的60万组配对数据进行预训练，在共享潜空间中对齐形态学特征与基因组信息。
result: "在少样本场景下基因表达预测准确率提升30%，生存预测C-index达0.724，且在未见过的癌症类型上表现出极强的零样本泛化能力。"
conclusion: BRIDGE证明了多器官联合建模在虚拟空间转录组学中的优越性，为数据匮乏环境下的精准癌症诊断和生物医学研究提供了强有力的支持。
---

## 摘要
最近的研究探索了从组织学图像生成虚拟空间转录组（ST）图谱，为实验室测量的分子分析提供了一种极具前景的替代方案。然而，现有方法主要依赖于单器官模型，且需要大量的器官特异性训练数据，这限制了它们在临床实践中具有挑战性的少样本情况下的准确性，即针对特定器官或技术仅有不到10张切片可用。在此，我们提出了 BRIDGE，这是一个在跨越13个人类器官和三种测序技术的超过60万对组织学-ST图谱上进行预训练的多器官基础模型。通过在共享的多器官潜空间中稳健地对齐形态特征和基因组信息，BRIDGE 可以利用不同组织间的通用生物学知识，实现准确且具有泛化能力的泛癌分子分析。在无需额外器官特异性微调的情况下，BRIDGE 准确预测了80个生物标志物基因的空间表达，在三种临床挑战性的少样本场景下实现了0.474的平均皮尔逊相关系数（PCC），比现有的最先进模型提高了30%。利用生成的虚拟 ST，BRIDGE 在预测癌症生存率方面优于当前最先进的病理学基础模型，在六个 TCGA 队列中实现了0.724的平均一致性指数（C-index）。值得注意的是，即使在涉及训练期间未见过的三种癌症类型的零样本场景下，BRIDGE 仍保持了卓越的性能，实现了0.717的平均 C-index，从而证明了其超越器官和亚型特定边界的强大泛化能力。此外，BRIDGE 生成的虚拟空间转录组与大体 RNA 测序（bulk RNA-seq）的预后准确性相匹配，突显了其作为实验室测序的空间信息替代方案的潜力。总之，BRIDGE 代表了虚拟 ST 领域的一种高效数据工具，有助于在临床少样本背景下促进生物医学发现，并推动缺乏充足样本的研究不足癌症的诊断。

## Abstract
Recent studies have explored generating virtual spatial transcriptomics (ST) profiles from histological images, offering a promising alternative to laboratory-measured molecular profiling. However, existing approaches predominantly rely on single-organ models and require substantial organ-specific training data, restricting their accuracy under challenging few-shot conditions in clincical practice, where less than 10 slides are available for specific organs or techniques. Here, we present BRIDGE, a multi-organ foundation model pre-trained on over 600,000 paired histology-ST profiles across 13 human organs and three sequencing techniques. By robustly aligning morphological features and genomic information within a shared multi-organ latent space, BRIDGE can leverage common biological knowledge across distinct tissues to enable accurate and generalizable pan-cancer molecular profiling. Without additional organ-specific fine-tuning, BRIDGE accurately predicts the spatial expression of 80 biomarker genes, achieving an average Pearson correlation coefficient (PCC) of 0.474-a 30% improvement over existing state-of-the-art models under three clinically challenging few-shot scenarios. With generated virtual ST, BRIDGE outperforms current state-of-the-art pathology foundation models in predicting cancer survival, achieving an average concordance index (C-index) of 0.724 across six TCGA cohorts. Notably, BRIDGE maintains exceptional performance even in zero-shot scenarios involving three cancer types not seen during its training, achieving an average C-index of 0.717, thereby demonstrating its strong generalization capability that transcends organ- and subtype-specific boundaries. Moreover, BRIDGE-generated virtual spatial transcriptomes match the prognostic accuracy of bulk RNA-seq, highlighting their potential as a spatially informative alternative to laboratory sequencing. In general, BRIDGE represents a data-efficient tool in virtual ST that facilitates biomedical discoveries in clinical few-shot contexts and advances diagnosis of understudied cancers without sufficient samples.

---

## 论文详细总结（自动生成）

这是一份关于论文《BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis》的结构化深入总结：

### 0. 源代码链接
*   **GitHub 链接**：[https://github.com/tracy666/BRIDGE](https://github.com/tracy666/BRIDGE)

### 1. 论文的核心问题与整体含义
*   **研究动机**：空间转录组学（ST）能提供组织切片中基因表达的空间分布，对理解癌症生物学至关重要，但其成本高昂、技术复杂且数据稀缺。
*   **核心问题**：现有的“虚拟 ST”模型（从 H&E 图像预测基因表达）大多针对单一器官训练，依赖大量特定器官的数据。在临床实践中，许多器官或罕见癌症的样本极少（少于 10 张切片），导致现有模型在“少样本（Few-shot）”场景下泛化能力差、预测准确度低。
*   **整体含义**：BRIDGE 旨在通过构建一个跨 13 个器官的大规模多器官基础模型，利用不同组织间的通用生物学知识，解决数据匮乏环境下的精准分子图谱分析问题。

### 2. 论文提出的方法论
*   **核心思想**：采用双模态架构，通过对比学习（Contrastive Learning）和生成学习（Generative Learning）策略，在共享的潜空间中对齐组织形态学特征与基因组信息。
*   **关键技术细节**：
    *   **三位一体的学习目标**：
        1.  **对比损失（Contrastive Loss）**：将视觉特征和基因组特征对齐到统一的 128 维潜空间。
        2.  **生成损失（Generative Loss）**：直接从图像特征预测基因表达，增强预测精度。
        3.  **重建损失（Reconstruction Loss）**：利用掩码语言模型（MLM）思想，对基因数据进行掩码重建，确保编码器捕捉核心基因组信息。
    *   **架构组成**：
        *   **视觉编码器**：使用在 ImageNet 上预训练的 DenseNet-121。
        *   **基因组编码器**：使用专门处理表格数据的 TabNet。
        *   **解码器**：包含基因预测头和重建头。
*   **推理模式**：支持“直接预测”和“基于检索的推理”（从参考库中匹配最相似的基因谱），后者能更好地保留基因间的生物学关系。

### 3. 实验设计
*   **数据集**：
    *   **BIG-600K**：作者构建的包含 13 个器官、超过 60 万个配对组织-ST 点位的数据集。
    *   **TCGA 队列**：用于下游生存分析，涵盖 6 个队列（包括 3 个完全未见过的零样本癌症类型：膀胱癌、食管癌、胃癌）。
*   **Benchmark 与对比方法**：
    *   **ST 预测对比**：ST-Net, DeepSpaCE, Hist2ST, THItoGene, BLEEP 等。
    *   **生存预测对比**：病理基础模型（UNI, CONCH, CTransPath, HIPT 等）以及实验测量的 Bulk RNA-seq。
*   **场景设置**：低数据量（Understudied organs）、技术差异（不同测序平台）、来源混合（多实验室批次效应）。

### 4. 资源与算力
*   **硬件**：使用了 8 台 NVIDIA GeForce RTX 3090 GPU。
*   **训练细节**：
    *   总 Batch Size 为 384。
    *   单器官模型训练 20 个 Epoch，多器官基础模型训练 50 个 Epoch。
    *   使用了梯度累积（Step=2）、线性预热和余弦退火学习率调度。

### 5. 实验数量与充分性
*   **实验规模**：论文进行了大规模的跨器官验证，包括 16 张全扫描切片（WSI）的多器官评估集。
*   **充分性**：
    *   涵盖了从基因表达预测、空间模式可视化到下游临床生存分析的全流程。
    *   专门设计了**少样本（Few-shot）**和**零样本（Zero-shot）**实验，验证了模型在极端情况下的鲁棒性。
    *   对比了当前最先进的病理大模型（如拥有 3 亿参数的 UNI），实验设计客观且具有挑战性。

### 6. 论文的主要结论与发现
*   **性能飞跃**：在少样本场景下，BRIDGE 的预测准确率（PCC）比现有 SOTA 提升了 30%。
*   **零样本泛化**：即使在训练中未见过的癌症类型上，BRIDGE 的生存预测能力（C-index 0.717）依然极强，证明其学习到了跨器官的通用分子规律。
*   **超越视觉模型**：尽管参数量（19.6M）远小于 UNI 等模型，但由于引入了基因组监督，其生存预测表现更优。
*   **替代潜力**：BRIDGE 生成的虚拟 ST 在预后分析上达到了与实验室 Bulk RNA-seq 相当甚至更优的水平，且额外提供了空间上下文信息。

### 7. 优点（亮点）
*   **数据效率**：通过多器官联合训练，解决了单器官模型在数据稀缺时容易过拟合的问题。
*   **双模态对齐**：不仅能预测基因，还能实现跨模态检索（如用组织图像检索单细胞 RNA-seq 数据），极大地扩展了应用场景。
*   **临床实用性**：直接利用常规 H&E 切片生成高分辨率分子图谱，显著降低了精准医疗的成本门槛。

### 8. 不足与局限
*   **数据偏差**：尽管涵盖了 13 个器官，但不同器官间的数据分布仍不均衡（如乳腺癌数据较多，鼻咽癌极少）。
*   **分辨率限制**：受限于现有 ST 技术的训练数据，预测的分辨率主要集中在 Spot 级别（55-100μm），尚未完全达到单细胞物理分辨率。
*   **验证范围**：虽然在 TCGA 上做了零样本测试，但对于更多罕见病种和非肿瘤疾病的覆盖仍有待加强。

（完）
