---
title: InterScale reveals multi-scale cellular interaction programs in spatial transcriptomics
title_zh: InterScale 揭示了空间转录组学中的多尺度细胞相互作用程序
authors: "Drummer, F. K., Jimenez, S., Marco, F. D., Schaar, A. C., Pentimalli, T. M., Beckmann, J., Rajewsky, N., Theis, F. J."
date: 2026-05-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.07.723456v1.full.pdf"
tags: ["query:cpath"]
score: 6.5
evidence: 用于空间转录组学中多尺度细胞相互作用的图变换器
tldr: 组织稳态和疾病源于跨空间尺度的细胞间相互作用，但现有空间转录组学方法难以同时捕捉局部和长程依赖。本文提出InterScale，一种结合图卷积网络（GCN）和全局Transformer编码器的图Transformer方法，旨在联合建模局部与全局细胞相互作用。该方法能从基因到组织层面解析多尺度交互程序，并在神经类器官和人类胰腺数据集中成功识别了空间受限的神经分化和疾病相关的组织重塑，为研究跨尺度细胞通讯提供了可扩展且可解释的框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的空间转录组学计算方法通常只能捕捉局部邻近或长程依赖，缺乏能同时整合多尺度细胞相互作用的统一框架。
method: 提出InterScale，通过集成图卷积网络作为局部组件和全局Transformer编码器，学习细胞通讯的多尺度表示。
result: 在神经类器官和人类胰腺数据集中，该方法成功解析了受形态发生素梯度调控的神经分化程序以及与1型糖尿病相关的空间组织重塑。
conclusion: InterScale为研究跨尺度的细胞相互作用提供了一个模块化、无偏见且具有生物学可解释性的可扩展分析框架。
---

## 摘要
组织稳态和疾病源于跨空间尺度的细胞间相互作用：从微米范围内的自分泌和近分泌信号，到协调跨组织反应的旁分泌梯度。虽然这些可以通过空间转录组学读取，但现有的计算方法要么捕获基于局部邻接的依赖关系，要么捕获远程依赖关系，但很少在单一框架内同时捕获两者。我们介绍了 InterScale，这是一种图变换器（graph-transformer）方法，可联合建模空间转录组数据中的局部和全局细胞相互作用。通过将图卷积网络作为局部组件与全局变换器编码器集成，InterScale 学习了细胞通讯的多尺度表示。下游工作流实现了从基因到组织层面的相互作用的尺度解析解释。应用于神经类器官中的 Sonic Hedgehog 形态发生素模式，InterScale 解析了空间受限的神经元分化程序以及沿形态发生素梯度的更广泛的祖细胞调节状态。在对比健康和 1 型糖尿病组织的人类胰腺数据集中，它揭示了与疾病相关的空间重组和组织重塑。InterScale 的模块化架构支持多种空间转录组学平台，并为研究跨尺度的细胞相互作用提供了一个可扩展、无偏且具有生物学可解释性的框架。

## Abstract
Tissue homeostasis and disease emerge from cell-cell interactions operating across spatial scales: from autocrine and juxtacrine signals within micrometers to paracrine gradients coordinating responses across tissues. While these can be read out from spatial transcriptomics, existing computational methods capture either local adjacency-based or long-range dependencies, but rarely both within a single framework. We introduce InterScale, a graph-transformer approach that jointly models local and global cellular interactions from spatial transcriptomics data. By integrating a Graph Convolutional Network as a local component with a global transformer encoder, InterScale learns multi-scale representations of cellular communication. A downstream workflow enables scale-resolved interpretation of interactions from gene to tissue level. Applied to Sonic Hedgehog morphogen patterning in neural organoids, InterScale resolves spatially restricted neuronal differentiation programs and broader progenitor regulatory states along the morphogen gradient. In a human pancreatic dataset contrasting healthy and type 1 diabetic tissue, it reveals disease-associated spatial reorganization and tissue remodeling. InterScale's modular architecture supports diverse spatial transcriptomics platforms and provides a scalable, unbiased, and biologically interpretable framework for studying cellular interactions across scales.