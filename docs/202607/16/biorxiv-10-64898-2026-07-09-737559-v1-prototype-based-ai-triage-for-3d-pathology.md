---
title: Prototype-based AI triage for 3D pathology
title_zh: 基于原型的AI分诊用于3D病理学
authors: "Yan, R., Gao, G., Song, A. H., Hsieh, H.-C., Zhao, Y., Almagro-Perez, C., Brenes, D., Chow, S. S. L., Shen, J., Reddi, D. M., True, L. D., Lal, P., Madabhushi, A., Mahmood, F., Liu, J. T. C."
date: 2026-07-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.09.737559v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 基于原型的AI分诊用于3D病理
tldr: 非破坏性3D病理学可对完整标本高分辨率成像，但数据量庞大，人工审查不现实，需AI分诊。现有模型可解释性差且性能欠佳，尤其在标记数据有限的3D病理领域。本文提出SCOPE框架，结合无监督原型预训练、分割先验引导和跨切片聚合，生成切片级风险预测。在前列腺和食管癌症数据集上，SCOPE优于注意力及原型多实例学习基线，输出病理学家可解释的形态学原型，实现深度分辨风险剖面。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1694, \"height\": 1960, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1762, \"height\": 1711, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1885, \"height\": 1791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1623, \"height\": 1967, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1667, \"height\": 1971, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1877, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1883, \"height\": 1849, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1883, \"height\": 884, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1331, \"height\": 1114, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1657, \"height\": 1102, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1093, \"height\": 1598, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1091, \"height\": 1598, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-09-737559-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1091, \"height\": 1598, \"label\": \"Table\"}]"
motivation: 3D病理数据规模大，人工审查不可行；现有AI分诊可解释性差，性能不足，尤其在标记数据匮乏时。
method: SCOPE框架：聚类预训练初始化原型，分割先验引导原型学习，跨切片聚合生成切片级风险预测。
result: 在前列腺和食管数据集上，SCOPE在二元和多元分类中均优于注意力及原型多实例学习基线。
conclusion: SCOPE提供可解释的形态学原型，实现高效且准确的3D病理分诊，提升AI辅助的可信度。
---

## 摘要
非破坏性3D病理学能够对完整临床标本进行高分辨率无切片成像，提供比传统基于切片的2D组织病理学更全面的组织结构可视化。然而，体积数据集的大小和复杂性使得详尽的手动检查变得不切实际，从而推动了AI辅助分诊方法的发展，以选择少量高风险2D切片供病理学家审查。尽管先前的分诊模型已显示出潜力，但其可解释性较差且性能可能欠佳，尤其是在标记数据有限的3D病理学这一新兴领域。我们提出了SCOPE，一种基于分割引导的跨切片原型学习框架，用于对3D病理数据集中的二维层面进行综合风险评估。SCOPE结合了(i)在大规模未标记体积数据上的聚类预训练以初始化形态感知原型，(ii)来自公开可用模型的分割衍生结构先验以指导原型学习，以及(iii)跨相邻切片的跨切片(2.5D)原型聚合以生成切片级风险预测。在前列腺和食管数据队列中，SCOPE在二分类和多分类任务上持续优于基于注意力和基于原型的多实例学习基线，使得能够基于病理学家可解释的形态原型进行深度分辨的风险分析，用于3D分诊。

## Abstract
Non-destructive 3D pathology enables high-resolution slide-free imaging of intact clinical specimens, providing comprehensive visualization of tissue structures beyond what conventional slide-based 2D histopathology can provide. However, the scale and complexity of volumetric datasets make exhaustive manual review impractical, motivating AI-assisted triage methods to select a small number of high-risk 2D slices for pathologist review. While prior triage models have shown promise, interpretability is poor and performance can be suboptimal, especially in the nascent field of 3D pathology in which labeled data is limited. We present SCOPE, a Segmentation-guided CrOss-slice PrototypE learning framework for comprehensive risk assessment of 2D levels within 3D pathology datasets. SCOPE combines (i) clustering-based pretraining on large-scale unlabeled volumetric data to initialize morphology-aware prototypes, (ii) segmentation-derived structural priors from publicly available models to guide prototype learning, and (iii) cross-slice (2.5D) prototype aggregation across neighboring slices to generate slice-level risk predictions. In prostate and esophageal data cohorts, SCOPE consistently outperforms attention-based and prototype-based multiple instance learning baselines for both binary and multiclass prediction tasks, enabling depth-resolved risk profiling for 3D triage based on morphological prototypes that are interpretable to pathologists.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容生成的结构化中文总结。

### 0. 源代码链接
无。论文中未提及源代码链接。

### 1. 核心问题与整体含义（研究动机和背景）
*   **问题**：非破坏性3D病理学能够对完整临床标本进行高分辨率、无切片的成像，提供比传统2D组织病理学更全面的组织结构信息。然而，3D数据集规模巨大、结构复杂，导致人工逐层审查不现实。
*   **动机**：亟需开发AI辅助的“分诊”方法，自动从海量3D数据中筛选出少量高风险2D切片供病理学家详细检查，以提高诊断效率。现有分诊模型存在可解释性差、性能不足的问题，尤其是在3D病理这一标记数据稀缺的新兴领域。
*   **含义**：提出一种可解释、高性能、数据高效的AI分诊框架，有助于将3D病理技术从研究推向临床实践，提升病理诊断的自动化和可信度。

