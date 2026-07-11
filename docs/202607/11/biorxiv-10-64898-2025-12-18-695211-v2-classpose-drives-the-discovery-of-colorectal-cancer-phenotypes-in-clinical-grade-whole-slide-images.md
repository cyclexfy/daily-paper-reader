---
title: Classpose drives the discovery of colorectal cancer phenotypes in clinical grade whole slide images
title_zh: Classpose驱动临床级全切片图像中结直肠癌表型的发现
authors: "Mandal, S., de Almeida, J. G., Bräutigam, K., Papanikolaou, N., Graham, T. A."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.18.695211v2.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 结直肠癌，全切片图像，细胞表型分析，深度学习
tldr: 针对组织病理学细胞表型分析中人工注释耗时且主观的问题，提出基于Cellpose-SAM的Classpose框架，通过微调整个网络实现高精度细胞分割与分型。在6个数据集上超越现有方法，并在结直肠癌全切片图像队列中成功提取细胞组织与形态特征，用于预测MMR缺陷、BRAF和KRAS突变等分子条件。该框架易于训练且提供了QuPath扩展，有助于数字病理学的临床表型发现。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1740, \"height\": 1448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1707, \"height\": 1827, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1197, \"height\": 1179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1743, \"height\": 2204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1392, \"height\": 936, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1741, \"height\": 997, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1798, \"height\": 1267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1379, \"height\": 915, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1232, \"height\": 1451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1197, \"height\": 1174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1198, \"height\": 1181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1229, \"height\": 709, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1210, \"height\": 1120, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1204, \"height\": 1119, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 518, \"height\": 1038, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1207, \"height\": 1131, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 999, \"height\": 1546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1437, \"height\": 1556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1788, \"height\": 1062, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1809, \"height\": 1437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1796, \"height\": 2627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1502, \"height\": 2505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1789, \"height\": 1582, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1116, \"height\": 1046, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1046, \"height\": 1488, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 443, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 2094, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 2015, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 2015, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1118, \"height\": 1046, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1118, \"height\": 1047, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1200, \"height\": 894, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1468, \"height\": 932, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2025-12-18-695211-v2/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1748, \"height\": 1011, \"label\": \"Table\"}]"
motivation: 细胞表型分析依赖专家手工标注，耗时且主观，亟需自动化方法。
method: 基于Cellpose-SAM构建Classpose框架，对整个网络进行微调以优化细胞分类。
result: 在6个数据集取得SOTA，并在CRC WSI中通过细胞特征预测多种分子突变状态。
conclusion: Classpose提供易用的细胞分型工具，推动数字病理中的表型发现与临床决策。
---

## 摘要
组织病理学样本中的细胞表型分析对于诊断和研究工作流程至关重要。然而，人类专家注释需要大量时间和专业知识，并且受观察者间变异性的影响。在此，我们提出了Classpose，这是一个基于Cellpose-SAM构建的易于训练的细胞分割和表型分析框架，在6个不同数据集上取得了最先进的性能，优于其他竞争方法。我们证明这需要对整个网络进行微调，突出了实例分割对于下游细胞分类而言是一个较差的目标。我们将其应用于一个大型全切片图像（WSI）结直肠癌（CRC）队列（SurGen），并表明Classpose衍生的细胞组织和形态学特征可用于确定临床相关分子状态（MMR缺陷、BRAF突变、KRAS突变）的新颖空间形态表型，并预测这些相同的分子状态。我们公开了Classpose模型，并提供了一个用户友好的QuPath扩展，供数字病理学社区广泛使用。

## Abstract
Cell phenotyping in histopathology samples is essential for diagnostic and research workflows. However, human expert annotation requires significant time and expertise while being affected by inter-observer variability. Here, we present Classpose, an easily trainable framework for cell segmenting and phenotyping built on top of Cellpose-SAM with state-of-the-art performance across 6 distinct datasets, outperforming competing methods. We show that this requires fine-tuning the entire network, highlighting how instance segmentation is a poor objective for downstream cellular classification. We apply it to a large whole slide image (WSI) colorectal cancer (CRC) cohort (SurGen) and show that Classpose-derived cellular organisation and morphology features can be used to determine novel spatial morphological phenotypes for clinically relevant molecular conditions (MMR deficiency, BRAF mutations, KRAS mutations) and to predict these same molecular conditions. We make Classpose models available and provide a user-friendly QuPath extension for widespread use by the digital pathology community.

---

## 论文详细总结（自动生成）

好的，根据您提供的论文摘要和元数据，以下是对该论文的结构化中文总结。

