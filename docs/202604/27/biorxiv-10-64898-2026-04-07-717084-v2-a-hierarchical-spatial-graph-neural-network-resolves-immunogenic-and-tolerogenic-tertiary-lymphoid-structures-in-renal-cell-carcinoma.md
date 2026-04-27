---
title: A Hierarchical Spatial Graph Neural Network Resolves Immunogenic and Tolerogenic Tertiary Lymphoid Structures in Renal Cell Carcinoma
title_zh: 一种分层空间图神经网络解析肾细胞癌中的免疫原性和耐受性三级淋巴结构
authors: "Peng, G."
date: 2026-04-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.07.717084v2.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于肾细胞癌三级淋巴结构分类的图神经网络
tldr: 本研究针对肿瘤微环境中三级淋巴结构（TLS）的功能异质性，开发了一种分层空间图神经网络。该模型利用10x Visium空间转录组数据，通过图注意力与微分池化技术，将点位信号聚合为生态位和区域表征，从而精准区分免疫原性与耐受性TLS。研究不仅在肾细胞癌中取得高准确度，还揭示了非TLS区域CXCL13与免疫耗竭的相关性，解释了其在体转录组中与预后负相关的矛盾现象。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决传统体转录组学无法区分具有抗肿瘤作用的免疫原性TLS与促进免疫逃逸的耐受性TLS这一临床难题。
method: 提出一种结合图注意力网络（GAT）和微分池化（DiffPool）的三层架构图神经网络，对空间转录组图谱进行分层分类。
result: 模型在肾细胞癌验证中表现优异，并成功跨癌种识别出肝癌环境中的耐受性TLS，同时发现大部分CXCL13信号源于非TLS区域且与耗竭标记物共表达。
conclusion: 该分层图神经网络为解析TLS功能状态提供了有力工具，并阐明了空间异质性对肿瘤免疫预后评估的重要性。
---

## 摘要
肿瘤微环境中的三级淋巴结构（TLS）在功能上呈现出从免疫原性（驱动生发中心反应和抗肿瘤免疫）到耐受性（含有调节性T细胞和抑制性髓系群体）的光谱分布。区分这些状态具有重要的临床意义：免疫原性TLS预示着免疫检查点抑制剂（ICI）的反应，而耐受性TLS可能促进免疫逃逸。大体转录组学（Bulk transcriptomics）将有效的TLS与耗竭的免疫浸润混为一谈，掩盖了这一区别。我们提出了一种分层图神经网络（GNN），直接在10x Visium空间转录组图上运行，以在簇级别分类TLS的功能状态。该模型采用结合了图注意力（GAT）和微分池化（DiffPool）的三尺度架构，在预测免疫原性与耐受性状态之前，将点位（spot）级别的信号分层聚合为生态位（niche）和区域级别的表示。该模型在来自24个肾细胞癌（RCC）Visium样本（GSE175540）的915个TLS簇上进行了训练，在验证集上达到了0.718的AUC-ROC，并在BIONIKK队列的IgG验证样本上达到了0.908的临床AUC。对独立的多癌症Visium队列（GSE203612；乳腺癌、肝癌、卵巢癌、胰腺癌、子宫癌）进行的零样本迁移正确识别出肝细胞癌含有最具耐受性的TLS，这与已知的免疫抑制性肝肿瘤微环境一致。对TLS和非TLS区域中CXCL13的空间分解显示，85%的组织CXCL13信号源自非TLS实质，其主要与耗竭标志物（平均Spearman rho = 0.233）而非Tfh标志物（CXCR5 rho = 0.039）共表达——这一模式与TCGA-KIRC中大体CXCL13与较差总生存期相关的矛盾现象一致（HR = 1.38, p < 0.001）。代码和处理后的数据已托管至GitHub和Zenodo。

## Abstract
Tertiary lymphoid structures (TLS) in the tumour microenvironment span a functional spectrum from immunogenic -- driving germinal centre reactions and anti-tumour immunity -- to tolerogenic, harbouring regulatory T cells and suppressive myeloid populations. Distinguishing these states is clinically critical: immunogenic TLS predict ICI response whereas tolerogenic TLS may promote immune evasion. Bulk transcriptomics conflates productive TLS with exhausted immune infiltrates, masking this distinction. We present a hierarchical graph neural network (GNN) that operates directly on 10x Visium spatial transcriptomics graphs to classify TLS functional state at the cluster level. Using a three-scale architecture combining graph attention (GAT) and differentiable pooling (DiffPool), the model hierarchically aggregates spot-level signals into niche- and region-level representations before predicting immunogenic versus tolerogenic state. Trained on 915 TLS clusters from 24 renal cell carcinoma (RCC) Visium samples (GSE175540), the model achieves a validation AUC-ROC of 0.718 and a clinical AUC of 0.908 on IgG-validated samples from the BIONIKK cohort. Zero-shot transfer to an independent multi-cancer Visium cohort (GSE203612; breast, liver, ovarian, pancreatic, uterine) correctly identifies hepatocellular carcinoma as harbouring the most tolerogenic TLS, consistent with the known immunosuppressive liver tumour microenvironment. Spatial decomposition of CXCL13 across TLS and non-TLS compartments reveals that 85% of tissue CXCL13 signal originates from non-TLS parenchyma, where it co-expresses primarily with exhaustion markers (mean Spearman rho = 0.233) rather than Tfh markers (CXCR5 rho = 0.039) -- a pattern consistent with the paradoxical association of bulk CXCL13 with worse overall survival in TCGA-KIRC (HR = 1.38, p < 0.001). Code and processed data are deposited at GitHub and Zenodo.