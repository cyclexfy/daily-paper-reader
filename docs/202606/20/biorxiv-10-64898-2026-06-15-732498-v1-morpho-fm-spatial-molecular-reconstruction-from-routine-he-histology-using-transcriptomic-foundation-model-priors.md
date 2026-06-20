---
title: "Morpho-FM: spatial molecular reconstruction from routine H&E histology using transcriptomic foundation-model priors"
title_zh: "Morpho-FM: 利用转录组基础模型先验从常规H&E组织学重建空间分子图谱"
authors: "Huang, J.-J., Feng, X., Qu, L.-H., Zheng, L.-L."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732498v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: "使用基础模型从H&E全切片图像预测空间基因表达"
tldr: "常规H&E组织学缺乏直接分子读数，空间转录组学成本高且采样稀疏。为此，Morpho-FM提出一种弱监督框架，利用预训练单细胞转录组基础模型先验，从H&E全切片图像预测空间基因表达。在前列腺癌和肾癌基准上，平均Pearson相关系数达0.286-0.298，优于五种对比方法；在乳腺癌数据集中成功恢复ERBB2富集区域和边界分子梯度。该工作表明转录组基础模型先验能有效约束形态条件分子解码，有望将空间转录组洞察扩展至常规病理切片。"
source: biorxiv
selection_source: fresh_fetch
motivation: "常规H&E组织学缺乏直接分子读数，而空间转录组学成本高且采样稀疏，需要高效从H&E预测基因表达的方法。"
method: "提出Morpho-FM弱监督框架，利用预训练转录组基础模型先验，通过轻量形态-转录组适配器从H&E图像特征解码空间基因表达。"
result: 在前列腺癌和肾癌基准上平均Pearson相关系数0.286-0.298，优于五种方法；成功恢复ERBB2富集区域和分子梯度。
conclusion: 转录组基础模型先验有效约束形态条件分子解码，可扩展空间转录组洞察至常规病理切片。
---

## 摘要
常规苏木精-伊红（H&E）组织学以临床规模捕捉组织结构，但缺乏对组织肿瘤上皮、间质、血管和免疫区室转录程序的直接分子解读。空间转录组学提供了这一背景，但其成本、工作流程复杂性和稀疏采样限制了常规使用。大多数现有的组织学-表达模型是在小型配对队列上从头训练的，因此在从稀疏测量外推至密集的全组织分子图谱时约束力较弱。本文提出Morpho-FM，一种弱监督框架，通过将预训练的单细胞转录组基础模型先验条件化于局部组织学邻域，从常规H&E全切片图像预测空间基因表达。轻量级的形态-转录组适配器将缓存的整切片组织学特征映射到转录组解码器，从而能够预测测量位置、密集全切片重建以及重新聚合到原始测量支持。在统一的 prostate cancer 基准上，Morpho-FM在五种代表性方法中取得了最强的整体性能，在旋转单切片评估中达到每个基因平均Pearson相关系数0.286，在多切片留出验证中达到0.298。该框架在肾癌切片上复现了这一优势，在56个定向单切片评估中达到平均相关系数0.210，并在外部转移至透明细胞肾细胞癌切片后仍保留了可测量的预测信号。受控消融分析表明，预训练转录组初始化是性能提升的可重复来源，其贡献超过了组织学特征骨干变化带来的增益。除了预测准确性基准外，Morpho-FM在Xenium和HER2ST乳腺癌数据集中恢复了富含ERBB2的肿瘤区室、边界相关的分子梯度以及与注释对齐的组织域。这些结果共同支持转录组基础模型先验作为形态条件分子解码的有效约束，并展示了Morpho-FM将空间转录组学见解扩展到常规病理切片的潜力。

## Abstract
Routine haematoxylin and eosin (H&E) histology captures tissue architecture at clinical scale, but lacks a direct molecular readout of the transcriptional programmes that organise tumour epithelium, stroma, vasculature and immune compartments. Spatial transcriptomics provides this context, yet cost, workflow complexity and sparse sampling limit routine use. Most existing histology-to-expression models are trained de novo on small paired cohorts and therefore remain weakly constrained when extrapolating from sparse measurements to dense, tissue-wide molecular maps. Here we introduce Morpho-FM, a weakly supervised framework that predicts spatial gene expression from routine H&E whole-slide images by conditioning a pretrained single-cell transcriptomic foundation-model prior on local histological neighbourhoods. A lightweight morphology-to-transcriptome adapter maps cached whole-slide histology features into a transcriptomic decoder, enabling prediction at measured locations, dense full-section reconstruction, and re-aggregation to the original measurement support. Across harmonized prostate cancer benchmarks, Morpho-FM achieved the strongest overall performance among five representative methods, reaching mean per-gene Pearson correlations of 0.286 in rotating single-slide evaluation and 0.298 in multi-slide held-out validation. The framework reproduced this advantage across kidney cancer sections, achieved a mean correlation of 0.210 across 56 directed single-slide evaluations and retained measurable predictive signal after external transfer to clear-cell renal cell carcinoma sections. Controlled ablation analyses identified pretrained transcriptomic initialization as a reproducible source of performance gain exceeding that attributable to changes in the histology feature backbone. Beyond predictive accuracy benchmarks, Morpho-FM recovered ERBB2-enriched tumour compartments, boundary-associated molecular gradients, and annotation-aligned tissue domains across Xenium and HER2ST breast cancer datasets. Together, these results support transcriptomic foundation-model priors as an effective constraint for morphology-conditioned molecular decoding and demonstrate the potential of Morpho-FM to extend spatial transcriptomic insight across routine pathology sections.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 0. 论文的源代码链接
无。文中未提供源代码链接。

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：常规 H&E 组织学染色虽能捕捉组织结构，但缺乏直接的分子读出来解读肿瘤上皮、间质、血管和免疫区室的转录程序。空间转录组学可提供分子背景，但成本高、工作流程复杂且采样稀疏，难以常规使用。现有从组织学预测基因表达的方法大多在小规模配对队列上从头训练，从稀疏测量外推到密集全组织分子图谱时约束力弱。
- **研究动机**：开发一种能利用预训练单细胞转录组基础模型先验，从常规 H&E 全切片图像高效、准确地预测空间基因表达的方法，将空间转录组学洞察扩展至常规病理切片。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：提出 **Morpho-FM**，一种弱监督框架，通过将预训练的单细胞转录组基础模型（foundation model）先验条件化于局部组织学邻域，从 H&E 全切片图像预测空间基因表达。
- **关键技术细节**：
  - 使用轻量级 **形态-转录组适配器**（morphology-to-transcriptome adapter），将缓存的整切片组织学特征（从预训练的病理基础模型提取）映射到转录组解码器。
  - 转录组解码器初始化自预训练的单细胞转录组基础模型，提供先验约束。
  - 框架支持三种预测模式：在测量位置预测、密集全切片重建、重新聚合到原始测量支持（即按 spot 或 cell 聚合）。
  - 训练过程为弱监督：仅使用 H&E 图像和对应的稀疏空间转录组测量（如 spot-level 表达），无需 dense 标注。

