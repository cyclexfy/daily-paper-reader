---
title: Molecular Characterization of T-Lineage Acute Lymphoblastic Leukemia by an Optimal-Transport Based Multi-Omics Integration Framework
title_zh: 基于最优传输的多组学整合框架对T细胞谱系急性淋巴细胞白血病的分子特征描述
authors: "Li, L., Wang, J., Wan, S."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727257v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 利用最优传输整合多组学数据表征白血病
tldr: T-ALL是一种复杂异质性的儿童白血病，现有诊断方法耗时且计算模型多依赖单模态数据。为此提出OTTER框架，通过模态特异性变分自编码器和Gromov-Wasserstein最优传输整合RNA-seq与基因组变异数据，保留各模态几何结构。在1309名患者、17亚型队列中验证，成功识别亚型驱动特征和跨组学互作，提供了可解释的多组学整合方案并可推广至其他癌症。
source: biorxiv
selection_source: fresh_fetch
motivation: 当前T-ALL分型方法劳动密集且依赖单模态数据，缺乏有效的多组学整合手段。
method: 提出OTTER，一种基于最优传输的多模态深度学习框架，分别编码RNA-seq和体细胞变异，并用Gromov-Wasserstein最优传输对齐潜空间。
result: 在COG AALL0434队列中应用，通过梯度分析识别了亚型驱动的分子特征及跨组学协调程序。
conclusion: OTTER为多组学驱动的T-ALL分子表征提供了原则性、可解释且计算有效的框架，可推广至其他癌症。
---

## 摘要
T细胞谱系急性淋巴细胞白血病（T-ALL）是一种侵袭性儿童恶性肿瘤，其特征是在多个分子层面上存在复杂的异质性。准确的亚型分类对于理解疾病机制、风险分层和指导靶向治疗策略至关重要。然而，当前的诊断方法劳动密集且耗时，现有的计算方法受限于对单一模态数据或简单整合策略的依赖。异质性多组学数据的高效整合仍是一个主要的计算挑战。我们提出了OTTER（基于最优传输的转录组学和基因组学表征融合），这是一种新颖的多模态深度学习框架，可联合建模RNA-seq基因表达和体细胞基因组变异数据，用于T-ALL的分子特征描述。OTTER通过模态特定的变分自编码器编码每种组学模态，并使用Gromov-Wasserstein最优传输（GW-OT）对齐得到的潜在表征，该方法在无需共享特征空间的情况下保留了每种模态的内部几何结构。我们将OTTER应用于儿童肿瘤组（COG）AALL0434队列，该队列包含1,309名患者，覆盖17种T-ALL亚型。在保留集上进行了基于梯度的特征重要性和跨组学交互分析，以识别亚型驱动的分子特征和跨模态协调程序。OTTER为多组学驱动的T-ALL分子特征描述提供了一个有原则、生物学可解释且计算高效的框架。通过利用GW-OT进行几何保持的跨模态对齐，以及基于梯度的可解释性进行跨组学交互分析，OTTER超越了单模态方法，揭示了T-ALL的协调分子景观。该框架可推广至其他癌症和多组学整合任务。

## Abstract
T-lineage acute lymphoblastic leukemia (T-ALL) is an aggressive pediatric malignancy characterized by complex heterogeneity across multiple molecular layers. Accurate subtyping is essential for understanding disease mechanisms, risk stratification, and guiding targeted therapeutic strategies. However, current diagnostic approaches are labor-intensive and time-consuming, and existing computational methods are limited by reliance on single-modality data or simple integration strategies. Effective integration of heterogeneous multi-omics data remains a major computational challenge. We present OTTER (Optimal Transport-based Transcriptomics and gEnomics Representation fusion), a novel multi-modal deep learning framework that jointly models RNA-seq gene expression and somatic genomic variant data for T-ALL molecular characterization. OTTER encodes each omics modality through a modality-specific variational autoencoder and aligns the resulting latent representations using Gromov-Wasserstein optimal transport (GW-OT), which preserves the internal geometric structure of each modality without requiring a shared feature space. We applied OTTER to the Children's Oncology Group (COG) AALL0434 cohort comprising 1,309 patients across 17 T-ALL subtypes. Gradient-based feature importance and cross-omics interaction analysis were performed on the holdout set to identify subtype-driving molecular features and cross-modal coordinated programs. OTTER provides a principled, biologically interpretable, and computationally effective framework for multi-omics-driven T-ALL molecular characterization. By leveraging GW-OT for geometry-preserving cross-modal alignment and gradient-based interpretability for cross-omics interaction profiling, OTTER goes beyond single-modality approaches to uncover the coordinated molecular landscape of T-ALL. The framework is generalizable to other cancers and multi-omics integration tasks.