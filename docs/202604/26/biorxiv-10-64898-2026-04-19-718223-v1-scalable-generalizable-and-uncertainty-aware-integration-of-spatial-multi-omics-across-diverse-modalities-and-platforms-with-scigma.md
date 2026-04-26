---
title: "Scalable, Generalizable, and Uncertainty-Aware Integration of Spatial Multi-Omics Across Diverse Modalities and Platforms with SCIGMA"
title_zh: 利用 SCIGMA 实现跨多样化模态与平台的可扩展、可泛化且具有不确定性感知能力的空间多组学整合
authors: "Chang, S., Fleischmann, A., Ma, Y."
date: 2026-04-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.19.718223v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 整合包括成像和转录组数据在内的空间多模态数据集
tldr: 随着空间组学技术的发展，整合大规模、多模态（如转录组、蛋白质组等）数据成为挑战。本文提出SCIGMA，一种可扩展且通用的深度学习框架。它利用不确定性感知对比学习和多视图图神经网络，在保留模态特异信号的同时学习联合表示。SCIGMA支持多达五种模态的整合，并能处理百万级空间位点，在空间域检测和特征重建等方面表现优异，为复杂组织分析提供了稳健的解决方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决现有方法在整合大规模、异构且多模态的空间组学数据时面临的可扩展性、通用性及解释性不足的问题。
method: 提出了一种结合不确定性感知对比学习目标和多视图图神经网络的深度学习框架，以实现跨模态的联合表示学习并提供空间不确定性估计。
result: 在19个数据集上的评估显示，SCIGMA在空间域检测和特征重建等方面超越了现有方法，并成功处理了超过一百万个空间位点的大规模数据。
conclusion: SCIGMA为空间多组学整合提供了一个灵活、可扩展且具备不确定性评估能力的工具，有助于深入揭示组织的生物学复杂性。
---

## 摘要
空间组学技术的最新进展使得在高空间分辨率下同时分析转录组、蛋白质组、表观基因组、代谢组和成像数据成为可能，为剖析组织复杂性提供了前所未有的机遇。然而，整合这些多样化且大规模的空间多模态数据集仍然是一项重大的计算挑战。我们提出了 SCIGMA，这是一个用于空间多组学整合的可扩展且可泛化的深度学习框架。SCIGMA 引入了一种新颖的不确定性感知对比学习目标和多视图图神经网络，在学习具有生物学意义的联合表示的同时，保留了模态特异性信号。与现有方法不同，SCIGMA 提供空间分辨的不确定性估计，提高了可解释性，并能识别具有生物学或技术异质性的区域。SCIGMA 是首个支持多达五种模态整合的空间多组学方法（已在 Spatial-Mux-Seq 数据上得到验证），其模块化框架可扩展到未来具有更多模态的技术。它还可以扩展到超过一百万个空间位置，从而能够分析 VisiumHD 和 Xenium Prime 等超高分辨率数据集。我们在涵盖 8 种模态、10 种组织和 9 个平台的 19 个数据集上对 SCIGMA 进行了评估。在可基准测试的数据集上，SCIGMA 在空间域检测、模态保留、特征重建和可重复性方面均优于现有方法。在各项应用中，它揭示了具有生物学意义的结构、精细的空间域以及模态特异性的调节程序，同时其不确定性估计揭示了具有潜在生物学或技术变异的组织区域。总之，SCIGMA 为可扩展的空间多模态整合提供了一个稳健、灵活且面向未来的解决方案。

## Abstract
Recent advances in spatial omics technologies have enabled simultaneous profiling of transcriptomic, proteomic, epigenomic, metabolomic, and imaging data at high spatial resolution, offering unprecedented opportunities to dissect tissue complexity. However, integrating these diverse and large-scale spatial multi-modal datasets remains a major computational challenge. We present SCIGMA, a scalable and generalizable deep learning framework for spatial multi- omics integration. SCIGMA introduces a novel uncertainty-aware contrastive learning objective and multi-view graph neural networks to preserve modality-specific signals while learning biologically meaningful joint representations. Unlike existing methods, SCIGMA provides spatially resolved uncertainty estimates, improving interpretability and identifying regions of biological or technical heterogeneity. SCIGMA is the first spatial multi-omics method to support integration of up to five modalities - as demonstrated on Spatial-Mux-Seq data - and its modular framework is extensible to future technologies with even more modalities. It also scales to over one million spatial locations, enabling analysis of ultra-high-resolution datasets such as VisiumHD and Xenium Prime. We evaluated SCIGMA across 19 datasets spanning 8 modalities, 10 tissues, and 9 platforms. On benchmarkable datasets, SCIGMA outperformed existing methods in spatial domain detection, modality preservation, feature reconstruction, and reproducibility. Across applications, it uncovered biologically meaningful structures, refined spatial domains, and modality-specific regulatory programs, while its uncertainty estimates revealed tissue regions with potential biological or technical variation. Together, SCIGMA provides a robust, flexible, and future-ready solution for scalable spatial multi-modal integration.