---

### 0. 论文的源代码链接

未在提供的材料中明确给出。但论文提到了公开了Classpose模型，并提供了QuPath扩展，源代码可能通过相关仓库获取，具体链接需查阅原文。

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：组织病理学样本中细胞表型分析（细胞分割与分型）依赖人工专家标注，耗时、昂贵且存在观察者间差异。亟需自动化、可训练的高精度方法，以推动数字病理学中的表型发现和临床决策。
- **整体含义**：本文提出的Classpose框架能高效、准确地从全切片图像（WSI）中提取细胞组织和形态特征，用于预测结直肠癌中的分子状态（如MMR缺陷、BRAF/KRAS突变），从而为精准肿瘤学提供形态学表型标志物。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：基于Cellpose-SAM（一个基础分割模型），构建一个易于训练的细胞分割与表型分析一体化框架。关键发现是：实例分割作为下游细胞分类目标是较差的，因此需要对整个网络进行微调（而非仅微调分类头）以获得最优性能。
- **关键技术细节**：
  - 在Cellpose-SAM的基础上，将实例分割与细胞类型分类任务联合优化。
  - 微调整个网络（包括编码器和解码器），而不是仅微调分类层，从而让分割特征更好地服务于分类。
  - 提供用户友好的QuPath扩展，方便临床病理学家使用。
- **算法流程**：输入WSI切片 → 使用微调后的网络进行细胞分割 → 同时输出每个细胞的类别（表型） → 提取细胞层面的形态和组织特征 → 用于下游分子状态预测或表型发现。

### 3. 实验设计：数据集、基准、对比方法

- **数据集**：在6个不同数据集上进行了评估，涵盖多种组织类型和染色条件。并在一个大型结直肠癌WSI队列（SurGen队列）上应用。
- **基准（Benchmark）**：在6个数据集上实现了最先进的性能（SOTA）。
- **对比方法**：与其他竞争性细胞分割和表型分析方法进行了比较（具体方法名称在摘要中未列出，但声称优于它们）。
- **下游任务**：在SurGen CRC队列中，使用Classpose提取的细胞组织和形态学特征，预测MMR缺陷、BRAF突变、KRAS突变等分子状态。

### 4. 资源与算力

论文摘要和元数据中未明确说明使用的GPU型号、数量或训练时长。只提到“易于训练”，但具体算力需求未知。

### 5. 实验数量与充分性

- **实验数量**：论文在6个不同数据集上进行性能比较，并在一个大型队列中进行了分子状态预测验证，还做了消融实验（比较全网络微调 vs. 仅微调分类头，表明全微调的必要性）。实验数量较为充分。
- **充分性与公平性**：跨多个数据集验证增强了泛化性；消融实验揭示了关键设计原则；下游任务使用了真实临床队列，具有一定客观性。但对比方法和具体指标细节（如Dice、F1等）未在摘要中展示，需要原文佐证。

### 6. 论文的主要结论与发现

- **主要结论**：Classpose是一种在6个数据集上均达到SOTA的细胞分割与表型分析框架，且容易训练。
- **关键发现**：全网络微调对于细胞分类至关重要，实例分割目标本身不足以作为下游分类的预训练任务。
- **应用价值**：在结直肠癌WSI队列中，Classpose能够提取出与MMR缺陷、BRAF、KRAS突变相关的空间形态表型，并能有效预测这些分子状态，具有潜在的临床转化价值。

### 7. 优点：方法或实验设计上的亮点

- **方法亮点**：
  - 基于成熟分割模型Cellpose-SAM，易于扩展和训练。
  - 揭示了全网络微调的重要性，为类似任务提供了设计指导。
  - 提供了QuPath扩展，降低了使用门槛，有利于社区推广。
- **实验亮点**：
  - 在6个不同数据集上验证，覆盖了异质性数据，证明了鲁棒性。
  - 直接关联下游临床任务（分子状态预测），展示了实际价值。
  - 包含消融实验，支撑了方法设计的合理性。

### 8. 不足与局限

- **不足与局限**：
  - 实验细节（如具体性能数字、对比方法名称、消融指标等）在摘要中未提供，无法全面评估方法优劣。
  - 算力资源未报告，可能影响可重复性。
  - 仅针对结直肠癌进行了分子表型关联，其他癌种或组织的适用性未验证。
  - 未提及模型在不同染色、扫描仪条件下的泛化能力，以及多中心验证情况。
  - 预测分子状态的准确率、AUC等定量指标缺失，临床价值需进一步定量评估。

（完）
