---
title: Automatic deep learning-based segmentation and quantification of stented arterial cross-sections for morphometric analysis
title_zh: 基于深度学习的支架置入动脉横截面自动分割与定量分析，用于形态计量学研究
authors: "Kraftberger, M., Spirgath, K., Haase, T., Bandelin, R., Meyer, T., Jaitner, N., Tzschätzsch, H."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721259v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 组织学动脉横截面的自动分割
tldr: "针对动脉血管疾病研究中手动形态学分析耗时且主观的问题，本文提出了一种基于深度学习的自动化框架qHisto。该框架通过神经网络对支架动脉横截面进行精确分割，实现了对血管形态、纤维蛋白面积和管腔不对称性的定量分析。实验表明，该系统在保持高分割精度的同时，将分析时间缩短了90%，并能有效区分不同治疗干预的效果，为临床前研究提供了标准化工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的动脉组织学形态分析依赖人工操作，存在耗时长、主观性强且难以处理大规模数据集的问题。
method: 开发并训练了一个深度神经网络用于动脉结构分割，并扩展了qHisto框架以实现血管形态和组织成分的自动定量分析。
result: "模型分割精度中位Dice系数达0.892-0.996，分析效率提升90%，并成功识别出涂层与非涂层球囊在管腔面积等指标上的显著差异。"
conclusion: 该自动化框架实现了组织学横截面的标准化高效分析，显著降低了人工负担，有助于加速血管疾病机制和治疗效果的研究。
---

## 摘要
动脉血管疾病（如动脉粥样硬化）是全球最严重的健康威胁之一。在临床前研究中，组织学动脉横截面的形态计量分析被认为是评估血管重塑和治疗干预有效性的金标准。然而，形态计量分析通常由人工完成，这不仅耗时、具有主观性，且需要大量的人机交互。本文提出了一个全自动、独立于操作者的框架，用于支架置入动脉横截面的精确形态计量分析，扩展了先前开发的用于量化各种组织学成分的 qHisto（定量组织学）框架。使用 819 个横截面训练并评估了一个用于分割动脉结构的神经网络。此外，利用来自涂层和非涂层球囊的 72 个横截面，对血管形态、纤维蛋白面积和管腔不对称性进行了定量分析。该模型实现了极高的分割精度，中值 Dice 相似系数达到 0.892-0.996。与人工评估相比，该系统将分析时间缩短了 90%，从而能够高效处理大型数据集。此外，使用 qHisto 进行的形态计量分析显示，涂层和非涂层球囊之间存在显著差异，例如在管腔面积（AUC = 0.86）和纤维蛋白比例（AUC = 0.94）方面。我们开发的框架实现了组织学动脉横截面的全自动、全面且标准化的分析。这有助于减少耗时且重复的人工评估，从而促进临床前研究中疾病机制和治疗效果的研究。

## Abstract
Arterial vascular diseases, such as atherosclerosis, are among the most serious global health threats. In preclinical studies, morphometric analysis of histological arterial cross-sections is considered the gold standard for assessing vascular remodeling and the effectiveness of therapeutic interventions. However, morphometric analysis is usually performed manually, which is time-consuming, subjective, and requires significant user interaction. This paper presents a fully automated, operator-independent framework for the precise morphometric analysis of stented arterial cross-sections, extending the previously developed qHisto (quantitative histology) framework for the quantification of various histological components. A neural network for the segmentation of arterial structures was trained and evaluated using 819 cross-sections. In addition, a quantitative analysis of vascular morphology, fibrin area, and lumen asymmetry was performed using 72 cross-sections from coated and uncoated balloons. The model achieved high segmentation accuracy with a median Dice similarity coefficient of 0.892-0.996. Compared to manual evaluation, the system reduces analysis time by 90%, enabling efficient processing of large datasets. Furthermore, morphometric analysis with qHisto showed significant differences between coated and uncoated balloons, e.g. regarding lumen area (AUC = 0.86) and fibrin ratio (AUC = 0.94). Our developed framework enables fully automated, comprehensive and standardized analysis of histological arterial cross-sections. This helps to reduce time-consuming, repetitive manual assessments and thus facilitates research of disease mechanisms and treatment effects in preclinical studies.