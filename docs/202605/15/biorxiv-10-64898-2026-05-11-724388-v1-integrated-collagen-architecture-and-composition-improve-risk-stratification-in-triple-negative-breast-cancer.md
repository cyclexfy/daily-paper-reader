---
title: Integrated Collagen Architecture and Composition Improve Risk Stratification in Triple-Negative Breast Cancer
title_zh: 整合胶原架构与成分改善三阴性乳腺癌的风险分层
authors: "Ozbilgic, R., Dinc, B., Vipparthi, K., Seachrist, D., Nicolas, M., Keri, R. A., Liu, X., Yildirim, M., Karaayvaz, M."
date: 2026-05-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724388v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 用于乳腺癌风险分层的多模态计算病理学框架
tldr: COL1比例与患者的复发风险及总生存期显著相关。该方法整合了架构与成分生物标志物，能有效识别高风险亚群，为TNBC的精准风险分层提供了实用的计算病理学手段。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在通过定量分析标准组织标本中的胶原蛋白架构和成分，解决三阴性乳腺癌临床异质性导致的预后预测难题。
method: 利用多模态计算病理框架，结合马松染色与免疫组化技术，对胶原纤维架构进行聚类分析并计算COL3与COL1的比例。
result: COL1比例与更长的总生存期相关，整合两者可进一步优化风险分层。
conclusion: 定量评估肿瘤内胶原蛋白的架构和成分能提供重要的预后信息，是一种具有临床应用潜力的细胞外基质表型分析方法。
---

## 摘要
目的：三阴性乳腺癌（TNBC）表现出显著的临床异质性，尽管临床病理特征相似，部分患者仍会出现早期复发和较差的生存预后。本研究旨在确定源自标准组织病理学标本的瘤内胶原架构和成分的定量测量指标，是否能识别具有复发风险和不良生存结局的患者。实验设计：我们利用整合了马松三色染色（Masson's Trichrome）与 COL1 和 COL3 免疫组化的多模态计算病理学框架，分析了由 79 例 TNBC 肿瘤组成的回顾性队列（组织微阵列）。通过基于纤维的图像分析和无监督聚类对胶原架构进行定量，并使用归一化的 COL3:COL1 比率评估胶原成分。使用 Kaplan-Meier 分析、受限平均生存时间（RMST）和 Cox 比例风险模型评估其与无复发间隔（RFI）和总生存期（OS）的相关性。结果：无监督分析识别出四种不同的胶原架构状态，并根据复发模式将其整合为低风险组和高风险组。高风险胶原架构与显著较差的长期 RFI 相关（log-rank p=0.025；RMST 差异为 10.1 个月）。独立地，较高的 COL3:COL1 比率与 OS 的改善相关（log-rank p=0.042；RMST 差异为 9.4 个月）。架构和成分生物标志物的整合进一步细化了风险分层，识别出一个具有高风险架构且 COL3:COL1 比率较低的亚组，该组表现出最差的生存结局。值得注意的是，基于胶原的分层识别出了仅凭肿瘤分期难以预测的具有不同结局的患者。结论：瘤内胶原架构和成分的定量评估为 TNBC 提供了具有临床意义的预后信息，并实现了复发和生存风险的分层。这些发现支持将细胞外基质表型分析作为一种实用且可扩展的计算病理学方法，用于完善 TNBC 的风险评估。

## Abstract
Purpose: Triple-negative breast cancer (TNBC) exhibits substantial clinical heterogeneity, with some patients experiencing early recurrence and poor survival despite similar clinicopathologic features. We sought to determine whether quantitative measures of intratumoral collagen architecture and composition derived from standard histopathologic specimens can identify patients at risk of recurrence and adverse survival outcomes. Experimental Design: We analyzed a retrospective cohort of 79 TNBC tumors assembled into a tissue microarray using a multimodal computational pathology framework integrating Massons Trichrome staining with COL1 and COL3 immunohistochemistry. Collagen architecture was quantified using fiber-based image analysis and unsupervised clustering, while collagen composition was assessed using a normalized COL3:COL1 ratio. Associations with recurrence-free interval (RFI) and overall survival (OS) were evaluated using Kaplan-Meier analysis, restricted mean survival time (RMST), and Cox proportional hazards modeling. Results: Unsupervised analysis identified four distinct collagen architectural states, which were consolidated into low-risk and high-risk groups based on recurrence patterns. High-risk collagen architecture was associated with significantly worse long-term RFI (log-rank p=0.025; RMST difference 10.1 months). Independently, a higher COL3:COL1 ratio was associated with improved OS (log-rank p=0.042; RMST difference 9.4 months). Integration of architectural and compositional biomarkers further refined risk stratification, identifying a subgroup with high-risk architecture and low COL3:COL1 ratio that exhibited the poorest survival outcomes. Notably, collagen-based stratification identified patients with divergent outcomes not readily predicted from tumor stage alone. Conclusions: Quantitative assessment of intratumoral collagen architecture and composition provides clinically meaningful prognostic information in TNBC and enables stratification of recurrence and survival risk. These findings support extracellular matrix phenotyping as a practical and scalable computational pathology approach for refining risk assessment in TNBC.

