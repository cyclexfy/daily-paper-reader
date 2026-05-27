---
title: "Label-Free Multimodal Volumetric Imaging of Colon Cancer Tissue via Registration of Propagation-Based Phase-Contrast CT, Light-Sheet, and Three-Photon Microscopy"
title_zh: 基于传播相位对比CT、光片显微镜和三光子显微镜配准的无标记多模态体积成像结肠癌组织
authors: "Dullin, C., Schroeter, M., Pinkert-Leetsch, D., Ramos-Gomes, F., Markus, A., Missbach-Guentner, J., Bohnenberger, H., Stroebel, P., Alves, F."
date: 2026-05-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.726767v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 结肠癌组织的多模态体积成像
tldr: 本研究针对结肠癌FFPE样本，提出一种配准传播相位对比CT、光片显微镜和三光子显微镜三种无标记三维成像模态的流程。通过三级级联配准策略（粗全局对齐、刚性精炼、互信息相似度）实现空间对齐，并利用六维特征空间的高斯混合模型进行无监督组织分类，生成一致的多通道三维数据集，为全面分析组织架构提供新途径。
source: biorxiv
selection_source: fresh_fetch
motivation: 整合相位对比CT、光片显微镜和三光子显微镜的互补信息，以无标记方式全面研究结肠癌组织三维结构。
method: 采用三级级联配准，先对降采样数据粗对齐，再中等分辨率刚性精炼，以互信息为相似度，对齐PCT、LSM和3PM图像。
result: 成功生成空间对齐的多模态三维数据，并利用六维特征空间通过GMM实现无监督组织分类，识别出生物意义区域。
conclusion: 该配准与聚类框架实现了无标记三维组织分析，但需进一步优化并在更大数据集验证以提升效率与适用性。
---

## 摘要
多模态三维成像已成为研究病理标本复杂组织架构的有力方法。传播相位对比计算机断层扫描（PCT）、光片显微镜（LSM）和三光子显微镜（3PM）等技术基于不同的固有对比机制，提供未标记组织形态的互补信息。然而，由于成像几何、空间分辨率和模态特定畸变的差异，将这些异构数据集整合到统一的空间框架中仍具挑战性。本研究提出了一种配准流程，用于空间对齐从福尔马林固定石蜡包埋（FFPE）人结肠癌标本中获取的PCT、LSM和3PM体积数据集。这些标本的活检组织经过光学透明化处理，并使用三种高分辨率模态依次成像。为补偿采集之间的较大位置差异，开发了一种三级级联配准策略，包括在降采样数据上进行粗略全局对齐，随后在中间分辨率上进行刚性细化。采用互信息作为相似性度量，以确保稳健的多模态配准。所生成的框架能够产生空间对齐的多通道三维数据集，将X射线相位对比成像的结构信息与互补的光学对比信号相结合。除了配准，我们还展示了融合的六维特征空间可进一步用于基于高斯混合模型（GMM）的无监督组织表征，从而无需手动注释即可实现数据驱动的空间一致组织区域识别。定性评估证实了主要解剖结构在模态间的一致对齐，而无监督聚类揭示了尽管存在模态特定噪声和分辨率差异，仍具有生物学意义的模式。尽管需要在更大数据集上进行进一步优化和验证以提高计算效率和适用范围，但该方法已展现出全面组织分析的强大潜力，并实现了结肠癌组织架构的可扩展、无标记三维表征。

## Abstract
Multimodal 3D imaging has emerged as a powerful approach for investigating complex tissue architecture in pathological specimens. Techniques such as propagation-based phase-contrast computed tomography (PCT), light-sheet microscopy (LSM), and three-photon microscopy (3PM) provide complementary information on unlabeled tissue morphology based on distinct intrinsic contrast mechanisms. However, integrating these heterogeneous datasets into a unified spatial framework remains challenging due to differences in imaging geometry, spatial resolution, and modality-specific distortions. In this study, we present a registration pipeline for spatially aligning volumetric datasets acquired with PCT, LSM, and 3PM from formalin-fixed paraffin-embedded (FFPE) human colon cancer specimens. Biopsies from theses specimens were optically cleared and imaged sequentially using the three high-resolution modalities. To compensate for large positional differences between acquisitions, a three-stage cascade registration strategy was developed, consisting of coarse global alignment on down-sampled data, followed by rigid refinement at intermediate resolution. Mutual information was used as the similarity metric to ensure robust multimodal registration. The resulting framework enables the generation of spatially aligned multi-channel 3D datasets that combine structural information from X-ray phase-contrast imaging with complementary optical contrast signals. Beyond registration, we demonstrate that the fused six-dimensional feature space can be further exploited for unsupervised tissue characterization using a Gaussian Mixture Model (GMM), enabling data-driven identification of spatially coherent tissue regions without manual annotation. Qualitative evaluation confirms consistent alignment of major anatomical structures across modalities, while the unsupervised clustering reveals biologically meaningful patterns despite modality-specific noise and resolution differences. While further optimization and validation across larger datasets will enhance its computational efficiency and breadth of application, the approach already demonstrates strong potential for comprehensive tissue analysis and enables scalable, label-free 3D characterization of colon cancer tissue architecture.