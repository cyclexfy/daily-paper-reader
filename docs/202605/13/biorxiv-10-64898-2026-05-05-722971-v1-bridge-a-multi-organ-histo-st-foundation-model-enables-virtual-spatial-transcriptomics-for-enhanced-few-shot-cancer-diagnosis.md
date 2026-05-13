---
title: "BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis"
title_zh: BRIDGE：一种多器官组织学-空间转录组学基础模型，可实现虚拟空间转录组学以增强少样本癌症诊断
authors: "Liang, Z., ZHAO, W., Wang, F., Chen, G., Huang, Y., Yu, L."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.722971v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 病理与空间转录组的多器官基础模型
tldr: 本研究提出BRIDGE，一个多器官组织学-空间转录组学（ST）基础模型，旨在解决现有虚拟ST生成方法依赖单器官数据且在少样本场景下表现不佳的问题。该模型在13个器官、3种测序技术的60多万对数据上进行预训练，通过对齐形态学与基因组特征，实现了跨组织的生物学知识迁移。BRIDGE在少样本和零样本癌症诊断及生存预测中表现卓越，为临床样本稀缺情况下的分子分析提供了高效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的虚拟空间转录组生成方法通常局限于单器官且需要大量特定数据，难以应对临床中样本量极少的少样本诊断挑战。
method: 开发了名为BRIDGE的多器官基础模型，通过在跨13个器官的大规模配对组织学-ST数据上进行预训练，将形态特征与基因组信息对齐。
result: "在少样本场景下，BRIDGE对80个生物标志物基因的预测准确率提升了30%，且在生存预测任务中达到了0.724的平均一致性指数。"
conclusion: BRIDGE证明了多器官预训练能显著提升虚拟ST的泛化能力，为研究样本不足的癌症类型提供了强大的空间分子分析手段。
---

## 摘要
最近的研究探索了从组织学图像生成虚拟空间转录组学（ST）图谱的方法，为实验室测量的分子分析提供了一种极具前景的替代方案。然而，现有方法主要依赖于单器官模型，且需要大量的器官特异性训练数据，这限制了它们在临床实践中具有挑战性的少样本情况下的准确性，即针对特定器官或技术仅有不到10张切片可用。在此，我们提出了 BRIDGE，这是一个在跨越13个人类器官和三种测序技术的超过60万对组织学-ST图谱上进行预训练的多器官基础模型。通过在共享的多器官潜空间中稳健地对齐形态特征和基因组信息，BRIDGE 可以利用不同组织间的共同生物学知识，实现准确且具有泛化能力的泛癌分子分析。在无需额外器官特异性微调的情况下，BRIDGE 准确预测了80个生物标志物基因的空间表达，平均皮尔逊相关系数（PCC）达到0.474，在三种临床挑战性的少样本场景下比现有最先进模型提升了30%。利用生成的虚拟 ST，BRIDGE 在预测癌症生存率方面优于目前最先进的病理学基础模型，在六个 TCGA 队列中实现了0.724的平均一致性指数（C-index）。值得注意的是，即使在涉及训练期间未见过的三种癌症类型的零样本场景下，BRIDGE 仍保持了卓越的性能，平均 C-index 达到0.717，从而证明了其超越器官和亚型特定界限的强大泛化能力。此外，BRIDGE 生成的虚拟空间转录组与 bulk RNA-seq 的预后准确性相匹配，突显了其作为实验室测序的空间信息替代方案的潜力。总的来说，BRIDGE 代表了虚拟 ST 领域的一种高效数据工具，有助于在临床少样本背景下促进生物医学发现，并推进缺乏充足样本的未充分研究癌症的诊断。

## Abstract
Recent studies have explored generating virtual spatial transcriptomics (ST) profiles from histological images, offering a promising alternative to laboratory-measured molecular profiling. However, existing approaches predominantly rely on single-organ models and require sub-stantial organ-specific training data, restricting their accuracy under challenging few-shot conditions in clincical practice, where less than 10 slides are available for specific organs or techniques. Here, we present BRIDGE, a multi-organ foundation model pre-trained on over 600,000 paired histology-ST profiles across 13 human organs and three sequencing techniques. By robustly aligning morphological features and genomic information within a shared multi-organ latent space, BRIDGE can leverage common biological knowledge across distinct tissues to enable accurate and generalizable pan-cancer molecular profiling. Without additional organ-specific fine-tuning, BRIDGE accurately predicts the spatial expression of 80 biomarker genes, achieving an average Pearson correlation coefficient (PCC) of 0.474--a 30% improvement over existing state-of-the-art models under three clinically challenging few-shot scenarios. With generated virtual ST, BRIDGE outperforms current state-of-the-art pathology foundation models in predicting cancer survival, achieving an average concordance index (C-index) of 0.724 across six TCGA cohorts. Notably, BRIDGE maintains exceptional performance even in zero-shot scenarios involving three cancer types not seen during its training, achieving an average C-index of 0.717, thereby demonstrating its strong generalization capability that transcends organ- and subtype-specific boundaries. Moreover, BRIDGE-generated virtual spatial transcriptomes match the prognostic accuracy of bulk RNA-seq, highlighting their potential as a spatially informative alternative to laboratory sequencing. In general, BRIDGE represents a data-efficient tool in virtual ST that facilitates biomedical discoveries in clinical few-shot contexts and advances diagnosis of understudied cancers without sufficient samples.

---

## 论文详细总结（自动生成）

