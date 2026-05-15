---
title: "A multi-omic, spatial, and whole-slide image dataset of lung neuroendocrine tumours from the lungNENomics cohort"
title_zh: 来自 lungNENomics 队列的肺神经内分泌肿瘤多组学、空间和全切片图像数据集
authors: "Kalson, L., Sexton-Oates, A., Mathian, E., Voegele, C., Di Genova, A., Li, Z., Kim, J., Marsh, L. M., Brcic, L., Fernandez-Cuesta, L., Foll, M., Alcala, N."
date: 2026-05-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.12.724489v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 肺神经内分泌肿瘤的全切片图像数据集
tldr: 该研究发布了迄今为止最大的肺神经内分泌肿瘤（lung NETs）多组学数据集，涵盖201名患者的294个肿瘤样本。数据集整合了全基因组测序、RNA测序、甲基化阵列、空间蛋白组学及转录组学，并包含全切片病理图像。该资源旨在通过多尺度数据集成，深入探讨肺NETs的分子分型、内异质性及形态学特征，为未来临床研究提供重要基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 肺神经内分泌肿瘤较为罕见，且现有研究缺乏全基因组和影像学数据，导致其基因组和形态学特征尚未得到充分探索。
method: 研究团队收集了201名患者的样本，生成了包含WGS、RNA-seq、甲基化、空间组学及全切片病理图像的大规模多模态数据集。
result: 成功构建了包含多区域测序和空间信息的综合数据库，支持利用深度学习算法识别特定分子亚型的形态学特征。
conclusion: 该数据集为肺NETs的分子表征和多尺度整合研究提供了宝贵资源，有助于推动该领域的精准医疗发展。
---

## 摘要
肺神经内分泌肿瘤（lung NETs）是罕见的肿瘤，约占肺癌的 2%。最近的研究基于转录组和甲基化组数据确定了不同的分子亚群，但由于全基因组和影像数据有限，基因组和形态学特征仍未得到充分探索。我们生成了迄今为止最大的肺 NETs 多组学数据集（201 名参与者，共计 n = 294 个肿瘤），包括 RNA 测序、EPIC 850K 甲基化阵列和全基因组测序。该多组学数据集还包括 41 名参与者的多区域全基因组测序，从而能够量化肿瘤内异质性。此外，我们还生成了 64 名参与者的空间蛋白质组学、4 名参与者的空间转录组学以及 212 例病例的全切片组织病理学图像。该数据集能够对肺 NET 分子亚群进行全面表征，并利用深度学习算法识别亚群特异性的形态学特征。所有质量控制分析、处理后的数据和脚本均已提供，以确保可重复性。该数据集可作为进一步分析肺 NETs 分子和形态学特征以及未来多尺度整合研究的基础。

## Abstract
Lung neuroendocrine tumours (lung NETs) are rare neoplasms comprising approximately 2% of lung cancers. Recent studies have identified distinct molecular groups based on transcriptome and methylome data, but genomic and morphological features remain underexplored due to limited whole-genome and imaging data. We have generated the largest multi-omic dataset of lung NETs to date (201 participants, for a total of n = 294 tumours), including RNA sequencing, EPIC 850K methylation arrays, and whole-genome sequencing. This multi-omic dataset also include multi-regional whole-genome sequencing for 41 participants, allowing for the quantification of intra-tumoural heterogeneity. We additionally generated spatial proteomics (64 participants), spatial transcriptomics (4 participants) and whole-slide histopathology images for 212 cases. This dataset enables a comprehensive characterization of lung NET molecular groups and the identification of group-specific morphological features using deep learning algorithms. All quality control analyses, processed data, and scripts are provided to ensure reproducibility. This dataset is available as a basis for further molecular and morphological analysis of lung NETs, and for future research on multi-scale integration.

---

## 论文详细总结（自动生成）

这是一份关于论文《A multi-omic, spatial, and whole-slide image dataset of lung neuroendocrine tumours from the lungNENomics cohort》的结构化分析总结：

