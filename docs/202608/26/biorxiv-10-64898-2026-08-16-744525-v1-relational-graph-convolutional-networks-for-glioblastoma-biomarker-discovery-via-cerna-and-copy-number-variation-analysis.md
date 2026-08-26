---
title: Relational Graph Convolutional Networks for Glioblastoma Biomarker Discovery via ceRNA and Copy Number Variation Analysis
title_zh: 关系图卷积网络用于通过ceRNA和拷贝数变异分析发现胶质母细胞瘤生物标志物
authors: "Khandelwal, S., Jarvis, N., Zhan, J."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.16.744525v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 基于RGCN的基因组数据整合用于癌症预后生物标志物发现，但缺少组织病理图像
tldr: "胶质母细胞瘤预后极差，5年生存率仅6.9%，缺乏可靠生物标志物。现有ceRNA和CNV分析未整合多种调控机制。提出基于关系图卷积网络(RGCN)的晚期融合集成架构，联合分析ceRNA与CNV知识图谱。识别出五个新生物标志物，生存分析证实其预后价值，为靶向治疗和非侵入诊断提供候选。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法忽略ceRNA与CNV等调控机制的整合，导致胶质母细胞瘤生物标志物发现受限。
method: 构建ceRNA和CNV知识图谱，采用关系图卷积网络(RGCN)并通过晚期融合集成架构联合学习。
result: 模型优于基线，识别出hsa-miR-196a等五个新生物标志物，且经Kaplan-Meier和Cox回归验证。
conclusion: 晚期融合RGCN集成可有效捕获复杂基因互作，为胶质母细胞瘤生物标志物发现提供新框架。
---

## 摘要
胶质母细胞瘤（GBM）是一种高度侵袭性的脑肿瘤，其5年生存率极低，仅为6.9%，这主要归因于缺乏可靠的生物标志物。虽然竞争性内源RNA（ceRNA）和拷贝数变异（CNV）分析为生物标志物识别提供了独特的潜力，但当前的方法忽略了整合多种调控机制进行生物标志物检测。为了解决这一局限性，我们通过一种新颖的晚期融合集成架构，将关系图卷积网络（RGCNs）应用于ceRNA和CNV知识图谱。所提出的架构优于基线模型，并识别出五个新的生物标志物，包括hsa-miR-196a和hsa-miR-224。Kaplan-Meier生存分析和Cox回归表明，所识别的基因具有显著的预后和诊断能力。Kaplan-Meier曲线的早期分层表明这些基因在患者生存预测中的潜在价值。结果表明，晚期融合RGCN集成能够有效捕获复杂的基因相互作用，克服现有模型的局限性，并为生物标志物发现提供了一个框架。这些新的生物标志物可作为未来GBM治疗开发的潜在靶点和非侵入性诊断检测的候选标志物。

## Abstract
Glioblastoma (GBM) is a highly aggressive brain tumor with an extremely poor 5-year survival rate of 6.9%, largely attributable to the lack of reliable biomarkers. While competing endogenous RNA (ceRNA) and copy number variation (CNV) analyses offer unique biomarker identification potential, current approaches neglect the integration of multiple regulatory mechanisms for biomarker detection. To address this limitation, we applied relational graph convolutional networks (RGCNs) to ceRNA and CNV knowledge graphs through a novel late fusion ensemble architecture. The proposed architecture outperformed baseline models and identified five novel biomarkers, including hsa-miR-196a and hsa-miR-224. Kaplan-Meier survival analysis and Cox regression indicated that the identified genes hold significant prognostic and diagnostic power. The early stratification of the Kaplan-Meier curves indicates the potential these genes hold for patient survival prediction. The results illustrate that a late fusion RGCN ensemble effectively captures complex gene interactions, overcoming limitations of existing models and providing a framework for biomarker discovery. The novel biomarkers serve as prospective targets for future GBM therapeutic development and candidates for non-invasive diagnostic assays.