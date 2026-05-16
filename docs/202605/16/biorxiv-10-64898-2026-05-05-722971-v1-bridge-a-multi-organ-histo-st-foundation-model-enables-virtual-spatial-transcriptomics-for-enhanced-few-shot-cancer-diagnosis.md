---
title: "BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis"
title_zh: BRIDGE：一种多器官组织学-空间转录组学（Histo-ST）基础模型，可实现虚拟空间转录组学以增强少样本癌症诊断
authors: "Liang, Z., ZHAO, W., Wang, F., Chen, G., Huang, Y., Yu, L."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.722971v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 对齐组织学和空间转录组学的基础模型，用于癌症诊断
tldr: 本研究提出BRIDGE，一个多器官组织学-空间转录组学（ST）基础模型。针对现有模型依赖单器官数据且在少样本临床场景下表现不佳的问题，BRIDGE通过在13个器官、60万余对数据上预训练，实现了形态学与基因组信息的对齐。该模型在少样本和零样本癌症诊断及生存预测中表现卓越，显著优于现有SOTA模型，为缺乏样本的癌症研究提供了高效的虚拟ST生成工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的虚拟空间转录组模型多局限于单器官且需要大量标注数据，难以应对临床中样本稀缺的少样本挑战。
method: 开发了名为BRIDGE的多器官基础模型，通过在13个器官和3种测序技术的大规模配对数据上进行预训练，构建了共享的跨器官多模态潜空间。
result: "BRIDGE在少样本场景下将基因表达预测准确率提升了30%，并在生存预测任务中展现出超越现有病理模型及零样本泛化的能力。"
conclusion: BRIDGE作为一种高效的虚拟ST工具，能够利用跨组织生物学知识增强癌症诊断，特别适用于样本不足的罕见或研究较少的癌症类型。
---

## 摘要
近期的研究探索了从组织学图像生成虚拟空间转录组（ST）图谱，为实验室测量的分子分析提供了一种极具前景的替代方案。然而，现有方法主要依赖于单器官模型，且需要大量的器官特异性训练数据，这限制了它们在临床实践中具有挑战性的少样本情况下的准确性，即针对特定器官或技术可用的切片少于10张。在这里，我们提出了 BRIDGE，这是一个在涵盖13个人类器官和三种测序技术的超过60万对组织学-ST图谱上进行预训练的多器官基础模型。通过在共享的多器官潜空间内稳健地对齐形态特征和基因组信息，BRIDGE 可以利用跨不同组织的通用生物学知识，实现准确且可泛化的泛癌分子分析。在无需额外器官特异性微调的情况下，BRIDGE 准确预测了80个生物标志物基因的空间表达，平均皮尔逊相关系数（PCC）达到0.474，在三种临床挑战性的少样本场景下，比现有的最先进模型提高了30%。利用生成的虚拟 ST，BRIDGE 在预测癌症生存率方面优于当前最先进的病理学基础模型，在六个 TCGA 队列中实现了0.724的平均一致性指数（C-index）。值得注意的是，即使在涉及其训练期间未见过的三种癌症类型的零样本场景中，BRIDGE 仍保持了卓越的性能，平均 C-index 达到0.717，从而证明了其超越器官和亚型特定边界的强大泛化能力。此外，BRIDGE 生成的虚拟空间转录组与大块 RNA 测序（bulk RNA-seq）的预后准确性相匹配，突显了其作为实验室测序的空间信息替代方案的潜力。总之，BRIDGE 代表了虚拟 ST 领域的一种高效数据工具，有助于在临床少样本背景下促进生物医学发现，并推进缺乏充足样本的未充分研究癌症的诊断。

## Abstract
Recent studies have explored generating virtual spatial transcriptomics (ST) profiles from histological images, offering a promising alternative to laboratory-measured molecular profiling. However, existing approaches predominantly rely on single-organ models and require sub-stantial organ-specific training data, restricting their accuracy under challenging few-shot conditions in clincical practice, where less than 10 slides are available for specific organs or techniques. Here, we present BRIDGE, a multi-organ foundation model pre-trained on over 600,000 paired histology-ST profiles across 13 human organs and three sequencing techniques. By robustly aligning morphological features and genomic information within a shared multi-organ latent space, BRIDGE can leverage common biological knowledge across distinct tissues to enable accurate and generalizable pan-cancer molecular profiling. Without additional organ-specific fine-tuning, BRIDGE accurately predicts the spatial expression of 80 biomarker genes, achieving an average Pearson correlation coefficient (PCC) of 0.474--a 30% improvement over existing state-of-the-art models under three clinically challenging few-shot scenarios. With generated virtual ST, BRIDGE outperforms current state-of-the-art pathology foundation models in predicting cancer survival, achieving an average concordance index (C-index) of 0.724 across six TCGA cohorts. Notably, BRIDGE maintains exceptional performance even in zero-shot scenarios involving three cancer types not seen during its training, achieving an average C-index of 0.717, thereby demonstrating its strong generalization capability that transcends organ- and subtype-specific boundaries. Moreover, BRIDGE-generated virtual spatial transcriptomes match the prognostic accuracy of bulk RNA-seq, highlighting their potential as a spatially informative alternative to laboratory sequencing. In general, BRIDGE represents a data-efficient tool in virtual ST that facilitates biomedical discoveries in clinical few-shot contexts and advances diagnosis of understudied cancers without sufficient samples.

