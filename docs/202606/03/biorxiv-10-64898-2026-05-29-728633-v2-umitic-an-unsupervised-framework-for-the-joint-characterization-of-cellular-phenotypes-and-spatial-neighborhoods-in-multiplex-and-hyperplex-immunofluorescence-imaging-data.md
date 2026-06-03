---
title: "UMITIC: An unsupervised framework for the joint characterization of cellular phenotypes and spatial neighborhoods in multiplex and hyperplex immunofluorescence imaging data"
title_zh: UMITIC：一个用于多重和超多重免疫荧光成像数据中细胞表型和空间邻域联合表征的无监督框架
authors: "Sangüesa Recalde, M., De Andrea, C. E., Ariz, M."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728633v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 用于多重成像中细胞表型和空间邻域表征的无监督框架
tldr: 多重成像技术可同时检测数十种蛋白标志物，但高维数据分析缺乏人工注释面临挑战。UMITIC是一种无监督框架，通过CellCut细胞分割、CellMap对比学习降维和TissueNet图神经网络，联合表征细胞表型与空间邻域。在7-plex扁桃体数据中识别典型免疫细胞和区域，43-plex中实现更精细分型，58-plex结直肠癌中恢复预后组间差异，肺数据重构精度优于现有方法。无需手动标注即可实现跨数据集的鲁棒、可解释分析。
source: biorxiv
selection_source: fresh_fetch
motivation: 高维多重成像数据缺乏注释，现有方法难以同时有效表征细胞表型和组织空间结构。
method: UMITIC整合CellCut改进细胞分割，CellMap通过对比学习提取形态特征，TissueNet用图神经网络建模细胞空间交互。
result: 在7-plex至58-plex数据集上验证，准确识别免疫细胞和区域，结直肠癌中区分预后组，肺数据重构精度优于现有方法。
conclusion: UMITIC提供无监督模块化方案，可一致分析多种多重成像数据中的细胞表型和组织微环境。
---

## 摘要
多重成像技术能够在保留组织上下文的同时同时测量数十种蛋白标志物，提供组织组织结构的高分辨率视图。然而，从这些高维数据中提取有意义的见解——尤其是在超多重设置（>20种标志物）下——仍然是一个重大的计算挑战，尤其是在缺乏标注数据的情况下。本文提出了UMITIC（通过组织表征进行多重图像的无监督分析），一个模块化的无监督计算框架，用于从多重成像数据中联合表征细胞表型和组织邻域。UMITIC集成了三个组件：(i) CellCut，一种结合细胞核和细胞质预测以改善框架描绘能力的策略；(ii) CellMap，一种对比学习方法，生成富含形态学特征的单细胞图像切片的低维表示；(iii) TissueNet，一种图神经网络，用于建模空间细胞-细胞相互作用以识别组织邻域。我们在四个复杂度递增的数据集上评估了UMITIC，以测试其鲁棒性、可扩展性和生物学相关性。对于7重人类扁桃体数据集，该框架识别了典型的免疫细胞群体并重建了已建立的解剖区域。当应用于43重扁桃体图像时，UMITIC保留了这些组织级别的结构，同时通过增加标志物维度实现了更精细的细胞亚型分层过程。我们进一步在58重结直肠癌队列中验证了该方法，UMITIC能够恢复先前报道的不同预后患者组之间的免疫组成差异和空间组织变化。最后，当使用专家标注的关于人类肺组织的质谱流式成像数据集时，UMITIC与参考组织标注的一致性高于现有方法，显示了改进的肺微解剖重建准确性。这些结果共同表明，UMITIC能够在多种多重和超多重成像数据集上实现一致且可解释的细胞表型和组织结构分析，而无需手动标注。

## Abstract
Multiplexed imaging technologies enable the simultaneous measurement of dozens of protein markers while preserving context, providing a high-resolution view of tissue organization schemes. However, extracting meaningful insights from these high-dimensional datasets--particularly in hyperplex settings (>20 markers)--remains a major computational challenge, especially in the absence of annotated data. Here, we present UMITIC (Unsupervised Analysis of Multiplex Images via TIssue Characterization), a modular and unsupervised computational framework for the joint characterization of cell phenotypes and tissue neighborhoods from multiplex imaging data. UMITIC integrates three components: (i) CellCut, a strategy that combines nuclear and cytoplasmic predictions to improve the delineation capabilities of the framework; (ii) CellMap, a contrastive learning approach that generates low-dimensional representations of single-cell image crops that are enriched with morphological features; and (iii) TissueNet, a graph neural network that models spatial cell-cell interactions to identify tissue neighborhoods. We evaluated UMITIC across four datasets of increasing complexity to assess its robustness, scalability and biological relevance. With respect to a 7-plex human tonsil dataset, the framework identified canonical immune cell populations and reconstructed well-established anatomical regions. When applied to a 43-plex tonsil image, UMITIC preserved these tissue-level structures while enabling a finer cell subtype stratification process driven by increased marker dimensionality. We further validated our method on a 58-plex colorectal cancer cohort, where UMITIC was able to recover previously reported immune composition differences and spatial organization variations between patient groups with different prognoses. Finally, when an expert-annotated mass cytometry imaging dataset concerning human lung tissue was used, UMITIC achieved higher agreement with the reference tissue annotations than the existing approaches did, demonstrating improved lung microanatomy reconstruction accuracy. Together, these results show that UMITIC enables consistent and interpretable analyses of both cellular phenotypes and tissue architectures across diverse multiplex and hyperplex imaging datasets without the need for manual annotations.