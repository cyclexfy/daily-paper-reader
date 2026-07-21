---
title: Multicenter self-supervised computational pathology identifies prognostic histomorphological phenotypes in colorectal cancer
title_zh: 多中心自监督计算病理学识别结直肠癌预后组织形态表型
authors: "Heilijgers, F., Le, H. A., Coudray, N., Karimkhan, A., Chen, D., Peeters, K. C. M. J., Hacking, S., Mesker, W. E., Tsirigos, A., UNITED collaboration,"
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.15.738753v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: "在结直肠癌H&E全切片图像上进行自监督计算病理学分析"
tldr: "常规H&E病理切片中包含预后信号，但难以大规模提取。本研究开发自监督计算病理框架HPL-PanColon，提取组织表型聚类并训练注意力生存模型，在1024例结直肠癌队列中生成CHiPS评分。CHiPS较TNM模型提升c-index至0.706，高风险区富集间质、纤维炎性形态，低风险区为腺上皮模式。框架实现了可解释的组织学生存预测与空间肿瘤生物学发现。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738753-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1387, \"height\": 1944, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738753-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1276, \"height\": 1830, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738753-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1503, \"height\": 2197, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738753-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1585, \"height\": 979, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738753-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1207, \"height\": 1769, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738753-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1510, \"height\": 993, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-15-738753-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1183, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-15-738753-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1180, \"height\": 2347, \"label\": \"Table\"}]"
motivation: "结直肠癌H&E全切片图像蕴含预后信息，但现有方法难以高效提取可解释的表型信号。"
method: 基于自监督模型HPL-PanColon获取组织表型聚类，训练注意力生存模型生成CHiPS评分，并关联空间转录组学。
result: CHiPS显著分层患者无病生存率，联合TNM模型c-index从0.683升至0.706，高风险区对应促纤维增生和间质形态。
conclusion: 建立了可扩展的结直肠癌可解释组织学生存框架，揭示了形态学与空间微环境程序的关联。
---

## 摘要
H&E全切片图像捕获了肿瘤形态及周围微环境中编码的预后信息，但这些信号仍难以大规模提取和解读。在此，我们开发了一种自监督计算病理学框架，用于预测结直肠癌的无病生存期，并将模型推导的风险与可解释的组织形态和空间肿瘤生物学联系起来。利用一个跨越结直肠腺瘤和浸润性结直肠癌的多中心发育队列，我们训练了HPL-PanColon——一种自监督表示模型——以提取图块级嵌入并识别腺瘤-癌谱系中反复出现的组织形态表型聚类。与通用病理学基础模型相比，HPL-PanColon生成的表示减少了机构和数据集特定的批次效应。随后，我们在一个留一机构外的框架中，将HPL-PanColon应用于包含1,024名结直肠癌患者的全球生存队列，利用图块嵌入训练基于注意力的生存模型，并推导出结肠组织形态预后评分（CHiPS）。CHiPS根据无病生存期对患者进行分层，并为基于UICC TNM的临床病理模型提供了互补的预后信息，将c指数从0.683提升至0.706。整合模型注意力与表型分配，将CHiPS相关风险追溯至病理学家可识别的组织模式，高风险区域富含促纤维增生、间质和纤维炎症形态，而低风险区域反映富含肿瘤的上皮腺体模式。空间转录组学分析进一步将高风险形态与成纤维细胞、血管周围细胞、肌成纤维细胞和免疫反应性肿瘤微环境程序联系起来，而低风险形态则映射至上皮和肿瘤富集区域。这些发现建立了一个可扩展的框架，用于结直肠癌中基于组织学的可解释预后和空间生物学发现。

## Abstract
H&E whole-slide images capture prognostic information encoded in tumor morphology and the surrounding microenvironment, but these signals remain difficult to extract and interpret at scale. Here, we developed a self-supervised computational pathology framework to predict disease-free survival in colorectal cancer and link model-derived risk to interpretable histomorphology and spatial tumor biology. Using a multicenter developmental cohort spanning colorectal adenomas and invasive colorectal cancer, we trained HPL-PanColon, a self-supervised representation model, to extract tile-level embeddings and identify recurrent histomorphological phenotype clusters across the adenoma-carcinoma spectrum. Compared with general-purpose pathology foundation models, HPL-PanColon yielded representations with reduced institution- and dataset-specific batch effects. We then applied HPL-PanColon to a global survival cohort of 1,024 colorectal cancer patients in a leave-one-institution-out framework, using tile embeddings to train an attention-based survival model and derive the Colon Histomorphology Prognostic Score (CHiPS). CHiPS stratified patients by disease-free survival and provided complementary prognostic information to a UICC TNM-informed clinicopathological model, increasing the c-index from 0.683 to 0.706. Integrating model attention with phenotype assignments traced CHiPS-associated risk to pathologist-recognizable tissue patterns, with high-risk regions enriched for desmoplastic, stromal, and fibroinflammatory morphologies and low-risk regions reflecting tumor-rich epithelial glandular patterns. Spatial transcriptomic analysis further linked high-risk morphologies to fibroblastic, perivascular, myofibroblastic, and immune-reactive tumor microenvironment programs, while low-risk morphologies mapped to epithelial and tumor-enriched regions. These findings establish a scalable framework for interpretable histology-based prognosis and spatial biological discovery in colorectal cancer.

---

## 论文详细总结（自动生成）

