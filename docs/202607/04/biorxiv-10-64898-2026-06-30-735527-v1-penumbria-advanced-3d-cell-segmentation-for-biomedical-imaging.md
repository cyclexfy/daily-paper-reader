---
title: "Penumbria: Advanced 3D cell segmentation for biomedical imaging"
title_zh: Penumbria：面向生物医学成像的高级三维细胞分割
authors: "Stockert, L., Donovan, J., Baier, H."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.30.735527v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 用于生物医学成像的通用3D细胞分割框架
tldr: "三维细胞分割是生物医学成像分析的瓶颈，现有方法在处理多样细胞形态和低信噪比数据时表现有限。本文提出Penumbria框架，将分割转化为到细胞边界的距离回归问题，采用U-Net结合xLSTM瓶颈块和补丁嵌入，并引入全局Zernike相位层和缩放地理胶囊层分别处理像差和多尺度一致性。在四个多样三维数据集上，Penumbria优于Cellpose-SAM和StarDist-3D，平均精度最高提升38%，并释出1,543个斑马鱼神经元标注数据集。"
source: biorxiv
selection_source: fresh_fetch
motivation: 三维细胞分割因细胞形态多样、信噪比低及数据稀缺而成为瓶颈，现有方法无法通用处理各种成像条件。
method: Penumbria使用距离回归实现实例分割，基于U-Net加xLSTM瓶颈和补丁嵌入，并集成全局Zernike相位层校正像差与缩放地理胶囊层确保多尺度一致性。
result: "在四个三维数据集上，Penumbria全面超越Cellpose-SAM，除一个数据集外均优于StarDist-3D，平均精度最高提升38%。"
conclusion: Penumbria实现了通用、高精度的三维细胞分割，支持下游定量分析，并提供新数据集促进社区研究。
---

## 摘要
三维细胞结构的定量分析是理解组织组织、疾病进展和药物反应的基础。目前已有有效的二维分割方法，但由于细胞形态多样、信噪比低以及数据稀缺，三维细胞分割仍然是一个关键瓶颈。我们提出了Penumbria，一个通用三维细胞分割框架，在体显微镜下对不同形态的细胞群体和成像条件实现了最先进的准确性。Penumbria将分割表述为到细胞边界的距离回归问题，无需形状先验即可进行实例重建，并支持端到端GPU推理。基于U-Net的架构结合了xLSTM瓶颈块和补丁嵌入，实现了多尺度特征提取、空间上下文的远程建模以及卷积特征量分词化。该模型扩展了两个模块：全局Zernike相位层，在频域中学习Zernike参数化的相位校正以处理离焦和倾斜等光学像差；以及缩放地理帽层，在多个空间尺度上的固定网格位置采样特征，并在它们之间路由证据，使得检测仅在同时跨尺度一致时才具有置信度。在四个旨在测试现有方法极限的不同三维数据集上，Penumbra在所有四个数据集上优于Cellpose-SAM，在三个数据集上优于StarDist-3D，在第四个数据集上精度相当，平均精度均值比第二好的方法提高了高达38%。Penumbra强大的边界精度进一步支持了下游分析，如量化膜动力学或蛋白质定位。我们还发布了一个手工标注的共聚焦数据集，包含七个体积的1,543个斑马鱼神经元，Penumbra可以轻松快速地在此数据集上进行训练。

## Abstract
Quantitative analysis of three-dimensional cellular architecture is fundamental to understanding tissue organization, disease progression, and drug response. There are effective approaches for 2D segmentation, yet 3D cell segmentation remains a critical bottleneck due to diverse cell morphologies, low signal-to-noise ratios, and data scarcity. We introduce Penumbria, a general-purpose 3D cell segmentation framework that achieves state-of-the-art accuracy across morphologically distinct cell populations and imaging conditions in volumetric microscopy. Penumbria formulates segmentation as a regression problem on distances to cell boundaries, supporting instance reconstruction without shape priors and permitting end-to-end GPU inference. A U-Net-based architecture with xLSTM bottleneck blocks and patch embeddings enables multi-scale feature extraction, long-range modeling of spatial context, and convolutional feature-volume tokenization. The model is extended with two modules: a Global Zernike Phase Layer, which learns Zernike-parameterized phase corrections in the frequency domain to deal with optical aberrations such as defocus and tilt, and a Scaled Geocaps Layer, which samples features at fixed grid locations across multiple spatial scales, routing evidence between them such that a detection is only confident where concordance holds across scales simultaneously. Across four diverse 3D datasets selected to probe the limits of existing methods, Penumbria outperforms Cellpose-SAM on all four and StarDist-3D on three, with comparable accuracy on the fourth, achieving up to a 38% improvement in mean average precision over the second-best method. Penumbrias strong boundary accuracy further supports downstream analyses such as quantifying membrane dynamics or protein localization. We also release a hand-labeled confocal dataset of 1,543 zebrafish neurons across seven volumes, on which Penumbria can be easily and quickly trained.