### 2. 方法论：SCOPE框架
*   **核心思想**：通过**聚类预训练**初始化形态学敏感的原型，利用**分割先验**引导原型学习关注组织结构，并通过**跨切片聚合**（2.5D）结合相邻切片信息，生成可解释的切片级风险评分。
*   **关键技术细节**：
    1.  **聚类预训练**：在大规模未标记的3D体积数据上，对2D切片块进行无监督聚类，将聚类中心初始化为“原型”。这使原型在无标注情况下学会捕捉不同的组织形态模式。
    2.  **分割先验引导**：利用公开可用的分割模型（如细胞核、腺体分割）提取的结构先验（如分割掩膜），将其与原始图像特征融合，指导原型学习更注重组织学结构，而非纹理噪声。
    3.  **跨切片聚合**：对每个目标切片，聚合其相邻若干切片的信息（2.5D），通过注意力或平均池化等机制生成增强的切片表征，再利用原型匹配进行风险评分。最终输出每个切片的二元（高风险/低风险）或多元（如不同风险等级）风险预测。
*   **算法流程**（文字描述）：
    1.  **原型初始化**：从未标记3D数据中提取大量2D块，使用k-means聚类，得到K个聚类中心作为初始原型向量。
    2.  **特征提取**：对每个切片，使用主干网络（如ResNet）提取特征图，同时用分割模型生成结构先验特征图。
    3.  **原型学习**：通过对比学习或原型损失，使每个切片的特征与最匹配的原型距离最小化，同时与其他原型距离最大化。分割先验特征通过门控机制或特征拼接方式影响原型分配。
    4.  **跨切片聚合**：对目标切片及其相邻切片提取的特征进行聚合（如使用Transformer或简单平均），得到2.5D切片级特征。
    5.  **风险预测**：基于2.5D特征与所有原型的相似度向量，通过全连接层或线性分类器输出该切片的风险分数（例如，分类为“高危”、“中危”、“低危”）。

### 3. 实验设计
*   **数据集**：
    *   前列腺癌数据集（3D开放源成像）
    *   食管癌数据集（3D开放源成像）
*   **任务**：2D切片级风险预测，包含二分类（高风险 vs. 低风险）和多分类（如多个风险等级）。
*   **Benchmark**：对比了多种多实例学习（MIL）基线方法：
    *   基于注意力的MIL（Attention-based MIL）
    *   基于原型的MIL（Prototype-based MIL）
*   **评估指标**：AUC（曲线下面积）、准确率、F1分数等（具体指标在图中展示，文本未列出详细数值但声称“持续优于”基线）。
*   **消融实验**：文中提及进行了消融实验，验证了聚类预训练、分割先验引导、跨切片聚合三个模块的有效性（通过去除各模块的对比实验）。

### 4. 资源与算力
论文未明确说明所使用的GPU型号、数量及训练时长。仅提到训练基于深度学习框架，但未提供具体硬件配置和训练时间。需要指出这一信息缺失。

### 5. 实验数量与充分性
*   **实验数量**：在两个不同器官（前列腺和食管）的数据集上进行了评估，覆盖二分类和多分类任务，并包含消融实验。整体实验组数中等。
*   **充分性与公平性**：实验设计较为充分，因为：
    *   对比了多种当时主流基线（注意力MIL、原型MIL）。
    *   进行了消融实验，验证了各组件贡献。
    *   在两种不同癌种和数据源上验证，表明具有一定泛化能力。
    *   **不足**：论文未提供详细的数据集划分（如训练/验证/测试比例）、重复实验次数、显著性检验（如p值）等，可能无法完全排除偶然性。此外，基线方法是否在最优超参数下运行未明确说明。

### 6. 主要结论与发现
*   SCOPE框架在前列腺和食管癌数据集上，无论是二分类还是多分类任务，其性能（如AUC）均**一致优于**基于注意力和基于原型的MIL基线。
*   通过聚类预初始化和分割先验引导，SCOPE能够学习到病理学家可解释的形态学原型（如健康腺体、病变区域、坏死等模式），提升了模型的可解释性。
*   利用跨切片（2.5D）聚合利用相邻切片上下文信息，进一步提升了切片级风险预测的准确性。
*   最终实现了深度分辨的风险剖面（depth-resolved risk profiling），即能输出3D体积中每一层切片的精确风险，供分诊使用。

### 7. 优点
1.  **可解释性强**：通过原型学习，将模型决策与具体的组织形态模式关联，病理学家可以直观理解模型为何将某切片标记为高风险。
2.  **数据高效**：利用无监督聚类预训练，减少了对昂贵病理标注的需求，适合标记数据稀缺的3D病理领域。
3.  **性能优越**：在多个数据集和任务上明显优于强基线，证明方法有效。
4.  **结构先验整合**：引入分割先验，使模型关注组织学结构，而不是像素级纹理，符合病理学专家认知。
5.  **2.5D上下文利用**：跨切片聚合抓住了3D数据的本质特征，优于单纯基于2D切片的方法。

### 8. 不足与局限
1.  **计算资源未披露**：未提供训练所需GPU型号、数量和时间，使得他人难以复现或评估方法可行性。
2.  **实验细节不够透明**：缺乏交叉验证、统计显著性检验、超参数搜索细节，可能影响结论的稳健性。
3.  **数据规模**：仅使用两个数据集（前列腺、食管），且数据集规模未明确。结果可能无法直接推广到其他器官或更复杂的3D病理数据。
4.  **分诊有效性验证不足**：论文展示了切片级风险预测的准确性，但未进一步验证“基于此分诊结果，病理学家实际审查效率提升多少”或“漏诊率如何”。这需要人机协作的临床验证。
5.  **原型数量和语义**：原型数量K的选择是否关键，原型是否真正对应到临床有意义的形态学类别，仅通过图像验证，缺乏金标准病理专家标注验证。
6.  **对分割模型依赖**：分割先验的性能依赖于公开分割模型的质量，若目标组织形态与训练数据差异大，引导效果可能下降。

（完）
