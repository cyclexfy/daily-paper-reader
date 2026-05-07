---
title: "Spartan: activation-aware framework for spatial domain and variable gene discovery"
title_zh: Spartan：一种用于空间域和可变基因发现的激活感知框架
authors: "Faiz, M. F. I., Jokl, E., Jennings, R., Piper Hanley, K., Sharrocks, A., Iqbal, M., Baker, S. M."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.18.706570v2.full.pdf"
tags: ["query:cpath"]
score: 6.5
evidence: 组织结构空间域发现的计算框架
tldr: 针对空间转录组学中现有聚类方法易模糊解剖边界和忽略局部微结构的问题，本文提出Spartan框架。该框架通过引入局部空间激活（LSA）信号捕捉转录异质性，并结合空间拓扑构建多重图模型。Spartan在多种技术平台上实现了高分辨率的空间域识别和空间差异基因检测，具有良好的可解释性和线性扩展性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的空间聚类方法往往会模糊解剖边界或合并过渡区，难以准确识别高分辨率下的局部微结构。
method: 提出一种激活感知的多重图框架，通过整合空间拓扑与局部空间激活（LSA）信号来捕捉邻域内的转录偏差。
result: 在Visium HD、MERFISH等多种平台上成功恢复了精确的解剖分区，并能稳定识别复杂的过渡区域及空间变量基因。
conclusion: Spartan为高分辨率空间系统分析提供了一个鲁棒、可扩展且具有生物学解释力的计算框架。
---

## 摘要
空间转录组学正迅速向单细胞水平分辨率迈进，揭示了跨越连续解剖梯度的复杂组织结构。然而，准确识别空间域仍然是一个核心计算挑战，因为许多现有的聚类方法会模糊解剖边界、合并过渡区，或无法解析局部微结构。在这里，我们介绍了 Spartan，这是一个用于高分辨率空间域发现的激活感知多重图框架。Spartan 整合了空间拓扑和局部空间激活（LSA），这是一种邻域偏差信号，能够捕捉通常被基于相似性的聚类所削弱的局部转录异质性。通过对域内内聚性和局部激活结构进行联合建模，Spartan 在包括 Visium HD、MERFISH、Stereo-seq 和 STARmap 在内的多种空间分辨率转录组技术中恢复了与解剖结构一致的分区。我们进一步在发育中的人类食道和胃的高分辨率 Visium HD 切片中展示了其效用，其中激活感知图集成能够精确描绘复杂的过渡区域（如胃食管结合部），并支持稳定的多尺度空间域恢复，而无需脆弱的超参数调整。除了空间域识别，Spartan 还利用激活感知结构来检测与局部组织重塑相关的空间可变基因。Spartan 的计算规模随数据集大小近线性增长，为空间系统级分析提供了一个稳健且可解释的框架。

## Abstract
Spatial transcriptomics is rapidly advancing toward single-cell-level resolution, revealing complex tissue architectures organized across continuous anatomical gradients. However, accurate identification of spatial domains remains a central computational challenge, as many existing clustering approaches blur anatomical boundaries, merge transitional zones, or fail to resolve localized microstructures. Here we introduce Spartan, an activation-aware multiplex graph framework for high-resolution domain discovery. Spartan integrates spatial topology and Local Spatial Activation (LSA), a neighborhood deviation signal that captures localized transcriptional heterogeneity often attenuated by similarity-based clustering. By jointly modeling cohesion within domains and localized activation structure, Spartan recovers anatomically aligned partitions across spatially resolved transcriptomics technologies including Visium HD, MERFISH, Stereo-seq, and STARmap. We further demonstrate its utility in a high-resolution Visium HD section of developing human esophagus and stomach, where activation-aware graph integration enables precise delineation of complex transitional regions such as the gastroesophageal junction and supports stable multi-scale domain recovery without fragile hyperparameter tuning. Beyond domain identification, Spartan leverages activation-aware structure to detect spatially variable genes associated with localized tissue remodeling. Spartan scales near-linearly with dataset size, providing a robust and interpretable framework for spatial systems-level analysis.