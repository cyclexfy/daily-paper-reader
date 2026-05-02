---
title: "SpatialQuery: scalable discovery and molecular characterization of multicellular motifs from spatial omics data"
title_zh: SpatialQuery：从空间组学数据中实现多细胞基序的可扩展发现与分子表征
authors: "Hemberg, M., An, S., Gehlenborg, N., Keller, M."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.22.720136v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 空间组学数据的分子表征
tldr: SpatialQuery是一个用于空间组学数据分析的框架，旨在高效识别多细胞空间基序（motifs）并表征其分子特征。它通过差异表达和协变分析揭示受空间背景调控的基因，支持从转录组到蛋白质组的多尺度数据。该工具不仅能识别功能性组织单元，还能超越成对相互作用来分析复杂的多细胞环境，为理解组织发育和疾病微环境提供了可扩展的计算方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的空间单细胞技术缺乏能同时发现多细胞空间模式并表征其分子程序的计算方法。
method: 提出了SpatialQuery框架，通过识别重复出现的多细胞共定位基序，并结合差异表达和协变分析来进行分子表征。
result: 在肠道发育、肾脏和结肠疾病以及小鼠大脑图谱的应用中，成功揭示了跨胚层信号传导、疾病特异性纤维化生态位及区域性转录程序。
conclusion: SpatialQuery是一个高效且可扩展的工具，能够深入解析复杂组织中的多细胞相互作用，并可集成至Web门户进行交互式探索。
---

## 摘要
空间分辨率单细胞技术实现了细胞的原位分析，但能够同时发现多细胞空间模式并表征其分子程序的计算方法仍然有限。在此，我们介绍了 SpatialQuery，这是一个既能识别细胞基序（即重复出现的多细胞共定位模式），又能针对这些基序进行分子分析的框架。它通过差异表达分析揭示受空间背景调节的基因，并通过共变分析检测协调的表达变化。SpatialQuery 可以识别功能性组织单元，并超越成对分析来表征多细胞相互作用。在空间转录组学和蛋白质组学数据中的应用揭示了肠管模式形成中的跨胚层信号传导、肾脏和结肠中疾病特异性的纤维化和免疫抑制生态位，以及小鼠大脑图谱中基序相关转录程序的区域决定因素。SpatialQuery 以 Python 包的形式提供，我们展示了其轻量级的计算占用如何使其能够集成到基于 Web 的细胞图谱门户中，以进行交互式可视化和探索。

## Abstract
Spatially resolved single-cell technologies enable profiling of cells in situ, yet computational approaches that jointly discover multicellular spatial patterns and characterize their molecular programs remain limited. Here we introduce SpatialQuery, a framework that can both identify cellular motifs, i.e. recurrent multicellular co-localization patterns, and perform molecular analyses focused on the motifs. It uncovers genes modulated by spatial contexts through differential expression analysis, and detects coordinated expression changes through covariation analysis. SpatialQuery can identify functional tissue units, and goes beyond pairwise analyses to characterize multicellular interactions. Applications to both spatial transcriptomics and proteomics data uncover cross-germ-layer signaling in gut tube patterning, disease-specific fibrotic and immunosuppressive niches in kidney and colon, and regional determinants of motif-associated transcriptional programs in a mouse brain atlas. SpatialQuery is available as a Python package, and we demonstrate how its light computational footprint enables integration into web-based cell atlas portals for interactive visualization and exploration.