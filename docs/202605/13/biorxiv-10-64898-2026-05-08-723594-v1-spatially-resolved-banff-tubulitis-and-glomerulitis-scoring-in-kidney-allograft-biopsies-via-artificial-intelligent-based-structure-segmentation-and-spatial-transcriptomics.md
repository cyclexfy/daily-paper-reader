---
title: Spatially Resolved Banff Tubulitis and Glomerulitis Scoring in Kidney Allograft Biopsies via Artificial Intelligent-Based Structure Segmentation and Spatial Transcriptomics
title_zh: 基于人工智能结构分割与空间转录组学的肾移植活检样本空间分辨Banff小管炎和肾小球炎评分
authors: "Kates, H., Lee, C., Paul, A. S., Ansari, I., Tatke, A., Lee, T., Nguyen, M.-T., Eadon, M. T., Sarder, P., Chen Wongworawat, Y."
date: 2026-05-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.08.723594v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 全切片图像中的结构分割与空间转录组学
tldr: 本研究针对肾移植活检中Banff评分存在的人为误差及大块转录组缺乏空间分辨率的问题，提出了一种结合AI结构分割与空间转录组学的新方法。通过FUSION平台对肾小管和肾小球进行自动分割，并结合免疫细胞比例生成空间t评分和g评分。结果显示该方法在严重排斥反应中与病理学家评分高度一致，为提高诊断精准度、减少观察者间差异并推动临床应用奠定了基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决肾移植活检中Banff评分的主观变异性以及传统转录组分析缺乏空间定位信息的问题。
method: 利用FUSION平台结合AI图像分割技术与10x Genomics空间转录组学，通过计算特定结构内的免疫细胞比例来生成空间Banff评分。
result: 空间t评分在急性TCMR病例中与病理学家评分完全一致，而g评分在部分AMR病例中表现出一致性，差异主要源于轻微排斥反应中的低免疫信号。
conclusion: 该研究证明了利用AI分割与空间转录组学生成Banff评分的可行性，有助于提升肾移植排斥反应诊断的客观性和精确性。
---

## 摘要
背景：小管炎是T细胞介导的排斥反应（TCMR）的定义性组织学特征，而肾小球炎通常是抗体介导的排斥反应（AMR）的特征。使用Banff标准对小管炎和肾小球炎进行组织学定量存在观察者间的差异。批量转录组测序（如MMDx）引入了小管炎与TCMR以及肾小球炎与AMR的分子相关性，但缺乏空间分辨率。方法：我们将基于Web的平台FUSION（全切片图像中的功能单元状态识别）应用于8例肾移植活检样本队列（每种情况n=2），包括急性TCMR、活动性AMR、慢性活动性AMR和无排斥反应（对照）。该机器学习（ML）平台实现了空间转录组学（10x Genomics Visium v2）与高分辨率全切片组织学的集成可视化和分析。结果：利用AI分割的小管和肾小球区域内的转录组衍生免疫细胞比例来生成空间Banff t评分和g评分。衍生的t评分在两例急性TCMR病例中均与病理学家的评分完全一致；g评分在4例AMR病例中的2例显示出一致性，不一致的病例特征为分类边界附近的绝对免疫信号较低。结论：我们证明了利用基于AI的FTU分割结合空间转录组衍生的免疫细胞比例来生成符合Banff标准的空间信息t评分和g评分的可行性，在严重排斥反应中完全一致，在轻度排斥反应中部分一致。这种方法为经过验证的、空间转录组增强的t评分和g评分奠定了基础，从而提高了诊断精度，减少了肾脏病理学家之间的观察者差异，并支持潜在的临床应用。

## Abstract
Background: Tubulitis is a defining histologic feature of T cell-mediated rejection (TCMR), while glomerulitis is often characteristic of antibody mediated rejection (AMR). Histologic quantification of tubulitis and glomerulitis using Banff criteria is subject to interobserver variability. Bulk transcriptomic assays (e.g., MMDx) have introduced molecular correlations of tubulitis with TCMR and glomerulitis with AMR, but lack spatial resolution. Methods: We applied a web-based platform, FUSION (Functional Unit State Identification in Whole Slide Images), to a cohort of 8 cases (n=2 per condition) with kidney allograft biopsy samples acute TCMR, active AMR, chronic active AMR, and no rejection (control). The machine-learning (ML) platform enabled integrated visualization and analysis of spatial transcriptomics (10x Genomics Visium v2) together with high resolution whole slide histology. Results: Transcriptomics-derived immune cell proportions within AI-segmented tubular and glomerular regions were used to generate spatial Banff t- and g-scores. Derived t-scores showed full concordance with pathologist scores in both acute TCMR cases; g-scores showed concordance in 2 of 4 AMR cases, with discordant cases characterized by low absolute immune signal near the classification boundary. Conclusions: We demonstrate the feasibility of using AI-based FTU segmentation integrated with spatial transcriptomics-derived immune cell proportions to generate spatially informed t- and g-scores aligned with Banff criteria, with full concordance in severe rejection and partial concordance in mild rejection. This approach lays the foundation for validated, spatial transcriptomics-augmented t-scores and g-scores that enhance diagnostic precision, reduces inter observer variability among renal pathologists, and support potential clinical adoption.

---

## 论文详细总结（自动生成）

