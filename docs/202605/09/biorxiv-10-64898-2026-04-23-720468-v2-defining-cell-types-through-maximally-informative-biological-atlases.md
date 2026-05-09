---
title: Defining Cell Types through Maximally Informative Biological Atlases
title_zh: 通过最大信息量生物图谱定义细胞类型
authors: "Wollman, R."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.23.720468v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 将分子图谱映射到空间地图的信息论框架
tldr: 本研究针对细胞类型定义缺乏理论基础的问题，提出了一个基于信息论的框架，通过最大化空间信息量来构建生物图谱。该方法通过平衡细胞类型编码的熵与空间分布的熵，确定最优的分类体系，并能扩展至组织区域划分。在小鼠全脑空间转录组数据上的应用证明，该框架能有效识别兼具编码复杂性与空间信息量的细胞类型和区域分类，为基于组织空间结构的图谱构建奠定了理论基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的细胞类型定义缺乏统一的理论框架，难以在压缩高维分子数据的同时准确反映其空间组织规律。
method: 提出一种信息论框架，通过平衡细胞类型编码熵与空间熵，寻找能最大化空间信息含量的最优分类体系。
result: 在小鼠全脑空间转录组数据集上成功识别出在编码复杂度和空间信息量之间达到平衡的最优细胞类型及区域分类。
conclusion: 该研究为基于组织空间架构的细胞类型定义和区域图谱构建提供了一个统一且科学的信息论基础。
---

## 摘要
细胞类型图谱通过将高维分子谱压缩为可在组织间映射的离散细胞类型，从而组织生物学的复杂性。然而，关于什么构成细胞类型的原则性理论仍然缺乏。在这里，我引入了一个信息论框架，其中分子定义的细胞类型分类通过其产生的空间图谱的信息含量进行评估。最优分类法通过平衡细胞类型编码的熵与所得图谱的空间熵，从而实现空间信息的最大化。该框架可自然地推广到更高阶的空间划分，包括由局部细胞组成定义的组织区域。应用于小鼠全脑空间转录组数据集，该方法识别出平衡了编码复杂性与空间信息量的最优细胞类型和区域级分类法。总之，这些结果为基于组织空间结构的细胞类型和区域级图谱构建建立了统一的信息论基础。

## Abstract
Cell type atlases organize biological complexity by compressing high-dimensional molecular profiles into discrete cell types that can be mapped across tissues. Yet a principled theory of what constitutes a cell type remains lacking. Here, I introduce an information-theoretic framework in which molecularly defined cell type classifications are evaluated by the information content of the spatial maps they produce. The optimal taxonomy maximizes spatial information by balancing the entropy of the cell type code against the spatial entropy of the resulting map. The framework generalizes naturally to higher-order spatial partitions, including tissue regions defined by local cellular composition. Applied to a whole-brain mouse spatial transcriptomic dataset, this approach identifies optimal cell-type and region-level taxonomies that balance coding complexity with spatial informativeness. Together, these results establish a unified information-theoretic foundation for cell-type and region-level atlas construction grounded in tissue spatial architecture.