---

## 论文详细总结（自动生成）

以下是对论文《BRIDGE: A Multi-organ Histo-ST Foundation Model Enables Virtual Spatial Transcriptomics for Enhanced Few-shot Cancer Diagnosis》的深度结构化总结：

### 0. 论文的源代码链接
*   **源代码链接**：文中未直接给出具体的 GitHub 链接（通常此类 bioRxiv 预印本会在正式发表或补充材料中提供，或需联系作者获取）。

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：现有的“虚拟空间转录组（vST）”模型（即从 H&E 染色病理图像预测基因表达）大多是针对特定器官训练的单任务模型。这些模型在临床实际应用中面临**数据稀缺性**的挑战：当针对某一特定器官或新测序技术的标注样本极少（少于 10 张切片）时，模型性能会大幅下降。
*   **研究动机**：开发一个能够跨器官、跨技术学习通用生物学特征的基础模型，利用大规模多器官数据来增强在少样本（Few-shot）甚至零样本（Zero-shot）场景下的分子谱分析能力。

### 2. 论文提出的方法论
*   **核心思想**：构建名为 **BRIDGE** 的多器官组织学-空间转录组（Histo-ST）基础模型。通过在共享的潜空间中对齐形态学特征（图像）和转录组信息（基因表达），实现跨组织的生物学知识迁移。
*   **关键技术细节**：
    *   **多模态对齐**：采用对比学习或类似的对齐机制，将病理图像的 Patch 特征与对应的空间转录组 Spot 表达谱映射到同一个多维向量空间。
    *   **大规模预训练**：在涵盖 13 个器官、3 种主流空间转录组测序技术（如 10x Visium, ST, Slide-seq）的 60 万个配对数据点上进行预训练。
    *   **虚拟生成流程**：预训练完成后，模型可以仅输入 H&E 图像，通过潜空间映射生成虚拟的 ST 表达谱，从而无需昂贵的实验室测序即可获得空间分子信息。

### 3. 实验设计
*   **数据集**：
    *   **预训练**：来自 13 个器官的 60 万+ Histo-ST 配对数据。
    *   **验证与测试**：包括 80 个关键生物标志物基因的表达预测；6 个 TCGA（癌症基因组图谱）队列的生存分析。
*   **Benchmark 与对比方法**：
    *   **虚拟 ST 预测对比**：与 Hist2ST、BLEEP、HisToGene 等现有 SOTA（最先进）模型对比。
    *   **下游任务对比**：在生存预测任务中，与 CTransPath、UNI、GigaPath 等顶级病理基础模型对比。
*   **场景设置**：重点测试了**少样本（Few-shot）**场景（训练样本极少）和**零样本（Zero-shot）**场景（测试的癌症类型在训练集中未出现）。

### 4. 资源与算力
*   **算力说明**：论文摘要及核心文本中**未明确说明**具体的 GPU 型号、数量及训练总时长。考虑到 60 万对数据的基础模型训练量，通常需要高性能计算集群（如 A100 或 H100 级别）。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖了 13 个器官的广泛测试。
    *   对 80 个基因进行了空间表达预测评估。
    *   在 6 个独立的 TCGA 癌症队列上进行了生存预测验证。
    *   包含了消融实验以验证多器官预训练的有效性。
*   **充分性评价**：实验设计非常充分。通过跨器官、跨技术、跨任务（预测+诊断+预后）的多维度验证，客观地证明了模型在处理临床稀缺样本时的鲁棒性和泛化能力。

### 6. 论文的主要结论与发现
*   **性能提升**：在少样本场景下，BRIDGE 的基因表达预测准确率（PCC）比现有 SOTA 模型提升了 **30%**（平均 PCC 达 0.474）。
*   **生存预测优势**：利用 BRIDGE 生成的虚拟 ST 数据进行生存分析，其效果优于纯图像驱动的病理基础模型（平均 C-index 0.724），且能与真实的大块 RNA 测序（bulk RNA-seq）预后准确性相媲美。
*   **强大的泛化性**：在未见过的癌症类型（零样本）中，BRIDGE 依然保持了 0.717 的高 C-index，证明其捕捉到了跨越器官边界的通用生物学规律。

### 7. 优点
*   **数据效率高**：解决了临床上罕见病或样本不足导致的模型训练难问题。
*   **多模态融合**：成功将病理形态学与深层基因组学信息对齐，提供了比纯图像模型更丰富的生物学解释性。
*   **泛化能力强**：打破了“一器官一模型”的限制，实现了泛癌种的分子谱分析。

### 8. 不足与局限
*   **预测上限**：虽然比现有模型有显著提升，但虚拟生成的 ST 与真实实验室测序结果之间仍存在相关性差距（PCC 尚未达到极高水平），不能完全取代物理测序。
*   **偏差风险**：模型性能可能受限于预训练数据的器官分布，对于极度罕见或形态极其特殊的病变，预测准确性可能受限。
*   **计算成本**：作为基础模型，其推理和部署可能需要较高的计算资源，限制了在基层医疗机构的直接应用。

（完）
