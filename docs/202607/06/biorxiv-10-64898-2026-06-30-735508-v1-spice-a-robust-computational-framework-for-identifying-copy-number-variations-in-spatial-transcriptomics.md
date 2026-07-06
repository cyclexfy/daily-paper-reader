---
title: "SPICE: A Robust Computational Framework for Identifying Copy Number Variations in Spatial Transcriptomics"
title_zh: "SPICE: 一种用于识别空间转录组学中拷贝数变异的稳健计算框架"
authors: "Banerjee, K., Langefeld, R. C., Keller, E. T., Zhou, X."
date: 2026-07-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.30.735508v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 用于空间转录组数据中拷贝数变异识别的概率方法，应用于癌症
tldr: 拷贝数变异驱动肿瘤异质性，空间转录组技术为解析其空间分布提供了机遇。SPICE是一种概率方法，整合基因表达、空间坐标和转录组SNP信息，识别体细胞CNV和等位基因特异性拷贝数。在多个平台数据中验证了SNP可靠性，实现了准确、空间一致的CNV重构和亚克隆分析。该方法为空间转录组研究基因组异质性提供了鲁棒有效的解决方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法在空间转录组数据中CNV检测精度有限，需整合基因表达、空间坐标和SNP多种信息以提高准确性和空间一致性。
method: SPICE采用概率模型，联合利用基因表达、空间坐标和转录组杂合SNP，推断体细胞CNV和等位基因特异性拷贝数。
result: 在不同空间转录组平台上验证了SNP可靠性，成功实现准确且空间连贯的CNV景观重构，并有效控制假阳性。
conclusion: SPICE为分析癌症空间转录组中的基因组异质性提供了鲁棒且有效的工具。
---

## 摘要
拷贝数变异（CNV）改变基因组片段的数量，是肿瘤内异质性的主要驱动因素，其特征是空间上组织且遗传上不同的细胞群体。空间分辨转录组学（SRT）技术的最新进展能够在数千个空间索引的组织位置上分析基因表达，为重建CNV结构和剖析癌症亚克隆的空间组织提供了强大机会。在这里，我们介绍SPICE（空间推断CNV事件），一种从SRT数据中识别体细胞CNV和等位基因特异性拷贝数（ASCN）图谱的概率方法。SPICE的一个关键特性是其整合SRT数据中多种互补信息的能力，包括基因表达、空间坐标和从转录组读段推断的杂合SNP，以显著提高CNV检测的准确性和效力。使用不同SRT平台生成的数据集，我们首先评估从SRT数据衍生的SNP的可靠性，以确保稳健的下游推断。然后我们证明SPICE有效地整合这些模态，以提供准确且空间一致的CNV景观和亚克隆结构重建，同时保持对错误发现的出色控制。总之，SPICE为在癌症SRT研究中解析基因组异质性提供了稳健且有效的解决方案。

## Abstract
Copy number variation (CNV), which alters the number of genomic segments, is a major driver of intratumor heterogeneity, characterized by spatially organized and genetically distinct cell populations. Recent advances in spatially resolved transcriptomic (SRT) technologies, which profile gene expression across thousands of spatially indexed tissue locations, offer a powerful opportunity to reconstruct the CNV architecture and dissect the spatial organization of cancer subclones. Here, we introduce SPICE (spatial inference of CNV events), a probabilistic method for identifying somatic CNVs and allele-specific copy number (ASCN) profiles from SRT data. A key feature of SPICE is its ability to integrate multiple complementary information available in SRT data, including gene expression, spatial coordinates, and heterozygous SNPs inferred from transcriptomic reads, to substantially enhance the accuracy and power of CNV detection. Using datasets generated across different SRT platforms, we first assess the reliability of SNPs derived from SRT data to ensure robust downstream inference. We then demonstrate that SPICE effectively integrates these modalities to deliver accurate and spatially coherent reconstruction of CNV landscapes and subclonal architecture, while maintaining excellent control of false discoveries. Together, SPICE provides a robust and effective solution for dissecting genomic heterogeneity in SRT studies of cancer.