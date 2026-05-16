---
title: Dual-view Guided Context-aware Network for Automated Bone Lesion Segmentation and Quantification in Whole-body SPECT
title_zh: 双视图引导的上下文感知网络用于全身 SPECT 骨病灶自动分割与定量分析
authors: "chen, w., Yang, X., Lu, J., Miao, M., Huang, Y., Zheng, S., Zhang, C., Xie, L., Zhang, Y."
date: 2026-05-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.07.723665v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 全身SPECT中肿瘤转移骨病灶的自动分割
tldr: 全身SPECT骨显像对骨转移瘤诊疗至关重要，但自动分割受限于低对比度和复杂分布。本文提出Bone-Segnet网络，通过双视图引导、多尺度建模和Transformer全局上下文增强，提升了小病灶识别力。实验显示Dice分数从0.7440升至0.8750，该方法不仅优化了分割性能，还实现了病灶负荷的定量分析，为临床评估提供客观数据支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对全身SPECT骨显像中病灶对比度低、分辨率有限及分布复杂导致的自动分割挑战。
method: 提出Bone-Segnet网络，结合双视图协作、多尺度上下文建模及Transformer全局特征表示。
result: 实验结果显示Dice评分从0.7440显著提升至0.8750，并成功揭示了不同疾病间的代谢异质性。
conclusion: 该方法提升了骨病灶分割精度并支持定量负荷评估，为相关疾病的临床诊断提供了客观依据。
---

## 摘要
全身 SPECT 骨显像反映了全身骨骼的代谢活动，在肿瘤骨转移的筛查、治疗评估和预后评估中发挥着不可或缺的作用。然而，由于对比度低、空间分辨率有限以及病灶分布复杂，高代谢骨病灶的自动检测和分割仍具挑战性。在本研究中，我们提出了 Bone-Segnet，这是一种用于高代谢骨病灶的双视图引导自动分割网络，集成了多尺度特征建模、全局上下文建模和视图条件调制。使用像素级标注的前后位全身骨显像图像进行模型训练和预测。所提出的网络通过小病灶增强和多尺度上下文建模，增强了对低对比度和细小病灶的识别。进一步引入 Transformer 模块以强化全局特征表示，同时通过结合前后位成像的互补特性实现了跨视图协作建模。实验结果表明，所提方法在多个评估指标上均优于现有方法，Dice 分数从 0.7440 提高到 0.8750，表明分割性能显著提升。基于分割结果的进一步定量分析揭示了不同疾病类型在病灶数量、像素负担和空间分布模式方面的显著差异，反映了疾病相关骨骼代谢活动的异质性。总体而言，所提方法提高了自动病灶分割性能，并实现了病灶负担和空间分布模式的定量分析，为相关疾病的评估提供了客观的数据支持。索引词：全身 SPECT，骨病灶分割，双视图建模，定量分析。

## Abstract
Whole-body SPECT bone scintigraphy reflects skeletal metabolic activity throughout the body and plays an indispensable role in the screening, treatment evaluation, and prognostic assessment of bone metastases in tumors. However, the automatic detection and segmentation of hypermetabolic bone lesions remain challenging due to low contrast, limited spatial resolution, and complex lesion distributions. In this study, we proposed Bone-Segnet, a dual-view guided automatic segmentation network for hypermetabolic bone lesions that integrated multi-scale feature modeling, global context modeling, and view-conditioned modulation. Pixel-level annotated anterior and posterior whole-body bone scintigraphy images were used for model training and prediction. The proposed network enhanced the recognition of low-contrast and small-scale lesions through small-lesion enhancement and multi-scale contextual modeling. A Transformer module was further introduced to strengthen global feature representation, while cross-view collaborative modeling was achieved by incorporating the complementary characteristics of anterior and posterior imaging. Experimental results demonstrated that the proposed method outperformed existing approaches across multiple evaluation metrics, with the Dice score improving from 0.7440 to 0.8750, indicating a substantial improvement in segmentation performance. Further quantitative analysis based on the segmentation results revealed significant differences among disease types in lesion count, pixel burden, and spatial distribution patterns, reflecting the heterogeneity of disease-related skeletal metabolic activity. Overall, the proposed method improved automatic lesion segmentation performance and enabled quantitative analysis of lesion burden and spatial distribution patterns, providing objective data support for the assessment of related diseases. Index Terms--Whole-body SPECT, bone lesion segmentation, dual-view modeling, quantitative analysis.