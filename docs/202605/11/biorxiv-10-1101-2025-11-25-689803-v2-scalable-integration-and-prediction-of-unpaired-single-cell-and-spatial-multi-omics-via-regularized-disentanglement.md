---
title: Scalable integration and prediction of unpaired single-cell and spatial multi-omics via regularized disentanglement
title_zh: 通过正则化解耦实现非配对单细胞与空间多组学的可扩展整合与预测
authors: "Sun, J., Liang, C., Wei, R., Zheng, P., Yan, H., Bai, L., Zhang, K., Ouyang, W., Ye, P."
date: 2026-05-10
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.25.689803v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 单细胞与空间多组学的整合
tldr: 针对单细胞与空间多组学数据因破坏性检测导致的不匹配、异质性及规模庞大等集成难题，本文提出了scMRDR框架。该框架基于正则化解耦表示学习，无需配对监督即可实现跨模态数据的统一整合。它在保持计算效率的同时，支持跨模态翻译和空间坐标预测，为大规模多组学分析提供了高效且通用的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决大规模、非配对单细胞与空间多组学数据在集成过程中面临的模态异质性、技术噪声及计算扩展性挑战。
method: 提出了一种基于正则化解耦表示学习的统一架构，通过结构保持机制在无需配对监督的情况下实现多组学数据的对齐。
result: 在多个真实数据集上证明了该方法在批次校正、模态对齐及生物信号保留方面表现优异，并能有效进行空间坐标插补。
conclusion: scMRDR是一个可扩展且多功能的框架，能够支持复杂的跨模态翻译和空间解析分析，推动了大规模多组学研究的发展。
---

## 摘要
破译细胞状态需要能够整合大规模异构单细胞和空间组学数据的方法。然而，由于破坏性检测，这些数据通常是非配对的，并进一步受到模态异质性、技术噪声和巨大规模的干扰。在此，我们提出了 scMRDR，这是一个基于正则化解耦表示学习的可扩展计算框架，用于整合完全非配对的单细胞和空间多组学数据集。scMRDR 构建在统一且保持结构的架构之上，消除了对配对监督的需求，同时保持了计算效率，使其能够扩展到跨越多个不同组学模态的大型数据集。在各种真实世界的基准测试中，scMRDR 在批次校正、模态对齐和生物信号保留方面表现出强大的性能。该框架进一步支持跨组学模态的跨模态转换，并能够利用参考图谱为非空间单细胞数据集进行空间坐标插补。由此产生的空间映射允许进行空间分辨率分析，包括识别空间变量基因以及在原生组织背景下表征表观遗传调控程序。这些能力使 scMRDR 成为大规模多组学整合的可扩展且通用的框架。

## Abstract
Deciphering cellular states requires methods capable of integrating large-scale heterogeneous single-cell and spatial omics data. However, these data are typically unpaired due to destructive assays and further confounded by modality heterogeneity, technical noise, and immense scale. Here we present scMRDR, a scalable computational framework based on regularized disentangled representation learning for integrating fully unpaired single-cell and spatial multi-omics datasets. Built on a unified and structure-preserving architecture, scMRDR removes the need for pairing supervision while maintaining computational efficiency, enabling scaling to large datasets spanning multiple disparate omics modalities. Across diverse real-world benchmarks, scMRDR demonstrates strong performance in batch correction, modality alignment, and biological signal preservation. The framework further supports cross-modal translation across omics modalities and enables spatial coordinate imputation for non-spatial single-cell datasets using a reference atlas. The resulting spatial mapping allows spatially resolved analyses, including identification of spatially variable genes and characterization of epigenetic regulatory programs in their native tissue context. These capabilities position scMRDR as a scalable and versatile framework for large-scale multi-omics integration.