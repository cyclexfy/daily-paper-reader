---
title: Probabilistic coupling of cellular and microenvironmental heterogeneity by masked self-supervised learning
authors: "Kojima, Y., Tanaka, Y., Hirose, H., Chiwaki, F., Nishimura, K., Hayashi, S., Itahashi, K., Ishikawa, M., Shimamura, T., Mano, H."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.719876v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于组织微环境嵌入的掩码自监督学习
tldr: 采用基于Transformer的掩码自监督框架来学习组织异质性的表示。
source: biorxiv
selection_source: fresh_fetch
motivation: 用于组织微环境嵌入的掩码自监督学习。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWSpatial omics technologies have advanced to single-cell resolution, enabling systematic analysis of tissue microenvironments alongside cellular-state heterogeneity. However, computationally defining microenvironmental states at single-cell resolution and identifying representations most informative for biological discovery remain major challenges. Here we present Mievformer, a Transformer-based masked self-supervised framework that learns microenvironmental embeddings by encoding neighboring cellular states and relative spatial configurations to parameterize the conditional distribution of continuous cell states at central spatial positions. Through InfoNCE optimization, Mievformer learns representations that capture the relative enrichment of cell states across microenvironments, formalized as a conditional density ratio, thereby enabling probabilistic inference of the coupling between microenvironmental and cellular heterogeneity. Mievformer outperformed existing methods in niche clustering on simulated spatial transcriptomics data and achieved the highest average performance across five real datasets spanning three spatial transcriptomics platforms when evaluated using DREC, a ground-truth-free metric that most strongly correlated with ground-truth performance in simulations. Beyond conventional clustering, Mievformer enables identification of cellular subpopulations based on their microenvironmental distribution and detection of gene-expression signatures associated with colocalization of specific cell populations. Together, these results establish Mievformer as a quantitatively robust and biologically informative framework for learning microenvironment representations in spatial omics.