---

## 论文详细总结（自动生成）

这篇论文探讨了如何通过定量分析三阴性乳腺癌（TNBC）组织中的胶原蛋白架构和成分来改善患者的风险分层。以下是对该论文的深度结构化总结：

### 0. 论文的源代码链接
*   **GitHub 链接**：[https://github.com/karaayvazlab/TNBCproject.git](https://github.com/karaayvazlab/TNBCproject.git)（包含 QuPath、ImageJ/Fiji 和 R 脚本）。

### 1. 论文的核心问题与整体含义
*   **研究动机**：TNBC 具有高度的临床异质性。即使临床病理特征（如分期、等级）相似，患者的预后也大相径庭。
*   **核心问题**：目前的预后评估主要依赖肿瘤细胞特征，而忽略了细胞外基质（ECM）的结构信息。本研究旨在探索肿瘤内胶原蛋白的**架构（Architecture）**和**成分（Composition）**是否可以作为独立的预后生物标志物，以识别高风险患者。

### 2. 论文提出的方法论
研究构建了一个多模态计算病理学框架，主要步骤如下：
*   **数据获取**：使用 79 例 TNBC 患者的组织微阵列（TMA），进行马松三色染色（显示胶原架构）和 COL1/COL3 免疫组化（显示胶原成分）。
*   **胶原架构定量**：
    *   利用 ImageJ/Fiji 提取胶原通道。
    *   使用 **CT-FIRE** 和 **CurveAlign** 算法提取纤维特征（密度、长度、宽度、排列一致性、平直度）。
    *   通过**无监督层次聚类**将患者分为四种胶原状态（Cluster 1-4）。
*   **胶原成分定量**：
    *   计算归一化的 **COL3:COL1 比率**。
    *   使用最大选择秩统计量（maxstat）确定最佳切点，将患者分为高/低比率组。
*   **风险整合**：将架构聚类结果（分为高/低风险组）与成分比率结合，构建综合风险模型。

### 3. 实验设计
*   **数据集**：来自克利夫兰医学中心（Cleveland Clinic）的 79 例 TNBC 回顾性队列，中位随访时间 93 个月。
*   **评估指标**：无复发间隔（RFI）和总生存期（OS）。
*   **统计方法**：Kaplan-Meier 生存曲线、受限平均生存时间（RMST）差异分析、Cox 比例风险模型。
*   **对比基准**：传统的临床病理变量（肿瘤分期、淋巴结状态、年龄、肿瘤等级等）。

### 4. 资源与算力
*   **硬件**：文中提到使用了 **GPU 加速** 进行细胞核分割（Cellpose 2.0 算法），但未明确具体的 GPU 型号、数量或具体的训练/推理时长。
*   **软件**：主要依赖 QuPath (v6.0)、Fiji/ImageJ、R (v4.5.0) 以及 CT-FIRE/CurveAlign 插件。

### 5. 实验数量与充分性
*   **实验规模**：对 79 例样本进行了全流程分析，包括架构聚类、成分比率计算、单变量/多变量 Cox 回归、以及针对初治（Treatment-naïve）亚组的验证。
*   **充分性评价**：
    *   **优点**：实验设计逻辑严密，涵盖了从图像处理到临床生存分析的完整链条，并进行了多变量校正。
    *   **局限**：样本量（n=79）相对较小，且属于单中心回顾性研究。虽然进行了亚组分析，但统计效能可能受限。

### 6. 论文的主要结论与发现
*   **架构与复发相关**：识别出 4 种胶原架构，其中高风险架构（Cluster 2+3）的 6 年无复发间隔显著较差（RMST 缩短 10.1 个月）。
*   **成分与生存相关**：较高的 COL3:COL1 比率与更好的总生存期（OS）显著相关（RMST 增加 9.4 个月），其预后价值与淋巴结状态相当。
*   **整合模型更优**：整合架构和成分特征能识别出“高风险架构+低 COL3:COL1 比率”的最差预后亚组。
*   **超越传统分期**：胶原特征能识别出早期（I-II 期）患者中潜在的高风险个体，补充了传统分期的不足。

### 7. 优点
*   **临床可转化性强**：使用标准的组织化学染色（马松三色）和免疫组化，易于集成到现有的病理工作流中。
*   **多维度分析**：首次在 TNBC 中整合了胶原的物理结构（架构）和生化比例（成分），提供了更全面的 ECM 视角。
*   **定量化**：将主观的病理观察转化为客观的计算指标，减少了人为偏差。

### 8. 不足与局限
*   **样本量限制**：79 例样本对于建立稳健的临床预测模型来说偏少，需在大规模多中心队列中验证。
*   **空间代表性**：使用组织微阵列（TMA）核心样本可能无法完全代表整块肿瘤切片的空间异质性。
*   **治疗干扰**：回顾性队列中患者接受的化疗方案不统一，可能对胶原重塑和生存结局产生混杂影响。

（完）
