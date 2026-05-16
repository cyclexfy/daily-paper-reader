---
title: Deep Learning for Cross-Domain Spatial Transcriptomic Modeling of Tissue Repair
title_zh: 深度学习用于组织修复的跨域空间转录组建模
authors: "Pham, T. D."
date: 2026-05-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.13.724803v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 跨域空间转录组建模与病理碎片化定量
tldr: 本研究针对空间转录组学中高阶空间组织和跨系统动态特征刻画不足的问题，提出了一种深度学习框架。该框架结合了基于递归的潜在组织状态分析、病理碎片化定量及跨域表示学习，整合了皮肤伤口愈合与鳞状细胞癌等数据集。研究通过图嵌入和递归分析揭示了组织修复与肿瘤微环境中的空间重塑规律，为理解复杂生物系统的病理演变提供了新工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有空间转录组计算方法多侧重于聚类和批次整合，难以有效表征跨异质生物系统的高阶空间组织和可转移的组织状态动态。
method: 提出一种基于图的潜在嵌入框架，利用递归分析刻画空间组织，并通过病理碎片化指数定量评估组织内的空间紊乱程度。
result: 实验表明该框架在组织状态分离上表现优异（平均轮廓系数0.79），并揭示了伤口愈合中的组织修复与肿瘤组织中碎片化增加的显著差异。
conclusion: 基于递归启发的潜在空间分析能够为异质生物系统中的组织组织和病理重塑提供具有生物学解释性的特征刻画。
---

## 摘要
空间转录组学能够在保留完整组织内分子和空间信息的同时，实现对组织结构的探究。然而，现有的计算方法主要集中在聚类和批次整合上，对异质生物系统中高阶空间组织和可迁移组织状态动力学的表征有限。本研究介绍了一个跨域空间转录组框架，其核心是基于递归的潜在组织状态分析、病理碎片化定量，以及伤口修复与肿瘤相关微环境之间的可迁移表示学习。涵盖皮肤伤口愈合、口腔鳞状细胞癌以及头颈部鳞状细胞癌的人类空间转录组数据集被整合到一个基于图的潜在嵌入框架中。在潜在转录组空间内应用递归分析，以表征空间组织和重塑动力学。病理碎片化指数通过递归结构定量了组织内的空间紊乱。学习到的潜在嵌入达到了 0.79 的平均轮廓分数，证明了组织状态的连贯分离。递归分析揭示了伤口重塑过程中空间组织的逐渐恢复，而肿瘤相关组织则表现出增加的碎片化和异质递归结构。独立的单细胞 RNA-seq 参考图谱证明了潜在空间生态位中可复现的多细胞富集模式。该框架表明，受递归启发的潜在空间分析可以为跨异质生物系统的组织结构和病理重塑提供具有生物学解释性的表征。

## Abstract
Spatial transcriptomics enables investigation of tissue organization while preserving molecular and spatial information within intact tissues. However, existing computational methods primarily focus on clustering and batch integration and provide limited characterization of higher-order spatial organization and transferable tissue-state dynamics across heterogeneous biological systems. This study introduces a cross-domain spatial transcriptomic framework centered on recurrence-based latent tissue-state analysis, pathological fragmentation quantification, and transferable representation learning between wound repair and tumor-associated microenvironments. Human spatial transcriptomic datasets spanning cutaneous wound healing, oral squamous cell carcinoma, and head and neck squamous cell carcinoma were integrated within a graph-based latent embedding framework. Recurrence analysis was applied within latent transcriptomic space to characterize spatial organization and remodeling dynamics. A pathological fragmentation index quantified intra-tissue spatial disorganization from recurrence structure. The learned latent embeddings achieved a mean silhouette score of 0.79, demonstrating coherent separation of tissue states. Recurrence analysis revealed progressive restoration of spatial organization during wound remodeling, whereas tumor-associated tissues exhibited increased fragmentation and heterogeneous recurrence structure. Independent single-cell RNA-seq reference atlases demonstrated reproducible multicellular enrichment patterns within latent spatial niches. The proposed framework demonstrates that recurrence-inspired latent spatial analysis may provide biologically interpretable characterization of tissue organization and pathological remodeling across heterogeneous biological systems.