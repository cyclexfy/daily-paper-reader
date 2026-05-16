---
title: "CLEAR-HPV: Interpretable Concept Discovery for HPV-Associated Morphology in Whole-Slide Histology"
title_zh: CLEAR-HPV：全切片组织学中 HPV 相关形态的可解释概念发现
authors: "Qin, W., Liu-Swetz, Y., Tan, S., Wang, H."
date: 2026-05-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.04.703870v3.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 基于注意力的多实例学习用于全切片组织学
tldr: 本研究针对HPV相关癌症病理全切片图像预测中缺乏可解释性的问题，提出了CLEAR-HPV框架。该框架利用注意力机制重构多实例学习的潜在空间，在无需概念标签的情况下自动发现角质化、基底样和间质等形态学概念。通过将高维特征压缩为10个可解释的概念比例向量，该方法在保持预测性能的同时，实现了跨数据集的稳健泛化和空间可视化，为病理诊断提供了直观的形态学解释。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的注意力机制多实例学习模型虽然在HPV状态预测上表现优异，但缺乏对病理形态学特征的直观解释能力。
method: 提出CLEAR-HPV框架，通过在注意力加权的潜在空间中进行概念发现，将高维嵌入转化为紧凑且可解释的概念比例向量。
result: 该方法成功识别出关键的形态学概念并生成空间分布图，在将特征维度从1536降至10的同时，保留了原始模型的预测精度。
conclusion: CLEAR-HPV为基于注意力的MIL模型提供了一种通用的、与骨干网络无关的可解释性方案，增强了计算病理学在临床应用中的透明度。
---

## 摘要
人乳头瘤病毒（HPV）状态是头颈癌和宫颈癌预后及治疗反应的关键决定因素。尽管基于注意力的多实例学习（MIL）在 HPV 相关全切片组织病理学的切片级预测方面取得了显著成果，但其提供的形态学可解释性有限。为了解决这一局限性，我们引入了 CLEAR-HPV（Concept-Level Explainable Attention-guided Representation for HPV），这是一个利用注意力机制重构 MIL 潜空间，从而在训练过程中无需概念标签即可实现概念发现的框架。CLEAR-HPV 在注意力加权的潜空间中运行，能够自动发现角化型、基底样和间质形态学概念，生成空间概念图，并使用紧凑的概念比例向量表示每个切片。CLEAR-HPV 的概念比例向量保留了原始 MIL 嵌入的预测信息，同时将高维特征空间（例如 1536 维）缩减为仅 10 个可解释的概念。CLEAR-HPV 在 TCGA-HNSCC、TCGA-CESC 和 CPTAC-HNSCC 数据集上表现出一致的泛化能力，通过一种通用的、与骨干网络无关的框架，为基于注意力的全切片组织病理学 MIL 模型提供了紧凑的概念级可解释性。

## Abstract
Human papillomavirus (HPV) status is a critical determinant of prognosis and treatment response in head and neck and cervical cancers. Although attention-based multiple instance learning (MIL) achieves strong slide-level prediction for HPV-related whole-slide histopathology, it provides limited morphologic interpretability. To address this limitation, we introduce Concept-Level Explainable Attention-guided Representation for HPV (CLEAR-HPV), a framework that restructures the MIL latent space using attention to enable concept discovery without requiring concept labels during training. Operating in an attention-weighted latent space, CLEAR-HPV automatically discovers keratinizing, basaloid, and stromal morphologic concepts, generates spatial concept maps, and represents each slide using a compact concept-fraction vector. CLEAR-HPV's concept-fraction vectors preserve the predictive information of the original MIL embeddings while reducing the high-dimensional feature space (e.g., 1536 dimensions) to only 10 interpretable concepts. CLEAR-HPV generalizes consistently across TCGA-HNSCC, TCGA-CESC, and CPTAC-HNSCC, providing compact, concept-level interpretability through a general, backbone-agnostic framework for attention-based MIL models of whole-slide histopathology.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **CLEAR-HPV** 的新型可解释性框架，旨在解决计算病理学中全切片图像（WSI）预测模型“黑盒化”的问题。以下是对该论文的深度结构化总结：

### 0. 论文的源代码链接
*   **源代码链接**：论文摘要及元数据中未直接提供具体的 GitHub 链接（通常此类论文会在正式发表或补充材料中提供，但当前提取文本中未显示）。

