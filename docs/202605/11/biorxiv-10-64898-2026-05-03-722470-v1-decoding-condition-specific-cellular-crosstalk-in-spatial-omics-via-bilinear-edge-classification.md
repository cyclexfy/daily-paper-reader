---
title: Decoding Condition-Specific Cellular Crosstalk in Spatial Omics via Bilinear Edge Classification
title_zh: 通过双线性边分类解码空间组学中特定条件下的细胞串扰
authors: "Karin, J., Friedman, R., Nitzan, M."
date: 2026-05-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.03.722470v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 疾病进展中细胞通讯和空间组学的计算分析
tldr: 组织功能源于细胞空间配置及其交互，但在疾病或衰老过程中，这种空间结构常发生重组。现有工具多侧重于单细胞分析，忽略了邻近细胞间的协调变化。本文提出 CO_SCPLOWASEIC_SCPLOW 框架，通过双线性边缘分类直接建模空间组学中的条件特异性细胞交互。该方法将“边”作为推理单元，能有效识别与特定条件相关的多细胞交互模式和空间表达程序，为理解组织结构演变提供了新工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统空间转录组分析侧重于单细胞或离散标签，无法有效检测不同生物条件下邻近细胞间协调的转录变化。
method: 开发了名为 CO_SCPLOWASEIC_SCPLOW 的双线性分类框架，在细胞邻近图上通过建模基因间的协调关系来识别条件特异性的细胞交互。
result: 在肝纤维化、动脉粥样硬化和大脑衰老等应用中，该方法揭示了如内皮-巨噬细胞网络转变和肝细胞分区破坏等具有生物学意义的空间重组。
conclusion: 该研究证明了以交互（边）为中心的建模方式在揭示多细胞功能丧失和组织结构变化方面的优越性。
---

## 摘要
组织是由多细胞构成的结构化群落，其功能源于个体细胞特征与其相应空间配置的结合，这影响了它们的相互作用和响应模式。在疾病进展或衰老等过程中，组织会经历结构重组，包括不同细胞类型共定位的变化、功能性微环境（niches）的组装或破坏，以及细胞间通讯轴的紊乱。这些变化可能主要表现为细胞的空间重组，而非单个细胞的转录状态。尽管空间转录组学的计算工具在表征组织架构方面取得了显著进展，但大多数用于表征不同生物条件下组织状态变化的方法都运行在单个细胞层面，或依赖于离散的细胞类型标签，从而限制了检测邻近细胞之间协调转录变化的能力，而这些变化正是区分不同条件的关键。我们提出了 CO_SCPLOWASEIC_SCPLOW，这是一个运行在细胞邻近图上的双线性分类框架，它通过将相互作用（边）而非细胞（节点）作为生物推理的基本单元，直接建模空间组学数据中特定条件下的细胞-细胞相互作用。为了捕捉此类特定条件下的信号，我们利用了一个模型，其归纳偏置通过邻近细胞的协调基因-基因关系与细胞相互作用保持一致。CO_SCPLOWASEIC_SCPLOW 能够发现与条件相关的多细胞相互作用和空间表达程序，并表征多细胞功能和结构的丧失。应用于哺乳动物肝纤维化、动脉粥样硬化和大脑衰老，CO_SCPLOWASEIC_SCPLOW 揭示了具有生物学意义的空间重组，包括动脉粥样硬化斑块中从内皮细胞主导向巨噬细胞主导网络的转变、纤维化中肝细胞分区的破坏，以及衰老白质中少突胶质细胞与小胶质细胞的串扰。

## Abstract
Tissues are multicellular structured communities whose function emerges from a combination of individual cellular characteristics along with their corresponding spatial configuration, affecting their interactions and response patterns. During processes such as disease progression or aging, tissues can undergo structural reorganization, including changes in co-localization of different cell types, assembly or destruction of functional niches, and disruption of intercellular communication axes. Such changes can manifest primarily in the spatial reorganization of cells rather than in the transcriptional states of individual cells. While computational tools for spatial transcriptomics have made significant progress in characterizing tissue architecture, most approaches for characterizing changes in tissue states across biological conditions operate at the level of individual cells or rely on discrete cell type labels, thus limiting the ability to detect coordinated transcriptional changes between neighboring cells that distinguish one condition from another. We present CO_SCPLOWASEIC_SCPLOW, a bilinear classification framework operating on cellular proximity graphs, which directly models condition-specific cell-cell interactions in spatial omics data by focusing on interactions (edges), rather than cells (nodes), as the fundamental unit of biological inference. To capture such condition-specific signals, we leverage a model whose inductive bias aligns with cellular interactions through coordinated gene-gene relationships of neighboring cells. CO_SCPLOWASEIC_SCPLOW enables the discovery of condition-associated multicellular interactions and spatial expression programs, and characterizes the loss of multicellular function and structure. Applied to mammalian liver fibrosis, atherosclerosis, and brain aging, CO_SCPLOWASEIC_SCPLOW reveals biologically meaningful spatial reorganization, including the shift from endothelial-to macrophage-dominated networks in atherosclerotic plaques, disruption of hepatocyte zonation in fibrosis, and oligodendrocyte-microglia crosstalk in aging white matter.