---
title: "MAE-UNETR++: Masked Autoencoder Pretraining for 3-D Lung Nodule Segmentation"
title_zh: MAE-UNETR++：用于三维肺结节分割的掩蔽自编码器预训练
authors: "Savant, V., Wang, Y., Xuan, J."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.733000v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 通过掩码自编码器预训练进行肺结节分割用于癌症诊断
tldr: 三维肺结节分割面临体素级标注昂贵和域差异导致的迁移学习性能下降问题。本文提出基于掩码自编码器(MAE)的预训练方法，在目标域CT数据上进行自监督学习。实验表明，MAE预训练使UNETR++的Dice系数达0.307，显著优于随机初始化(0.136)和Decathlon迁移(0.257)；在低标注数据下，V-Net的DSC从0.010提升至0.071。该方法为有限标注的体积分割提供了鲁棒且实用的初始化策略。
source: biorxiv
selection_source: fresh_fetch
motivation: 三维医学图像体素级标注昂贵，迁移学习因源域与目标域差异大而效果不佳，亟需高效的自监督预训练策略。
method: 采用掩码自编码器(MAE)在目标域CT数据上进行自监督预训练，学习鲁棒的图像表示，再微调至肺结节分割任务。
result: MAE预训练使UNETR++的DSC达0.307，优于随机初始化(0.136)和Decathlon迁移(0.257)；V-Net在低数据场景下DSC从0.010升至0.071。
conclusion: MAE预训练能突破域差异带来的数据效率瓶颈，为有限标注的三维分割提供有效且鲁棒的初始化方法。
---

## 摘要
体素级别的三维医学影像标注成本高昂且难以扩展，这使得在实践中训练高容量三维分割模型面临挑战。从大型公共数据集进行迁移学习是常见的解决方法，但当源域与目标解剖结构和采集特性不同时（如肺结节常见情况），迁移学习可能表现不佳。本文提出一种基于掩蔽自编码器（MAE）预训练的方法，以突破领域差异带来的数据效率瓶颈，并针对三维肺结节分割的领域特定自监督学习进行了重点实证研究。我们评估了两种实验设置：第一，典型基线中MAE预训练与随机初始化的对比；第二，MAE与Decathlon迁移学习在UNETR++上的对比，同时测试基于MAE的预训练是否也惠及CNN基线模型（V-Net）。在目标域CT体数据上，MAE预训练实现了0.307的Dice相似系数（DSC），优于随机初始化的0.136和Decathlon权重的0.257。此外，MAE提升了V-Net在“低数据”场景（即标签不足数据）下的稳定性，将DSC从0.010提升至0.071。总体而言，这些结果表明，当标记数据有限时，基于MAE的预训练可为体素分割提供一种实用且鲁棒的初始化策略。

## Abstract
Voxel-level annotation for volumetric medical imaging is expensive and difficult to scale, which makes training highcapacity 3-D segmentation models challenging in practice. Transfer learning (TL) from large public datasets is a common remedy, but it can under-perform when the source domain differs from the target anatomy and acquisition characteristics, as is often the case for pulmonary nodules. In this work, we propose a masked autoencoder (MAE) pretraining-based approach to break the data efficiency wall of domain difference and present a focused empirical study of domain-specific self-supervised learning (SSL) for 3-D lung nodule segmentation. We evaluate two experimental settings: first, Masked Autoencoder (MAE) pretraining versus random initialization across representative baselines; second, MAE versus Decathlon TL for UNETR++ while testing whether MAE-based pretraining also benefits a CNN baseline (V-Net). MAE pretraining on target-domain CT volumes achieves a Dice Similarity Coefficient (DSC) of 0.307, outperforming random initialization (0.136) and Decathlon weights (0.257). In addition, MAE improves the stability of V-Net in a "low-data" regime (i.e., with "insufficiently labeled" data), increasing DSC from 0.010 to0.071. Overall, these results suggest that MAE-based pretraining can provide a practical and robust initialization strategy for volumetric segmentation when labeled data are limited.