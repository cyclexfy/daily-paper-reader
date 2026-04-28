---
title: Proteome-anchored multi-omics propagation of recurrent somatic alterations defines tumour states in cervical cancer and enables state-guided drug repurposing
title_zh: 以蛋白质组为锚点的复发性体细胞变异多组学传播定义了宫颈癌的肿瘤状态，并实现了状态引导的药物重定位
authors: "Hamese, S., Takundwa, M., Prinsloo, E., Thimiri Govindaraj, D. B."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.719801v1.full.pdf"
tags: ["query:cpath"]
score: 7.5
evidence: 整合多组学数据分析宫颈癌状态
tldr: 本研究针对宫颈癌的分子异质性，开发了一个以蛋白质组为核心的多组学分析框架。通过整合TCGA-CESC队列的基因组、表观组、转录组和蛋白质组数据，研究者成功将复发性体细胞突变映射为功能性肿瘤状态，并利用连接性图谱识别出能逆转这些状态的潜在药物，为宫颈癌的精准治疗和药物重用提供了新路径。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在超越单一的突变频率分析，通过多组学整合揭示宫颈癌中具有功能意义的肿瘤状态及其潜在的治疗靶点。
method: 利用弹性网络分类器将基因、转录和表观遗传状态投影到蛋白质组，并结合L1000数据库进行连接性图谱分析以筛选候选药物。
result: 成功定义了PIK3CA和DST等关键程序的蛋白质组特征，发现治疗脆弱性集中在应激缓冲和生存系统而非单一癌基因驱动。
conclusion: 该研究建立了一个可扩展的蛋白质组锚定框架，实现了从突变分析到功能性肿瘤状态推断及药物发现的跨越。
---

## 摘要
宫颈癌表现出显著的分子异质性，仅凭体细胞突变频率不足以完全代表功能后果或治疗脆弱性。在此，我们提出一个以蛋白质组为锚点的生物信息学框架，该框架整合了基因组、表观基因组、转录组和蛋白质组数据，以推断功能表达的肿瘤状态，并提名候选的状态逆转扰动剂。利用来自 TCGA 宫颈鳞状细胞癌和子宫内膜腺癌（TCGA-CESC）队列的匹配多组学数据，首先将复发性突变基因置于宫颈癌突变图谱中进行背景化，并根据调节性 DNA 甲基化扰动进行优先级排序。对于选定的程序（包括 PIK3CA、TTN、MUC5B、SYNE1 和 DST），在基因组、转录组和表观基因组水平上独立定义了正交分子状态，并使用基于 RPPA 的弹性网络分类器将其投影到蛋白质组上。这些模型在多种模态中表现出高判别性能，确立了上游分子状态在蛋白质组水平编码的可行性。随后，针对 L1000 Fireworks Display 查询了具有方向特征的状态特异性蛋白质组特征，以识别预测可逆转推断肿瘤状态的扰动剂。连通性映射揭示了以压力缓冲和生存系统为中心的收敛脆弱性轴，而非单一的致癌驱动因子，包括复制压力耐受、蛋白质稳态和分泌能力、检查点控制、凋亡缓冲、代谢适应和炎症信号传导。在所研究的程序中，与 DST 相关的状态产生了统计学上最稳健的连通性，将 RTK-mTOR 信号传导、凋亡启动和代谢-炎症调节确定为连贯的治疗假设，而其他程序则产生了与假设生成一致的较温和信号。总而言之，本研究建立了一个可扩展的、以蛋白质组为锚点的多组学框架，超越了以突变为中心的分析，转向功能性肿瘤状态推断，并为宫颈癌中状态引导的治疗假设生成提供了一条有原则的途径。

## Abstract
Cervical cancer exhibits substantial molecular heterogeneity, and somatic mutation frequency alone is an incomplete surrogate for functional consequence or therapeutic vulnerability. Here, we present a proteome-anchored bioinformatics framework that integrates genomic, epigenomic, transcriptomic, and proteomic data to infer functionally expressed tumour states and to nominate candidate state-reversing perturbagens. Using matched multi-omics data from the TCGA Cervical Squamous Cell Carcinoma and Endocervical Adenocarcinoma (TCGA-CESC) cohort, recurrently mutated genes were first contextualised within the cervical cancer mutational landscape and prioritised based on regulatory DNA methylation perturbations. For selected programmes, including PIK3CA, TTN, MUC5B, SYNE1, and DST, orthogonal molecular states were independently defined at the genomic, transcriptomic, and epigenomic levels and projected onto the proteome using RPPA-based elastic-net classifiers. These models demonstrated high discriminatory performance across multiple modalities, establishing the feasibility of proteome-level encoding of upstream molecular states. State-specific, directionally signed proteomic signatures were subsequently queried against the L1000 Fireworks Display to identify perturbagens predicted to reverse inferred tumour states. Connectivity mapping revealed convergent vulnerability axes centred on stress-buffering and survival systems rather than single oncogenic drivers, including replication stress tolerance, proteostasis and secretory capacity, checkpoint control, apoptotic buffering, metabolic adaptation, and inflammatory signalling. Among the programmes examined, DST-associated states produced the most statistically robust connectivity, prioritising RTK-mTOR signalling, apoptotic priming, and metabolic-inflammatory modulation as coherent therapeutic hypotheses, while other programmes yielded more moderate signals consistent with hypothesis generation. Collectively, this study establishes a scalable, proteome-anchored multi-omics framework that moves beyond mutation-centric analysis toward functional tumour-state inference and provides a principled route for state-guided therapeutic hypothesis generation in cervical cancer.