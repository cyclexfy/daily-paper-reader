---
title: Anatomy-Guided 3D Graph Networks for Couinaud Segmentation in Tumor Affected Livers
title_zh: 解剖学引导的 3D 图网络用于受肿瘤影响肝脏的 Couinaud 分段
authors: "You, L., Dang, H., Wang, H., Matta, E., zhou, X."
date: 2026-05-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724316v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 使用图网络在肝脏CT/MR图像中进行肿瘤分割
tldr: 本研究针对肿瘤导致的肝脏结构扭曲问题，提出一种解剖引导的3D图卷积网络框架。该框架结合3D UNet与3D GCN，通过两阶段策略隔离肝脏并进行全局空间推理，在临床盲测中Dice得分达0.828，展现了极强的泛化性能，并提供了首个开源的Couinaud分段深度学习资源。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统算法在处理肝癌导致的病理性结构扭曲时泛化能力不足，难以准确进行Couinaud分段。
method: 提出一种结合3D UNet与3D图卷积网络（GCN）的两阶段框架，利用解剖结构引导进行边界推理。
result: 模型在临床数据集盲测中达到了0.828的平均Dice得分，显著提升了在复杂病例上的表现。
conclusion: 该研究为受肿瘤影响的肝脏提供了鲁棒的分段方案，并发布了首个公开的Couinaud分段深度学习资源。
---

## 摘要
基于图像的肝脏 Couinaud 分段旨在自动提供肝脏 CT/MR 图像中可疑对象的位置。一旦实现，医生将被引导至可疑结节所在的目标切片和区域。然而，主要在健康肝脏图像上训练的传统算法由于病理性结构扭曲，往往难以推广到肝细胞癌 (HCC) 病例。在这项工作中，我们提出了一个鲁棒的两阶段框架，该框架集成了 3D UNet 和 3D 解剖结构引导的图卷积网络 (3D GCN)。这种两阶段策略有效地隔离了肝脏体积，以消除来自脾脏等邻近器官的结构噪声，使框架能够专注于八个分段之间复杂的 3D 解剖关系。为了确保全局空间推理所需的拓扑一致性，我们实施了一个标准化的预处理流水线，将仅含肝脏的体积沿 z 轴精确归一化为 50 帧。通过将轻量级 3D UNet 骨干网络与用于精细边界推理的 3D GCN 相结合，我们的模型在未见过的临床数据集上展示了卓越的泛化性能，在盲测中达到了 0.828 的平均 Dice 分数。通过发布我们的代码和预训练权重，我们旨在为鲁棒的 Couinaud 分段提供第一个公开可用的深度学习资源。

## Abstract
Image-based liver Couinaud segmentation is designed to automatically provide the locations of suspicious objects in liver CT/MR images. Once achieved, the physicians will be guided to the target slice and area where the suspicious node is located. However, conventional algorithms trained primarily on healthy liver images often fail to generalize to Hepatocellular Carcinoma (HCC) cases due to pathological structural distortions. In this work, we propose a robust two-stage framework that integrates a 3D Unet with a 3D Anatomical Structure-Guided Graph Convolutional Network (3D GCN). This two-stage strategy effectively isolates the liver volume to eliminate structural noise from neighboring organs, such as the spleen, allowing the framework to focus exclusively on the complex 3D anatomical relationships among the eight segments. To ensure the topological consistency required for global spatial reasoning, we implement a standardized preprocessing pipeline that normalizes liver-only volumes to exactly 50 frames along the z-axis. By combining a lightweight 3D UNet backbone with the 3D GCN for refined boundary reasoning, our model demonstrates superior generalization performance on unseen clinical datasets, achieving a mean Dice score of 0.828 in blind testing. By releasing our code and pretrained weights, we aim to provide the first publicly available deep learning resource for robust Couinaud segmentation.