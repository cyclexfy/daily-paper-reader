---
title: "Turep: Detecting cross-cancer tumor-reactive T cells in single-cell and spatial transcriptomics data"
title_zh: Turep：在单细胞和空间转录组数据中检测跨癌种肿瘤反应性T细胞
authors: "Liu, W., Tung, C.-H., Sevick-Muraca, E. M., Zhao, Z."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.719961v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 利用深度学习和空间转录组学进行跨癌症肿瘤检测
tldr: 识别肿瘤反应性T细胞对免疫治疗至关重要，但现有方法缺乏跨癌种鲁棒性。本文提出深度学习工具Turep，通过整合7种癌症的单细胞转录组与TCR数据，利用泛癌基因特征和数据增强技术，实现了高精度的跨癌种预测。Turep不仅能有效预测免疫治疗响应，还能揭示T细胞在空间转录组中的分布规律，为个性化免疫治疗提供了强有力的支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的肿瘤反应性T细胞识别特征通常源自单一队列，在跨癌种预测中缺乏鲁棒性。
method: 开发了基于深度学习的Turep方法，整合多癌种单细胞测序数据并利用生成式数据增强来识别泛癌肿瘤反应性基因特征。
result: Turep在不同癌症类型中实现了0.870的平均AUC，且其预测的T细胞比例能有效预示免疫治疗的临床响应。
conclusion: Turep为识别肿瘤反应性T细胞及其空间架构提供了强大的通用工具，有助于推动个性化癌症免疫治疗策略。
---

## 摘要
肿瘤浸润淋巴细胞对抗肿瘤免疫至关重要，但区分肿瘤反应性T细胞与非反应性旁观者细胞仍是一个重大挑战。现有的特征通常源自单一队列，在跨癌种预测中缺乏鲁棒性。我们提出了 Turep，这是一种深度学习方法，旨在利用单细胞或空间转录组数据对肿瘤反应性T细胞进行鲁棒的跨癌种预测。通过整合来自七种人类恶性肿瘤的配对单细胞 RNA 和 T 细胞受体测序数据，我们鉴定出了泛癌种肿瘤反应性基因特征，并利用生成式数据增强来解决数据不平衡问题。Turep 的表现始终优于现有的生物标志物，在不同癌症类型中实现了 0.870 的平均受试者工作特征曲线下面积（AUC）。在不同队列的验证中，我们发现 Turep 预测的肿瘤反应性 T 细胞比例可以预测免疫治疗的临床反应。此外，将 Turep 扩展到空间转录组学揭示了肿瘤反应性 T 细胞优先驻留在靶细胞表现出高水平抗原呈递的空间生态位中。总之，Turep 为识别肿瘤反应性 T 细胞及其空间架构提供了一个强大且具有泛化能力的工具，有助于实现个性化癌症免疫治疗策略。

## Abstract
Tumor-infiltrating lymphocytes are essential for anti-tumor immunity, yet distinguishing tumor-reactive T cells from non-reactive bystander cells remains a significant challenge. Existing signatures, often derived from single cohorts, lack robustness in cross-cancer prediction. We present Turep, a deep learning method designed for robust, cross-cancer prediction of tumor-reactive T cells using single-cell or spatial transcriptomics data. By integrating paired single-cell RNA and T cell receptor sequencing data from seven human malignancies, we identified a pan-cancer tumor-reactive gene signature and leveraged generative data augmentation to address data imbalance. Turep consistently outperformed existing biomarkers, achieving a mean area under the receiver operating characteristic curve of 0.870 across cancer types. In validation across diverse cohorts, we found that Turep-predicted tumor-reactive T cell proportions could predict clinical response to immunotherapy. Furthermore, extending Turep to spatial transcriptomics revealed that tumor-reactive T cells preferentially resided in spatial niches where target cells exhibited elevated antigen presentation. Overall, Turep provides a powerful, generalizable tool for identifying tumor-reactive T cells and their spatial architectures, facilitating personalized cancer immunotherapy strategies.