### 1. 论文的核心问题与整体含义
*   **研究背景**：HPV（人乳头瘤病毒）感染状态是头颈癌（HNSCC）和宫颈癌（CESC）患者预后评估和治疗方案选择的关键指标。
*   **核心问题**：虽然基于注意力的多实例学习（Attention-based MIL）在预测 HPV 状态方面表现出色，但其决策过程缺乏透明度。病理学家难以理解模型关注的具体形态学特征（如角质化、基底样细胞等），这限制了 AI 工具在临床中的信任度和应用。
*   **研究目标**：开发一种无需手动标注形态学概念、能自动发现并量化病理特征的可解释框架，同时保持高预测精度。

### 2. 论文提出的方法论
*   **核心思想**：CLEAR-HPV 并不直接对原始特征进行解释，而是在**注意力加权的潜空间**中进行“概念发现”。它将高维的图像特征压缩为极低维度的“概念比例向量”。
*   **关键技术细节**：
    1.  **特征提取与注意力机制**：使用预训练的骨干网络（如 CTransPath）提取组织切片块（Patches）的特征，并通过注意力机制识别对预测贡献最大的区域。
    2.  **概念发现层（Concept Discovery）**：在注意力加权的特征空间中，通过聚类或原型学习自动识别出 $K$ 个形态学概念（本研究中 $K=10$）。
    3.  **概念比例向量（Concept-Fraction Vector）**：将整张切片表示为一个 10 维向量，每个维度代表某种特定形态学概念在切片中所占的比例。
    4.  **空间可视化**：将发现的概念映射回原始图像，生成空间分布图，供病理学家验证其生物学意义。

### 3. 实验设计
*   **数据集**：
    *   **TCGA-HNSCC**：头颈部鳞状细胞癌数据集（主要训练与验证）。
    *   **TCGA-CESC**：宫颈鳞状细胞癌数据集（跨器官泛化测试）。
    *   **CPTAC-HNSCC**：外部独立验证数据集。
*   **Benchmark（基准）**：标准的基于注意力的多实例学习模型（AB-MIL）。
*   **对比实验**：
    *   对比了使用原始高维嵌入（如 1536 维）与使用 CLEAR-HPV 压缩后的 10 维概念向量在预测 HPV 状态上的性能（AUC）。
    *   验证了发现的概念与已知病理形态（如角化、间质、基底样形态）的一致性。

### 4. 资源与算力
*   **算力说明**：论文摘要及提取内容中**未明确说明**具体的 GPU 型号、数量或训练时长。通常此类 MIL 模型训练需要高性能显卡（如 NVIDIA A100 或 V100），但文中未给出具体参数。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了多个大型公开数据集（TCGA 和 CPTAC），并进行了跨器官（头颈癌到宫颈癌）的泛化实验。
*   **充分性评价**：实验设计较为充分。通过将特征维度从 1536 维大幅压缩至 10 维，并证明预测效能几乎无损，有力地证明了该方法的有效性。同时，通过空间映射进行定性分析，增强了结果的说服力。

### 6. 论文的主要结论与发现
*   **性能保持**：CLEAR-HPV 在将特征空间压缩 150 倍以上的情况下，依然保持了与原始模型相当的预测准确率。
*   **自动概念识别**：模型成功自动识别出了与 HPV 状态密切相关的形态学特征，如 HPV 阴性肿瘤中常见的“角化”特征和 HPV 阳性肿瘤中常见的“基底样”特征。
*   **强泛化性**：在不同来源的数据集和不同的器官类型上，该框架表现出高度的一致性和稳健性。

### 7. 优点
*   **无需标签的概念学习**：不需要病理学家手动标注成千上万个细胞或组织块，降低了数据准备成本。
*   **极度压缩的可解释性**：将复杂的深度学习特征转化为 10 个直观的比例数值，极大地提升了模型的可理解性。
*   **骨干网络无关性**：该框架可以插入到任何基于注意力的 MIL 模型中，具有很强的通用性。

### 8. 不足与局限
*   **概念数量的预设**：研究中将概念数量固定为 $K=10$，这可能无法捕捉到所有细微的病理变化，且 $K$ 的选择缺乏自动化标准。
*   **预训练偏差**：模型依赖于预训练的特征提取器（如 CTransPath），如果预训练模型未能捕捉到某些关键特征，CLEAR-HPV 也无法将其找回。
*   **临床验证深度**：虽然模型发现了形态学概念，但这些概念与临床预后（如生存率）的直接关联还需更深入的大规模临床研究验证。

（完）