### 0. 论文的源代码链接
无（论文未提供公开的源代码仓库链接）。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：结直肠癌（CRC）的常规H&E全切片图像中蕴含丰富的预后信息，尤其是肿瘤形态和微环境特征，但现有方法难以大规模、可解释地提取这些信号。传统临床病理模型（如UICC TNM分期）虽然有效，但忽略了组织形态学中的细微异质性。
- **整体含义**：该研究旨在开发一个自监督计算病理学框架，从H&E图像中自动学习与预后相关的组织表型，生成可解释的预后评分（CHiPS），并将其与空间转录组学数据关联，揭示形态学背后的生物学程序。这项工作为结直肠癌的预后评估提供了可扩展、可解释的工具，并推动了“形态-分子”关联的发现。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用自监督学习在大量无标签的结直肠腺瘤-癌谱系组织图像上训练一个专门的表示模型（HPL-PanColon），以提取图块级嵌入并聚类得到可解释的组织形态表型。然后，基于这些嵌入训练注意力生存模型，预测无病生存期（DFS），并生成一个综合评分（CHiPS）。最后通过注意力权重和表型映射，将风险回溯到具体的组织模式上。
- **关键技术细节**：
  - **HPL-PanColon模型**：自监督表示模型（基于对比学习或掩码图像建模等，具体细节未详述），在多中心发育队列（涵盖腺瘤和浸润性CRC）上训练，旨在减少机构和数据集特定的批次效应。
  - **表型聚类**：对图块嵌入进行无监督聚类，得到反复出现的组织形态表型（如腺上皮、间质、纤维炎症等）。
  - **注意力生存模型**：基于Transformer或注意力机制的多示例学习（MIL）模型，利用图块嵌入预测患者生存风险，并使用留一机构外（leave-one-institution-out）交叉验证。
  - **CHiPS评分**：由注意力生存模型输出的风险分数，整合全切片信息。
  - **可解释性分析**：通过注意力权重与表型分配的联合分析，识别高风险和低风险组织模式。空间转录组学（ST）将形态表型与基因表达程序（如成纤维细胞、免疫反应性TME）关联。

### 3. 实验设计：数据集、基准测试与对比方法
- **数据集**：
  - **发育队列**：多中心数据集，包含结直肠腺瘤和浸润性结直肠癌的H&E图像，用于训练HPL-PanColon。
  - **全球生存队列**：1,024例结直肠癌患者，来自多个机构，用于训练和评估生存模型（留一机构外验证）。
- **基准测试**：主要对比了基于UICC TNM的临床病理模型（仅使用临床病理变量），以及加入CHiPS后的联合模型。
- **对比方法**：
  - 与通用病理学基础模型（如自监督模型在非结直肠癌数据上训练的表示）比较，HPL-PanColon的表示能减少批次效应（机构和数据集特异性）。
  - 生存预测性能：采用c-index指标，比较单纯TNM模型、CHiPS模型以及两者联合模型。
- **结果**：CHiPS单独分层能力显著，联合模型c-index从0.683提升至0.706。

### 4. 资源与算力
论文未明确说明所使用的GPU型号、数量或训练时长。仅提及训练了自监督模型和注意力生存模型，但未提供算力消耗细节。

### 5. 实验数量与充分性
- **实验组数**：
  - 发育队列训练自监督模型（一个模型训练）。
  - 生存队列使用留一机构外验证（根据机构数可能产生多个子实验）。
  - 消融实验：可能包括与通用基础模型的比较、不同聚类数目的影响等（文中未详细列出所有消融实验）。
  - 空间转录组学关联分析（一组独立验证）。
- **充分性评价**：实验覆盖了训练、验证、多中心外部验证和生物学解释，整体较为充分。但缺少详细的消融实验（如不同自监督策略、不同聚类算法）以及多个生存模型架构的对比。公平性方面，留一机构外设计减少了机构偏差，但未与现有深度学习预后模型（如PORPOISE、DeepSurv等）进行直接比较。

### 6. 论文的主要结论与发现
- **主要结论**：自监督计算病理学框架HPL-PanColon能够提取结直肠癌中与预后相关的组织形态表型，生成的CHiPS评分可以独立于TNM分期预测无病生存期，并与临床病理模型互补，提升预测性能。
- **关键发现**：
  - 高风险区域富含促纤维增生（desmoplastic）、间质（stromal）和纤维炎症（fibroinflammatory）形态；低风险区域为富含肿瘤的上皮腺体模式。
  - 空间转录组学将高风险形态与成纤维细胞、血管周围细胞、肌成纤维细胞和免疫反应性TME程序关联；低风险形态对应上皮和肿瘤富集区域。
  - 自监督表示减少了机构和数据集批次效应，优于通用病理基础模型。

### 7. 优点：方法或实验设计上的亮点
- **自监督表示专门针对结直肠腺瘤-癌谱系**：相比通用基础模型，更适应下游任务，减少批次效应。
- **留一机构外验证**：严格的多中心验证，增强了模型的泛化性和公平性。
- **可解释性**：将深度学习注意力与病理学家可识别的组织模式（表型聚类）结合，实现了透明风险解释。
- **多模态关联**：结合空间转录组学，为形态学发现提供了分子生物学证据，提升了科学深度。
- **端到端流程**：从图像到预后评分再到空间生物学，形成了一个完整的可扩展框架。

### 8. 不足与局限
- **源代码未公开**：限制了可复现性和社区进一步优化。
- **算力开销未报告**：无法评估方法的计算成本。
- **对比基准不够广泛**：仅与TNM模型和自己训练的基础模型对比，未与现有先进的深度学习生存预测模型（如基于GNN的、多模态融合的）进行比较。
- **聚类表型的病理学验证**：虽然进行了关联，但未进行大规模病理专家一致性验证，可能存在语义偏差。
- **空间转录组学样本量可能较小**：文中未详细说明ST分析所用样本数，且ST数据可能来自不同队列，存在批次效应风险。
- **单一癌种**：方法针对结直肠癌，是否推广到其他癌种未知。
- **预后指标**：只评估了无病生存期（DFS），未评估总生存期（OS）或其他终点。

（完）