### 0. 论文的源代码链接
*   **分析脚本与流程：** [https://github.com/IARCbioinfo/MS_lungNENomics](https://github.com/IARCbioinfo/MS_lungNENomics)
*   **生物信息学工作流：** [https://github.com/IARCbioinfo/](https://github.com/IARCbioinfo/)

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题：** 肺神经内分泌肿瘤（lung NETs）是一种罕见且研究不足的肺癌类型。现有的临床分类（典型和非典型类癌）存在观察者间差异大、预后预测价值有限等问题。
*   **研究动机：** 尽管已有研究通过转录组和甲基化组确定了分子亚群，但由于缺乏大规模的全基因组测序（WGS）和高分辨率病理影像数据，该疾病的基因组特征、肿瘤内异质性（ITH）以及分子分型与形态学特征之间的关联仍不清楚。
*   **整体含义：** 本文发布了迄今为止最大的肺 NETs 多模态数据集（lungNENomics 队列），旨在为该领域的分子表征、形态学识别及多尺度数据整合提供标准参考。

### 2. 论文提出的方法论
该论文主要是一篇**数据描述符（Data Descriptor）**，其核心贡献在于构建了多维度的实验与分析框架：
*   **多组学集成：** 整合了 WGS（72人）、RNA-seq（178人）和 DNA 甲基化阵列（191人）。
*   **空间组学技术：** 利用 GeoMx® 数字空间分析（DSP）进行空间蛋白质组学（64人，513个感兴趣区域）和 10x Genomics Visium 进行空间转录组学（4人）。
*   **病理影像：** 对 212 例病例进行了 40x 放大倍率的全切片图像（WSI）扫描。
*   **生物信息学流程：** 使用 Nextflow 编写的可重复工作流，涵盖了从原始读段比对（BWA/STAR）、变异检测（Mutect2/Strelka2）、拷贝数分析（PURPLE/GISTIC2）到甲基化处理（minfi）的全过程。
*   **技术验证：** 引入了 NGSCheckMate 进行样本匹配验证，并利用下采样（Downsampling）模拟实验验证了低深度测序样本在分子分型中的鲁棒性。

### 3. 实验设计
*   **数据集构成：** 包含 201 名参与者的 294 个肿瘤样本，涵盖了 1 级（典型）和 2 级（非典型）类癌，以及部分大细胞神经内分泌癌（LCNEC）和小细胞肺癌（SCLC）作为对比。
*   **Benchmark/对比：** 
    *   **内部验证：** 通过 41 名参与者的多区域采样（ITH 研究）来评估肿瘤内部的遗传差异。
    *   **性别验证：** 交叉比对临床记录与 WGS、RNA-seq、甲基化推断的性别，确保数据一致性。
    *   **质量控制：** 使用 FastQC、MultiQC、RSeQC 等工具对每一类数据进行严格的 QC 过滤。

### 4. 资源与算力
*   **算力支持：** 文中提到使用了法国国家高性能计算资源 **GENCI-IDRIS**（项目号 2022-AD011012172R1 等）。
*   **具体配置：** 未详细列出具体的 GPU 型号、数量或确切的训练时长，但指出所有软件依赖均通过 Docker 和 Singularity 容器化，确保了在高性能计算环境下的可移植性。

### 5. 实验数量与充分性
*   **实验规模：** 样本量（n=294 肿瘤）对于罕见病研究而言非常庞大。
*   **充分性：** 
    *   **多维度验证：** 论文不仅提供了原始数据，还提供了详细的质量控制报告（如 Phred 分数、重复率、比对率等）。
    *   **鲁棒性测试：** 针对一个低深度 RNA-seq 样本（LNEN079），进行了 100 次下采样模拟实验，证明了其分子分型结果的稳定性。
*   **客观性：** 采用了中心化病理审查（6 名专家共同审核），减少了单中心研究的偏倚。

### 6. 论文的主要结论与发现
*   **分子分型：** 确认肺 NETs 可分为四个分子组（Ca A1, Ca A2, Ca B, 和 supra-carcinoid enriched），每组具有独特的分子谱和形态特征。
*   **数据价值：** 证明了集成 WGS、空间组学和 WSI 数据对于理解罕见肿瘤异质性的必要性。
*   **技术可靠性：** 验证了即使在测序深度较低或样本类型不同（FFPE vs 冰冻）的情况下，通过标准化的生物信息学流程仍能获得高质量、一致的分子结论。

### 7. 优点
*   **规模空前：** 填补了肺 NETs 缺乏大规模全基因组和空间组学数据的空白。
*   **多模态整合：** 罕见地将分子组学与高分辨率全切片影像（WSI）结合，支持未来的人工智能/深度学习病理研究。
*   **高度可重复性：** 提供了完整的 Nextflow 流程、容器镜像和 Zenodo 上的处理后数据，符合开放科学标准。

### 8. 不足与局限
*   **空间转录组样本量较小：** 仅包含 4 例 Visium 样本，可能不足以捕捉该疾病全部的组织学多样性。
*   **临床随访数据：** 虽然提到了预后，但论文重点在于数据描述，缺乏长期的临床生存关联深度分析（这可能在配套的另一篇研究论文中体现）。
*   **数据访问限制：** 由于涉及人类基因组敏感信息，原始数据（CRAM/FASTQ）需要通过受控访问申请（EGA），这在一定程度上增加了获取门槛。

（完）
