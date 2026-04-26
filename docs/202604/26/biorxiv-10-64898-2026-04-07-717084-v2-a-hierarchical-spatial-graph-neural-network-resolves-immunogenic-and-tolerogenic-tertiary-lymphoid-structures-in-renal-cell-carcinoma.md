---
title: A Hierarchical Spatial Graph Neural Network Resolves Immunogenic and Tolerogenic Tertiary Lymphoid Structures in Renal Cell Carcinoma
title_zh: 分层空间图神经网络解析肾细胞癌中的免疫原性和耐受性三级淋巴结构
authors: "Peng, G."
date: 2026-04-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.07.717084v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 用于肾细胞癌三级淋巴结构分类的图神经网络
tldr: 本研究针对肿瘤微环境中三级淋巴结构（TLS）的功能异质性，开发了一种分层空间图神经网络。该模型利用10x Visium空间转录组数据，通过图注意力机制和微分池化，将单点信号聚合为区域表征，从而区分免疫原性和耐受性TLS。研究不仅在肾细胞癌中取得高预测精度，还揭示了CXCL13在非TLS区域与免疫耗竭相关的空间分布特征，为精准免疫治疗提供了新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的批量转录组学无法区分具有抗肿瘤作用的免疫原性TLS与促进免疫逃逸的耐受性TLS，限制了临床预后判断。
method: 提出一种结合图注意力网络（GAT）和微分池化（DiffPool）的三层分层图神经网络，直接在空间转录组图谱上对TLS功能状态进行分类。
result: "模型在肾癌验证集和独立多癌症队列中表现优异，并发现85%的CXCL13信号源于非TLS区域且与免疫耗竭标志物共表达。"
conclusion: 该分层GNN模型能有效识别TLS的功能状态，并解释了CXCL13在不同空间隔室中与临床预后相关的矛盾现象。
---

## 摘要
肿瘤微环境中的三级淋巴结构（TLS）在功能上呈现出从免疫原性（驱动生发中心反应和抗肿瘤免疫）到耐受性（含有调节性 T 细胞和抑制性髓系群体）的光谱分布。区分这些状态具有重要的临床意义：免疫原性 TLS 预示着免疫检查点抑制剂（ICI）的疗效，而耐受性 TLS 则可能促进免疫逃逸。批量转录组学（Bulk transcriptomics）将有效的 TLS 与耗竭的免疫浸润混为一谈，掩盖了这一区别。我们提出了一种分层图神经网络（GNN），直接在 10x Visium 空间转录组图谱上运行，以在集群层面分类 TLS 的功能状态。该模型采用结合了图注意力机制（GAT）和可微池化（DiffPool）的三尺度架构，将位点（spot）层面的信号分层聚合为生态位（niche）和区域（region）层面的表征，进而预测免疫原性与耐受性状态。该模型在来自 24 个肾细胞癌（RCC）Visium 样本（GSE175540）的 915 个 TLS 集群上进行了训练，在验证集上的 AUC-ROC 达到 0.718，在 BIONIKK 队列的 IgG 验证样本上的临床 AUC 达到 0.908。在对独立的多癌症 Visium 队列（GSE203612；包括乳腺癌、肝癌、卵巢癌、胰腺癌、子宫癌）进行的零样本迁移中，模型准确识别出肝细胞癌含有最具耐受性的 TLS，这与已知的肝脏肿瘤微环境的免疫抑制特性相一致。对 TLS 和非 TLS 区域的 CXCL13 进行空间分解显示，组织中 85% 的 CXCL13 信号源自非 TLS 实质，且主要与耗竭标志物共表达（平均 Spearman rho = 0.233），而非与 Tfh 标志物共表达（CXCR5 rho = 0.039）——这一模式与 TCGA-KIRC 中批量 CXCL13 与较差总生存期相关的矛盾现象一致（HR = 1.38, p < 0.001）。代码和处理后的数据已存放在 GitHub 和 Zenodo。

## Abstract
Abstract Tertiary lymphoid structures (TLS) in the tumour microenvironment span a functional spectrum from immunogenic -- driving germinal centre reactions and anti-tumour immunity -- to tolerogenic, harbouring regulatory T cells and suppressive myeloid populations. Distinguishing these states is clinically critical: immunogenic TLS predict ICI response whereas tolerogenic TLS may promote immune evasion. Bulk transcriptomics conflates productive TLS with exhausted immune infiltrates, masking this distinction. We present a hierarchical graph neural network (GNN) that operates directly on 10x Visium spatial transcriptomics graphs to classify TLS functional state at the cluster level. Using a three-scale architecture combining graph attention (GAT) and differentiable pooling (DiffPool), the model hierarchically aggregates spot-level signals into niche- and region-level representations before predicting immunogenic versus tolerogenic state. Trained on 915 TLS clusters from 24 renal cell carcinoma (RCC) Visium samples (GSE175540), the model achieves a validation AUC-ROC of 0.718 and a clinical AUC of 0.908 on IgG-validated samples from the BIONIKK cohort. Zero-shot transfer to an independent multi-cancer Visium cohort (GSE203612; breast, liver, ovarian, pancreatic, uterine) correctly identifies hepatocellular carcinoma as harbouring the most tolerogenic TLS, consistent with the known immunosuppressive liver tumour microenvironment. Spatial decomposition of CXCL13 across TLS and non-TLS compartments reveals that 85% of tissue CXCL13 signal originates from non-TLS parenchyma, where it co-expresses primarily with exhaustion markers (mean Spearman rho = 0.233) rather than Tfh markers (CXCR5 rho = 0.039) -- a pattern consistent with the paradoxical association of bulk CXCL13 with worse overall survival in TCGA-KIRC (HR = 1.38, p < 0.001). Code and processed data are deposited at GitHub and Zenodo.