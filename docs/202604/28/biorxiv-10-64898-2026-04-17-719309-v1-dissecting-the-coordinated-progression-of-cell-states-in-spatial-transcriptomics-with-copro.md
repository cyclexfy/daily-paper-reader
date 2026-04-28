---
title: Dissecting the coordinated progression of cell states in spatial transcriptomics with CoPro
title_zh: 利用 CoPro 剖析空间转录组学中细胞状态的协调进展
authors: "Miao, Z., Qu, Y., Huang, S., Laux, L., Peters, S., Aristel, A., Zhang, Z., Niedernhofer, L. J., McMahon, A., Kim, J., Zhang, N."
date: 2026-04-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.17.719309v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 空间转录组学与组织学的计算框架
tldr: 空间转录组学研究面临识别跨空间连续变化且在细胞类型间协调的基因表达程序的挑战。本文提出CoPro计算框架，旨在检测细胞状态的空间协调进展。CoPro支持监督和无监督模式，能有效分离重叠的空间模式，适用于多种单细胞级空间技术。通过对结肠、大脑、肝脏和肾脏数据的分析，证明了其在解析复杂组织空间协调和解耦生物过程方面的强大能力。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决空间转录组学中难以识别跨空间连续变化且在不同细胞类型间协同演化的基因表达程序的问题。
method: 开发了名为CoPro的计算框架，通过监督或无监督模式识别共变基因程序，并利用灵活的核设计解耦重叠的空间模式。
result: 在结肠、肝脏、大脑和肾脏等多种组织中成功分离了分化、炎症、衰老及解剖分区等重叠的生物信号。
conclusion: CoPro是分析复杂组织中基因表达空间协调性并解耦重叠生物过程（如解剖结构与疾病变异）的有力工具。
---

## 摘要
空间转录组学使得研究细胞如何在组织内协调其分子状态成为可能，从而为正常功能和疾病过程提供见解。一个关键挑战是识别在空间上连续变化且在细胞类型之间协调的基因表达程序。我们提出了 CoPro，这是一个用于检测细胞状态空间协调进展的计算框架。CoPro 可以在监督和无监督模式下运行，以识别在细胞类型内部或之间共同变化的基因程序，并解离多个重叠的空间模式。CoPro 可应用于单细胞水平的空间转录组数据集，包括 MERFISH、SeqFISH+、Xenium 以及组织学推断的转录组数据。我们利用从结肠、大脑、肝脏和肾脏组织收集的数据证明了 CoPro 的实用性。在结肠中，CoPro 将沿隐窝轴的上皮分化与空间局限的炎症信号区分开来。在衰老的肝脏中，它识别出叠加在解剖分区上的多种衰老相关细胞程序。在大脑中，灵活的核设计能够解耦沿背腹轴和内侧-外侧轴的基因表达梯度。在肾脏中，CoPro 识别出对肾单位功能至关重要的肾小管-血管协调。这些结果证明了 CoPro 在分析复杂组织中基因表达的空间协调以及解离重叠生物过程（如解剖结构和疾病相关变异）方面的实用性。

## Abstract
Spatial transcriptomics enables the study of how cells coordinate their molecular states within tissue, providing insight into both normal function and disease processes. A key challenge is to identify gene expression programs that vary continuously across space and are coordinated between cell types. We present CoPro, a computational framework for detecting the spatially coordinated progression of cellular states. CoPro can operate in both supervised and unsupervised modes to identify gene programs that co-vary within or between cell types, and to disentangle multiple overlapping spatial patterns. CoPro can be applied to single-cell-level spatial transcriptomics datasets, including MERFISH, SeqFISH+, Xenium, and histology-imputed transcriptomic data. We demonstrate the utility of CoPro with data collected from colon, brain, liver, and kidney tissues. In the colon, CoPro separates epithelial differentiation along the crypt axis from spatially localized inflammatory signals. In the aging liver, it identifies multiple aging-associated cellular programs superimposed on anatomical zonation. In the brain, the flexible kernel design enables the decoupling of the gene expression gradient along the dorsal-ventral and medial-lateral axes. In the kidney, CoPro identifies tubule-vasculature coordination that is essential in nephron function. These results demonstrate CoPros utility for analyzing spatial coordination of gene expression in complex tissues and disentangling overlapping biological processes, such as anatomical organization and disease-associated variation.