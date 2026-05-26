---
title: "HESTIA: Scalable Multimodal Integration of Histology and High-Resolution Spatial Transcriptomics for Robust Spatial Domain Identification"
title_zh: "HESTIA: 组织学与高分辨率空间转录组学的可扩展多模态整合实现稳健的空间域识别"
authors: "Zhong, Z., Zhu, X., Guo, J., Liao, S., Chen, A."
date: 2026-05-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.14.723098v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 组织学与空间转录组的多模态整合
tldr: 针对亚细胞分辨率空间组学数据规模大、转录组稀疏性导致现有方法难以处理的问题，提出HESTIA多模态算法，通过避免内存密集型计算高效处理大规模数据，在聚类准确性和空间连续性上超越现有方法，并能准确划分结构边界，解析肿瘤异质性和免疫微环境。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有分析框架难以处理高分辨率空间组学带来的大规模数据及严重转录组稀疏性。
method: 提出HESTIA算法，通过规避内存密集型计算高效整合组织学和空间转录组数据。
result: HESTIA在聚类准确性和空间连续性上优于现有方法，准确描绘精细结构边界，成功解析临床相关肿瘤异质性和免疫微环境。
conclusion: HESTIA为大规模高分辨率空间组学数据提供了鲁棒的空间域识别方法，推动空间组学在病理和生物学中的应用。
---

## 摘要
空间组学通过提供关于天然组织微环境如何调节细胞功能和疾病机制的宝贵见解，彻底改变了分子生物学。要准确捕捉这种结构复杂性并解码潜在的生物学过程，需要有效整合来自多种模态的数据。然而，过渡到亚细胞分辨率会带来大规模数据量和严重的转录组稀疏性，这对当前的分析框架构成了挑战。为此，我们提出了HESTIA（组织学增强的可扩展跨分辨率空间转录组学整合），这是一种高效的多模态算法，专为识别大规模、高分辨率空间组学数据中的空间域而设计。通过规避内存密集型计算，HESTIA能够轻松处理现有算法因内存限制而无法处理的大规模数据集。HESTIA在聚类准确性和空间连续性方面优于当前的多模态方法，能够精确描绘精细的结构边界。此外，将HESTIA应用于大规模病理样本，成功解析了肺癌和结直肠癌中临床相关的瘤内异质性，并绘制了不同的免疫微环境。

## Abstract
Spatial omics has revolutionized molecular biology by providing invaluable insights into how native tissue microenvironments regulate cellular functions and disease mechanisms. Accurately capturing this structural complexity and decoding the underlying biological processes requires effectively integrating data from multiple modalities. However, transitioning to subcellular resolutions introduces massive data scales and severe transcriptomic sparsity, which challenge current analytical frameworks. To address this, we present HESTIA (Histology-Enhanced Scalable cross-Resolution inTegration for spatial trAnscriptomics), a highly efficient multimodal algorithm designed for identifying spatial domains in large-scale, high-resolution spatial omics data. By circumventing memory-intensive computations, HESTIA effortlessly processes massive datasets that existing algorithms fail due to memory constraints. HESTIA outperforms current multimodal methods in clustering accuracy and spatial continuity, accurately delineating fine structural boundaries. Furthermore, applying HESTIA to large-scale pathological samples successfully dissects clinically relevant intratumoral heterogeneity and maps distinct immune microenvironments in lung and colorectal cancers.