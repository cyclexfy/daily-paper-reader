---
title: "RNABag: A Generalizable Transcriptome Foundation Model for Precision Oncology across Biopsy Modalities"
title_zh: RNABag：一种跨活检模式的精准肿瘤学可泛化转录组基础模型
authors: "Luo, P., Luo, D., Li, D., Xue, X., Yang, J., Gong, X., Tang, K."
date: 2026-04-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.19.719450v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 用于精准肿瘤学和癌症分类的转录组基础模型
tldr: RNABag是一个通用的转录组基础模型，旨在解决癌症分析中常见的批次效应和跨平台泛化难题。该模型通过关注高变基因和大规模数据增强进行预训练，学习鲁棒的特征表示。它在泛癌起源分类、癌症检测、生存分层及复发预测等任务中表现优异，并成功扩展至血浆cfRNA和血小板等液体活检领域，为精准肿瘤学的多模态监测提供了强有力的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对转录组数据分析中存在的批次效应和跨平台泛化能力差的问题，开发一种通用的癌症诊断基础模型。
method: 通过筛选高变基因减少噪声，并利用广泛的数据增强技术进行预训练，以学习对批次变化不敏感的鲁棒表示。
result: 模型在泛癌分类和癌症检测中表现卓越，具备强大的零样本泛化能力，并能有效预测患者生存风险及液体活检样本。
conclusion: RNABag证明了通过跨活检方式的全面转录组建模，可以实现对癌症状态和进展的精准监测。
---

## 摘要
转录组数据对癌症状态和进展高度敏感，这使得基于转录组的基础模型在多种临床肿瘤学推理中具有巨大潜力。然而，转录组分析通常受到技术批次效应和跨平台泛化能力有限的阻碍。在这里，我们介绍了 RNABag，这是一种旨在良好泛化至外部数据集的基础模型。特别地，该模型仅关注高变基因以减少噪声；并利用广泛的数据增强对 RNABag 进行预训练，以学习对批次变化具有不变性的鲁棒表示。我们证明了 RNABag 在内部验证集的泛癌组织起源分类和癌症检测中表现优异，并且在外部队列和内部临床样本的零样本泛化中也表现出色。此外，经过专门的微调后，RNABag 在广泛的临床应用中展现出强大的能力。该模型能有效地对患者生存进行分层并预测复发风险，突出了驱动肿瘤进展的关键分子通路。至关重要的是，我们将 RNABag 的效用扩展到液体活检，在血浆 cfRNA 和肿瘤诱导血小板 (TEPs) 中实现了高诊断准确率，从而支持其在无创癌症监测中的应用。可解释性分析揭示了肿瘤免疫逃逸在癌症诱导的血浆 cfRNA 信号中的关键作用。总之，我们的研究表明，通过跨活检模式的转录组综合建模，可以详细且精准地监测癌症状态和进展。

## Abstract
Transcriptomic data is highly sensitive to cancer state and progression, making transcriptome-based foundation models a great promise for diverse clinical ontological inference. However, analyses of transcriptome are conventionally hindered by technical batch effects and limited generalization across platforms. Here, we introduce RNABag, a foundation model designed to generalize well to external datasets. In particular, the model only focuses on highly variable genes to reduce noise; and extensive data augmentation was utilized to pretrain RNABag to learn robust representations, invariant to batch variations. We demonstrate that RNABag achieves superior performance in pan-cancer tissue-of-origin classification and cancer detection in internal validation sets, as well as in zero-shot generalization to external cohorts and in-house clinical samples. Furthermore, RNABag, after specialized finetuning, exhibits strong capabilities in a wide range of clinical applications. The model effectively stratifies patient survival and predicts relapse risks, highlighting key molecular pathways driving tumor progression. Crucially, we extend RNABags utility to liquid biopsies, achieving high diagnostic accuracy in plasma cfRNA and tumor-educated platelets (TEPs), thereby supporting its application in non-invasive cancer monitoring. Interpretability analysis revealed pivotal role of tumor immune escape in the cancer induced plasma cfRNA signals. In summary, our study indicates that cancer states and progression may be monitored in details and precision via comprehensive modeling of transcriptome across biopsy modalities.