以下是对论文《BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis》的结构化深入总结：

### 0. 源代码链接
*   **GitHub:** [https://github.com/tracy666/BRIDGE](https://github.com/tracy666/BRIDGE)

### 1. 论文的核心问题与整体含义
*   **研究背景：** 空间转录组学（ST）能同时提供组织形态和分子信息，对癌症诊断至关重要。但 ST 技术成本高昂、操作复杂且数据稀缺。
*   **核心问题：** 现有的“虚拟 ST”生成模型（从 H&E 染色切片预测基因表达）大多依赖单器官训练，在临床常见的**少样本（Few-shot）**场景下（如特定器官切片少于 10 张、测序技术更迭、多中心批次效应）表现极差，容易过拟合且泛化性弱。
*   **研究动机：** 开发一个多器官基础模型，通过大规模跨组织预训练，学习通用的生物学特征，从而在数据极少的情况下也能准确推断空间分子图谱。

### 2. 论文提出的方法论
*   **核心思想：** 构建名为 **BRIDGE** 的双模态基础模型，通过**对比学习**和**生成式学习**的结合，在共享的潜空间中对齐组织学图像特征与基因组信息。
*   **关键技术细节：**
    *   **视觉编码器：** 采用 DenseNet-121（ImageNet 预训练），将 224x224 的组织图像块编码为视觉嵌入。
    *   **基因组编码器：** 采用 TabNet，专门处理表格化的基因表达数据，并引入掩码建模（MLM）增强鲁棒性。
    *   **多任务损失函数：**
        1.  **对比损失 (InfoNCE)：** 强制对齐配对的图像和基因嵌入。
        2.  **生成损失 (MSE)：** 监督模型直接从图像特征预测基因表达。
        3.  **重建损失：** 确保基因编码器在部分数据缺失（掩码）时仍能恢复原始信息。
    *   **推理模式：** 支持“直接预测”和“检索式推理”（利用参考库如 scRNA-seq 匹配最相似的表达谱）。

### 3. 实验设计
*   **数据集：** 自建 **BIG-600K** 数据集，包含来自 13 个人类器官、3 种测序技术的 60 多万个配对点位。
*   **测试场景：**
    1.  **少样本场景：** 数据稀缺（如卵巢、鼻咽）、技术变异（10X Visium vs. 早期 ST 技术）、多实验室来源混合。
    2.  **生存预测：** 使用 TCGA 数据库中 6 个队列（包括 3 个训练集未见过的癌症类型进行零样本测试）。
*   **Benchmark 与对比方法：**
    *   **ST 预测：** ST-Net, DeepSpaCE, Hist2ST, THItoGene, BLEEP 等。
    *   **生存预测：** 顶级病理基础模型（UNI, CONCH, CTransPath, HIPT, PLIP, QuiltNet, DINOv2）以及实验测量的 Bulk RNA-seq。

### 4. 资源与算力
*   **硬件：** 使用了 **8 块 NVIDIA GeForce RTX 3090 GPU**。
*   **训练细节：** 
    *   总 Batch Size 为 384，采用梯度累积（step=2）。
    *   单器官模型训练 20 epoch；多器官基础模型训练 **50 epoch**（每 epoch 处理约 50 万对数据）。
    *   使用了线性预热和余弦退火学习率调度。

### 5. 实验数量与充分性
*   **实验规模：** 涵盖 13 个器官，重点评估了 80 个具有临床诊断意义的生物标志物基因。
*   **充分性：** 实验设计非常严谨，不仅对比了传统的单器官模型，还挑战了**零样本（Zero-shot）**泛化实验（针对未见过的癌症类型和亚型）。通过消融实验验证了多器官联合训练的优越性，并对比了当前最先进的巨型病理基础模型，实验结果具有高度的客观性和说服力。

### 6. 主要结论与发现
*   **性能飞跃：** 在少样本场景下，BRIDGE 的预测准确率（PCC）比现有最强模型提升了 **30%**（平均 PCC 达 0.474）。
*   **生存预测优势：** BRIDGE 在 TCGA 任务中的平均 C-index 达到 **0.724**，优于参数量大得多的 UNI 模型（0.704），且在零样本癌症中依然保持 0.717 的高水平。
*   **替代潜力：** BRIDGE 生成的虚拟 ST 预后能力与金标准 Bulk RNA-seq 相当，甚至在某些挑战性亚型（如三阴性乳腺癌）中表现更优。
*   **跨模态能力：** 成功实现了从组织图像到单细胞测序（scRNA-seq）参考库的跨模态检索。

### 7. 优点
*   **数据高效性：** 证明了通过基因组信息的显式对齐，较小规模的模型（19.6M 参数）可以超越纯视觉预训练的巨型模型。
*   **强大的泛化性：** 能够跨器官迁移生物学知识，解决了罕见癌症缺乏训练数据的痛点。
*   **临床落地性：** 直接利用常规 H&E 切片生成分子信息，极大地降低了精准医疗的成本。

### 8. 不足与局限
*   **物理分辨率限制：** 预测的分辨率受限于训练数据的原始分辨率（约 55-100μm），尚未达到真正的亚细胞级精度。
*   **数据偏差风险：** 尽管涵盖 13 个器官，但对于某些极罕见病理亚型的覆盖可能仍不平衡。
*   **检索依赖性：** 检索式推理的效果高度依赖于外部参考数据库（如 scRNA-seq 库）的质量和多样性。

（完）