## 3. 实验设计：数据集、benchmark、对比方法
- **数据集**：
  - 前列腺癌（prostate cancer）基准：统一的数据集，用于旋转单切片评估和多切片留出验证。
  - 肾癌切片（kidney cancer sections）：包括 56 个定向单切片评估，以及外部转移至透明细胞肾细胞癌（ccRCC）切片。
  - 乳腺癌数据集：Xenium 和 HER2ST 数据集（用于恢复 ERBB2 富集区域、边界分子梯度等生物学验证）。
- **Benchmark**：在统一的前列腺癌基准上，与五种代表性方法对比（具体方法名称未列出，但提及五种对比方法）。
- **对比方法**：未逐一列出名称，但文中指出 Morpho-FM 在五种方法中取得最强整体性能。

## 4. 资源与算力
- **未明确说明**。文中未提及使用的 GPU 型号、数量、训练时长等具体硬件资源。仅提到使用了预训练基础模型（可能依赖现有基础模型参数）。

## 5. 实验数量与充分性
- **实验数量**：
  - 前列腺癌：旋转单切片评估（每个切片作为测试，其余训练，循环） + 多切片留出验证（留出若干完整切片）。
  - 肾癌：56 个定向单切片评估 + 外部跨癌种转移验证。
  - 乳腺癌：Xenium 和 HER2ST 数据集上的生物学恢复能力验证（定性+定量）。
  - 消融分析：控制组织学特征骨干变化、预训练转录组初始化等。
- **充分性评价**：
  - 较充分：覆盖了多个癌种（前列腺、肾、乳腺）、多种评估设置（旋转留出、跨切片、跨数据集）、消融分析、生物学意义验证（ERBB2、分子梯度）。
  - 客观性：使用统一基准、对比多种方法、外部转移验证（ccRCC），结果支持主要结论。
  - 不足：未提及在不同染色条件、不同扫描仪下的鲁棒性；对比方法未详细列出，可能影响可复现性。

## 6. 论文的主要结论与发现
- **主要结论**：转录组基础模型先验能有效约束形态条件分子解码，提高从 H&E 预测空间基因表达的准确性。
- **具体发现**：
  - 在前列腺癌基准上，Morpho-FM 平均每基因 Pearson 相关系数达 0.286（旋转单切片）和 0.298（多切片留出），优于五种对比方法。
  - 在肾癌基准上，平均相关系数 0.210，外部转移至 ccRCC 仍保留可测量预测信号。
  - 消融分析证实预训练转录组初始化是性能提升的可重复来源，贡献超过组织学特征骨干变化。
  - 在乳腺癌数据集中成功恢复富含 ERBB2 的肿瘤区室、边界分子梯度以及与注释对齐的组织域。

## 7. 优点
- **方法创新**：首次将单细胞转录组基础模型先验引入 H&E 到空间转录组的预测中，利用大规模先验知识克服小样本外推问题。
- **轻量高效**：适配器轻量级，利用缓存特征，避免重复大模型推理。
- **弱监督框架**：无需密集标注，仅需稀疏 spot 表达即可训练，实用性强。
- **验证充分**：跨多个癌种、多种评估设置，并进行了生物学意义验证（ERBB2、分子梯度），不仅是数值指标。
- **消融分析深入**：分离了预训练初始化和特征骨干的贡献，归因清晰。

## 8. 不足与局限
- **伦理/偏差风险**：未讨论预测结果可能引入的种族、性别、医院 bias；预训练基础模型本身可能带有偏差。
- **实验覆盖**：
  - 仅测试了前列腺癌、肾癌、乳腺癌三种癌种，泛化到其他癌种（如肺癌、结直肠癌）未知。
  - 未在非肿瘤组织（如炎症、正常组织）上评估。
  - 对比方法仅列出5种，未给出具体名称和配置，可复现性受影响。
- **应用限制**：
  - 依赖高质量 H&E 全切片图像和预训练基础模型（可能受限于版权或计算资源）。
  - 预测的基因表达为相对水平，可能无法达到真实空间转录组的高分辨率（单细胞级）。
  - 未提供源代码，阻碍社区复现和进一步改进。
  - 算力需求未披露，可能对资源有限实验室不友好。

（完）
