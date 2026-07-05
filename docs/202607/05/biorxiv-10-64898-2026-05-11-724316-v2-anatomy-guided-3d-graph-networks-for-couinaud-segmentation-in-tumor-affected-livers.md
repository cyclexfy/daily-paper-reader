---
title: Anatomy-Guided 3D Graph Networks for Couinaud Segmentation in Tumor Affected Livers
title_zh: 解剖引导的三维图网络用于肿瘤影响肝脏中的库伊诺分割
authors: "You, L., Dang, H., Wang, H., Matta, E., zhou, X."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724316v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 通过肝脏肿瘤分割进行癌症诊断
tldr: 肝脏Couinaud分割在肝癌病例中因肿瘤引起的结构扭曲而极具挑战。本文提出两阶段框架：先用轻量3D UNet分割肝脏以去除邻近器官噪声，再用3D解剖结构引导图卷积网络（3D GCN）建模八个肝段间的空间拓扑关系。通过将肝脏标准化为50帧确保全局一致性，盲测平均Dice达0.828。首次开源针对肿瘤肝脏的Couinaud分割代码与预训练权重，提供有力的公共基线。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法在肝癌肝脏上因病理结构扭曲泛化差，需解剖引导提升鲁棒性。
method: 两阶段：3D UNet提取肝脏区域，3D GCN利用标准化拓扑建模段间边界与空间关系。
result: 盲测平均Dice 0.828，超越传统方法，代码与权重开源。
conclusion: 首次提供针对肿瘤肝脏的Couinaud分割深度学习资源，验证解剖引导图网络的有效性。
---

## 摘要
基于图像的肝脏库伊诺分割旨在自动提供肝脏CT/MR图像中可疑物体的位置。一旦实现，医生将被引导至可疑节点所在的目标切片和区域。然而，主要在健康肝脏图像上训练的常规算法通常由于病理性结构扭曲而无法推广到肝细胞癌（HCC）病例。在这项工作中，我们提出了一个稳健的两阶段框架，该框架集成了3D Unet和三维解剖结构引导的图卷积网络（3D GCN）。这种两阶段策略有效地分离肝脏体积，消除邻近器官（如脾脏）的结构噪声，使框架能够专注于八个分段之间复杂的三维解剖关系。为了确保全局空间推理所需的拓扑一致性，我们实施了一个标准化的预处理流程，将仅包含肝脏的体积沿z轴归一化为精确的50帧。通过将轻量级3D UNet骨干网络与用于精细边界推理的3D GCN相结合，我们的模型在未见过的临床数据集上表现出优越的泛化性能，在盲测中平均Dice得分达到0.828。通过发布我们的代码和预训练权重，我们旨在提供第一个公开可用的深度学习资源，用于稳健的库伊诺分割。

## Abstract
Image-based liver Couinaud segmentation is designed to automatically provide the locations of suspicious objects in liver CT/MR images. Once achieved, the physicians will be guided to the target slice and area where the suspicious node is located. However, conventional algorithms trained primarily on healthy liver images often fail to generalize to Hepatocellular Carcinoma (HCC) cases due to pathological structural distortions. In this work, we propose a robust two-stage framework that integrates a 3D Unet with a 3D Anatomical Structure-Guided Graph Convolutional Network (3D GCN). This two-stage strategy effectively isolates the liver volume to eliminate structural noise from neighboring organs, such as the spleen, allowing the framework to focus exclusively on the complex 3D anatomical relationships among the eight segments. To ensure the topological consistency required for global spatial reasoning, we implement a standardized preprocessing pipeline that normalizes liver-only volumes to exactly 50 frames along the z-axis. By combining a lightweight 3D UNet backbone with the 3D GCN for refined boundary reasoning, our model demonstrates superior generalization performance on unseen clinical datasets, achieving a mean Dice score of 0.828 in blind testing. By releasing our code and pretrained weights, we aim to provide the first publicly available deep learning resource for robust Couinaud segmentation.