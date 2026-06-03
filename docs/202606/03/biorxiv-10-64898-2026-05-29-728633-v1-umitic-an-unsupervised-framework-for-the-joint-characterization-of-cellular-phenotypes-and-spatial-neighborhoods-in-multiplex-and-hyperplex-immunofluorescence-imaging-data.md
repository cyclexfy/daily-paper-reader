---
title: "UMITIC: An unsupervised framework for the joint characterization of cellular phenotypes and spatial neighborhoods in multiplex and hyperplex immunofluorescence imaging data"
title_zh: UMITIC：一种用于多重和超多重免疫荧光成像数据中细胞表型和空间邻域联合表征的无监督框架
authors: "Sangüesa Recalde, M., De Andrea, C. E., Ariz, M."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728633v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 无监督多重成像空间表征框架
tldr: 多重免疫荧光成像数据虽能同时测量数十种蛋白标志物，但缺乏注释时难以挖掘生物学意义。UMITIC框架通过CellCut优化细胞分割，CellMap使用对比学习提取形态学特征，TissueNet构建图神经网络建模细胞间空间关系，从而实现无监督的细胞表型和组织邻域联合表征。在7-plex、43-plex、58-plex及专家标注数据集上，UMITIC准确重建了免疫细胞组成和空间结构，与现有方法相比与专家标注一致性更高。该工作为超多重成像数据的自动化分析提供了可扩展的通用工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 多重成像数据缺乏无监督分析方法，手动注释耗时且难以扩展到高维数据。
method: UMITIC集成CellCut（细胞分割）、CellMap（对比学习提取形态特征）和TissueNet（图神经网络建模细胞交互）三个模块。
result: 在7-plex至58-plex数据集上，UMITIC准确识别细胞亚群和组织微环境，与专家标注一致性优于现有方法。
conclusion: UMITIC为无监督分析超多重成像数据提供鲁棒且可解释的方案，无需人工标注。
---

## 摘要
多重成像技术能够在保留组织结构背景的同时同时测量数十种蛋白标志物，从而提供组织结构方案的高分辨率视图。然而，从这些高维数据集中提取有意义的见解——尤其是在超多重设置（>20个标志物）下——仍然是一个主要的计算挑战，尤其是在缺乏标注数据的情况下。在此，我们提出UMITIC（通过组织特征进行多重图像的无监督分析），一个模块化的无监督计算框架，用于从多重成像数据中联合表征细胞表型和组织邻域。UMITIC整合了三个组件：(i) CellCut，一种结合核和细胞质预测以改善框架描绘能力的策略；(ii) CellMap，一种对比学习方法，用于生成富含形态学特征的单细胞图像裁剪的低维表示；(iii) TissueNet，一种图神经网络，用于建模空间细胞-细胞相互作用以识别组织邻域。我们在四个复杂度递增的数据集上评估了UMITIC，以评估其鲁棒性、可扩展性和生物学相关性。针对一个7重人体扁桃体数据集，该框架识别了典型的免疫细胞群体并重构了已建立的解剖区域。当应用于一个43重扁桃体图像时，UMITIC保留了这些组织级结构，同时通过增加的标志物维度实现了更精细的细胞亚型分层过程。我们进一步在一个58重结直肠癌队列中验证了我们的方法，UMITIC能够恢复先前报道的不同预后患者组之间的免疫组成差异和空间组织变化。最后，当使用一个关于人体肺组织的专家注释质量细胞计数成像数据集时，UMITIC比现有方法实现了与参考组织注释更高的一致性，展示了改进的肺微解剖结构重建准确性。总之，这些结果表明UMITIC能够在无需手动注释的情况下，对多种多重和超多重成像数据集中的细胞表型和组织结构进行一致且可解释的分析。

## Abstract
Multiplexed imaging technologies enable the simultaneous measurement of dozens of protein markers while preserving context, providing a high-resolution view of tissue organization schemes. However, extracting meaningful insights from these high-dimensional datasets--particularly in hyperplex settings (>20 markers)--remains a major computational challenge, especially in the absence of annotated data. Here, we present UMITIC (Unsupervised Analysis of Multiplex Images via TIssue Characterization), a modular and unsupervised computational framework for the joint characterization of cell phenotypes and tissue neighborhoods from multiplex imaging data. UMITIC integrates three components: (i) CellCut, a strategy that combines nuclear and cytoplasmic predictions to improve the delineation capabilities of the framework; (ii) CellMap, a contrastive learning approach that generates low-dimensional representations of single-cell image crops that are enriched with morphological features; and (iii) TissueNet, a graph neural network that models spatial cell-cell interactions to identify tissue neighborhoods. We evaluated UMITIC across four datasets of increasing complexity to assess its robustness, scalability and biological relevance. With respect to a 7-plex human tonsil dataset, the framework identified canonical immune cell populations and reconstructed well-established anatomical regions. When applied to a 43-plex tonsil image, UMITIC preserved these tissue-level structures while enabling a finer cell subtype stratification process driven by increased marker dimensionality. We further validated our method on a 58-plex colorectal cancer cohort, where UMITIC was able to recover previously reported immune composition differences and spatial organization variations between patient groups with different prognoses. Finally, when an expert-annotated mass cytometry imaging dataset concerning human lung tissue was used, UMITIC achieved higher agreement with the reference tissue annotations than the existing approaches did, demonstrating improved lung microanatomy reconstruction accuracy. Together, these results show that UMITIC enables consistent and interpretable analyses of both cellular phenotypes and tissue architectures across diverse multiplex and hyperplex imaging datasets without the need for manual annotations.