---
title: Generalisable tissue-wide molecular reconstruction from histology
title_zh: 从组织学可推广的组织级分子重建
authors: "Zhang, A., Yu, L., Bian, B., Cao, Y., Ye, S., Han, E., Robertson, H., Dong, Y., Mao, Y., Liu, B., Patrick, E., Kim, J., Yang, J. Y. H."
date: 2026-06-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.09.731252v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: "从H&E组织学重建分子状态"
tldr: "空间转录组学技术难以大规模应用，现有方法依赖稀疏的空间剖析，但受限于分子测量稀疏、基因面板部分重叠和跨数据集重建。GHIST+框架通过整合细胞形态、局部组织环境和共享组织表示，从H&E组织学重建全组织分子状态。在多种癌症和GTEx乳腺组织中，GHIST+成功从稀疏TMA测量重建有生物学意义的全组织分子组织，保留空间结构、细胞类型和年龄相关状态。该框架为从常规组织学进行队列级分子重建提供了可扩展方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: "现有H&E到空间基因表达预测方法难以处理稀疏测量、部分重叠基因面板和跨异质数据集的全组织重建。"
method: GHIST+整合细胞形态、局部组织环境和共享组织表示，将稀疏分子测量扩展为全组织分子图。
result: 在多种癌症和GTEx乳腺组织中，从稀疏TMA测量重建了有生物学意义的全组织分子组织，保留空间结构、细胞类型和年龄相关状态。
conclusion: GHIST+建立了可扩展框架，将稀疏空间剖析转化为全组织分子地图，支持从常规组织学进行队列级分子重建。
---

## 摘要
空间转录组学技术可测量完整组织内的基因表达，但在大规模组织切片和患者队列中仍难以扩展。因此，许多研究依赖组织微阵列（TMAs）或稀疏空间谱系设计，这些设计仅对有限组织区域进行分子测量，且通常使用异质性基因面板生成。

现有的基于H&E的空间基因表达预测方法仍面临稀疏分子测量、部分重叠基因面板以及跨异质性空间数据集的组织级重建等挑战。在此，我们提出GHIST+，一个从H&E组织学重建单细胞分子状态的组织级框架。GHIST+整合细胞形态、局部组织环境和共享组织表示，将稀疏分子测量扩展到跨异质性空间数据集的组织级分子图谱。在多种癌症类型和GTEx乳腺组织中，GHIST+从稀疏的TMA衍生测量中重建了具有生物学意义的组织级分子组织，同时保留空间组织结构、细胞类型组织以及癌症和非癌症环境中与年龄相关的组织状态。GHIST+建立了一个可扩展的框架，将稀疏空间谱系实验转化为组织级分子图谱，从而在异质性空间转录组学环境下从常规组织学实现队列规模的分子重建。

## Abstract
Spatial transcriptomics technologies measure gene expression within intact tissues but remain difficult to scale across large tissue sections and patient cohorts. Consequently, many studies rely on tissue microarrays (TMAs) or sparse spatial profiling designs, where molecular measurements are available for only limited tissue regions and are often generated using heterogeneous gene panels.

Existing H&E to spatial gene expression prediction methods remain challenged by sparse molecular measurements, partially overlapping gene panels and tissue-wide reconstruction across heterogeneous spatial datasets. Here, we present GHIST+, a framework for tissue-wide reconstruction of single-cell molecular states from H&E histology. GHIST+ integrates cellular morphology, local tissue context and shared tissue representations to extend sparse molecular measurements into tissue-wide molecular maps across heterogeneous spatial datasets. Across multiple cancer types and GTEx breast tissues, GHIST+ reconstructs biologically meaningful tissue-wide molecular organisation from sparse TMA-derived measurements while preserving spatial tissue structure, cell-type organisation and age-associated tissue states across cancer and non-cancer settings. GHIST+ establishes a scalable framework for transforming sparse spatial profiling experiments into tissue-wide molecular maps, enabling cohort-scale molecular reconstruction from routine histology under heterogeneous spatial transcriptomic settings.