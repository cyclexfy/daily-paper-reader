---
title: "GlioVision: A Multi-Modal MRI Framework for Non-Invasive Glioma Molecular Biomarkers Prediction"
authors: "Nazir, A., Cheema, M. N., Hsu, Y.-C., Jiang, X., Zhu, J.-J., Harmanci, A. S., Harmanci, A."
date: 2026-04-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.22.719993v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 利用MRI和分子标签预测胶质瘤分子生物标志物的多模态框架
tldr: 本研究提出GlioVision框架，旨在通过多模态MRI非侵入性地预测胶质瘤的四种关键分子生物标志物。针对传统手术活检的风险及现有深度学习模型在实时性和泛化性上的不足，该框架采用了集成注意力机制的SCRU-DenseNet架构和置信度过滤机制。在大型多中心数据集上的验证表明，该模型在IDH突变和WHO分级等预测上达到了极高的准确率，为符合2021年WHO标准的胶质瘤分子诊断提供了高效、安全的辅助工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统胶质瘤分子标志物检测依赖有创手术且存在采样偏差，而现有深度学习方法缺乏实时性且难以处理异质性数据。
method: 开发了基于MONAI的GlioVision框架，核心采用带有空间和通道注意力机制的SCRU-DenseNet架构，并引入置信度过滤流形来管理预测不确定性。
result: 在多中心数据集上，该模型对IDH、1p/19q、MGMT和WHO分级的预测AUC分别达到0.94、0.87、0.86和0.92。
conclusion: GlioVision实现了高精度的非侵入性胶质瘤分子诊断，并通过隐私保护评估为临床应用和数据安全提供了重要参考。
---

## Abstract
Gliomas are aggressive primary brain tumors that necessitate critical molecular biomarker predictions for optimal clinical decision-making. Traditional assessment relies on surgical tumor specimens analysis, which carries procedural risks and sampling bias due to tumor heterogeneity. Existing deep learning methods for non-invasive prediction lack real-time applicability, remain resource-intensive, and are frequently trained on narrowly represented datasets. We present GlioVision, a framework built on the MONAI library to process multimodal data, including glioma MRI and molecular labels, to predict and identify, non-invasively, four major glioma molecular biomarkers: IDH mutation, 1p/19q co-deletion, MGMT methylation, and WHO grade. The core architecture comprises Spatially and Channel-wise Recalibrated 3D DenseNet (SCRU-DenseNet), which utilizes a computational attention gate and an Adaptive Contrast-Specific Processing Stream (ACPS) to tackle multi-site, heterogeneous datasets. We introduced the Confidence-Filtered Predictive Manifold (CFPM) to manage uncertainty by excluding predictions with low confidence. GlioVision is trained and validated on the largest multi-cohort datasets, achieving strong biomarker prediction with AUCs of (IDH 0.94, 1p/19q 0.87, MGMT 0.86, WHO grades 0.92), supporting molecularly defined glioma diagnosis under the WHO 2021 classification guidelines. Finally, we provide a Differential Training Integrity Assessment (DTI-A) to analyze routes of MRI data privacy protections through model obfuscation. Our results advance the codebase, model release, and leakage considerations around MRI data analysis literature.