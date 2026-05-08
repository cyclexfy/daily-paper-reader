---
title: "multiVIB: A unified probabilistic contrastive learning framework for atlas-scale integration of single-cell multi-omics data"
authors: "Xu, Y., Fleming, S. J., Wang, B., Schoenbeck, E. G., Babadi, M., Huo, B.-X."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.29.691308v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 用于多组学数据整合的概率对比学习框架
tldr: 随着单细胞技术的发展，构建大规模脑细胞图谱需要整合跨平台、跨物种和跨模态的异构数据。本文提出multiVIB，一个统一的概率对比学习框架，旨在解决现有工具适用范围窄且易产生伪影的问题。该方法在保持生物学差异的同时实现了高效的数据对齐，在BRAIN Initiative等大规模数据集上表现优异，为构建下一代单细胞多组学图谱提供了可扩展且忠实于生物学特征的解决方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的单细胞数据整合工具通常仅适用于特定场景，且在处理异构数据时容易产生伪影或抹除生物学差异。
method: 提出了一种名为multiVIB的统一概率对比学习框架，能够处理多种整合场景并缓解错误对齐。
result: multiVIB在BRAIN Initiative的大规模数据集上实现了最先进的性能，并能可靠地保留跨物种整合中的物种特异性差异。
conclusion: multiVIB作为一个可扩展且生物学保真的基础框架，为构建下一代大规模脑细胞图谱提供了强有力的支持。
---

## Abstract
Comprehensive brain cell atlases are essential for understanding neural functions and enabling translational insights. As single-cell technologies proliferate across experimental platforms, species, and modalities, these atlases must scale accordingly, calling for data integration framework that aligns heterogeneous datasets without erasing biologically meaningful variations. Existing tools typically address narrow integration settings, forcing researchers to assemble \textit{ad hoc} workflows that may generate artifacts. Here, we introduce multiVIB, a unified probabilistic contrastive learning framework that handles diverse integration scenarios. We show that multiVIB achieves state-of-the-art performance while mitigating spurious alignments. Applied to atlas-scale datasets from the BRAIN Initiative, multiVIB demonstrates robust and scalable integration, including integration of diverse data modalities and reliable preservation of species-specific variations in cross-species integration. These capabilities position multiVIB as a scalable, biologically faithful foundation for constructing next-generation brain cell atlases with the growing landscape of single-cell data.