这是一份关于该论文的结构化深入总结：

### 0. 论文源代码链接
*   **GitHub 链接**：[https://github.com/SarderLab/LLU-kidney-spatial-tx](https://github.com/SarderLab/LLU-kidney-spatial-tx)

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：肾移植排斥反应的诊断金标准是基于 Banff 标准的组织病理学评估，但其中的“小管炎（Tubulitis）”和“肾小球炎（Glomerulitis）”评分存在显著的人为观察者差异。
*   **研究动机**：
    *   **传统病理局限性**：人工计数免疫细胞耗时耗力，且在区分上皮细胞核与炎性细胞核时存在视觉挑战。
    *   **分子诊断局限性**：批量转录组学（如 MMDx）虽能提供分子证据，但丢失了关键的空间定位信息。
    *   **AI 图像分析局限性**：单纯基于图像的 AI 模型在复杂细胞定位（如区分管腔内与间质细胞）上仍有难度。
*   **整体含义**：本研究旨在通过结合 **AI 结构分割**与**空间转录组学（Spatial Transcriptomics）**，开发一种客观、可量化且具有空间分辨能力的 Banff 评分新方法。

### 2. 论文提出的方法论
*   **核心思想**：利用 AI 自动识别肾脏的功能组织单位（FTU，如小管、肾小球），并结合空间转录组数据计算这些特定结构内的免疫细胞比例，从而映射回 Banff 评分标准。
*   **关键技术细节**：
    1.  **数据采集**：使用 10x Genomics Visium v2 平台对 FFPE 肾移植活检切片进行空间转录组测序。
    2.  **AI 分割（FUSION 平台）**：使用 FUSION 平台及其内置的 DeepCell 管道，在全切片图像（WSI）上自动分割小管、肾小球（硬化与非硬化）、血管和间质。
    3.  **细胞类型反卷积**：利用 Seurat v5 的 `TransferData` 功能，参考 KPMP 单核转录组图谱（>20万个核），预测每个 Visium 位点（Spot）的细胞比例，并将多种免疫细胞合并为单一的“免疫类别（IMM）”。
    4.  **空间评分生成**：
        *   **t 评分（小管炎）**：计算每个小管内的 IMM 比例，取“最严重小管”的 IMM 比例作为指标，设定阈值（如 >0.70 为 t3）。
        *   **g 评分（肾小球炎）**：计算受累（IMM 比例 >0.10）肾小球占总肾小球的百分比，按 Banff 比例标准转化为 g0-g3。

### 3. 实验设计
*   **数据集**：包含 8 例肾移植活检样本，涵盖四种诊断类别：非排斥对照（n=2）、活动性 AMR（n=2）、急性 TCMR（n=2）、慢性活动性 AMR（n=2）。
*   **Benchmark（基准）**：由资深肾脏病理学家根据 2018 年 Banff 标准给出的原始病理评分。
*   **对比方法**：主要对比了 AI 衍生的空间评分与病理学家人工评分的一致性（Concordance）。

### 4. 资源与算力
*   **算力说明**：文中未明确提及具体的 GPU 型号、数量或训练时长。
*   **软件工具**：使用了 FUSION Web 平台、R 语言（Seurat v5.1.0, jsonlite v1.8.9）以及 10x Genomics 的 Space Ranger。

### 5. 实验数量与充分性
*   **实验规模**：作为一项**概念验证（Proof-of-concept）**研究，样本量较小（N=8）。
*   **充分性评价**：
    *   **覆盖度**：涵盖了主要的排斥类型（TCMR 和 AMR），实验设计逻辑清晰。
    *   **局限性**：由于每种诊断仅 2 例，无法进行大规模的灵敏度和特异性统计分析。实验主要侧重于方法论的可行性展示，而非临床效能的全面验证。

### 6. 论文的主要结论与发现
*   **t 评分一致性极高**：在急性 TCMR 病例中，AI 衍生的 t 评分与病理学家评分达到 **100% 一致**。严重排斥反应的小管 IMM 比例显著高于对照组。
*   **g 评分部分一致**：在 AMR 病例中，g 评分表现出部分一致性。在严重排斥病例中表现良好，但在轻度排斥（免疫信号弱）的病例中出现了不一致。
*   **技术可行性**：证明了将空间转录组数据与解剖结构分割集成，可以实现自动化的、符合临床标准的病理评分。

### 7. 优点
*   **客观性**：消除了人工评分的主观偏差，提供了基于基因表达的定量依据。
*   **空间精准**：相比批量转录组，该方法能精确区分免疫浸润是发生在小管内还是间质中。
*   **集成化**：FUSION 平台实现了组织形态学与多组学数据的无缝可视化集成。

### 8. 不足与局限
*   **分辨率限制**：Visium v2 的 Spot 直径为 55μm，大于单个细胞且常跨越结构边界，导致在轻度浸润时信号被稀释（产生边缘效应）。
*   **样本量小**：N=8 的规模不足以支持临床诊断效能的定论。
*   **成本与时效**：空间转录组测序成本高昂且流程复杂，短期内难以在常规临床实践中普及。
*   **解剖定位精度**：目前无法完全区分上皮内信号与管周信号，未来可能需要亚细胞分辨率的技术（如 Xenium）来进一步优化。

（完）
