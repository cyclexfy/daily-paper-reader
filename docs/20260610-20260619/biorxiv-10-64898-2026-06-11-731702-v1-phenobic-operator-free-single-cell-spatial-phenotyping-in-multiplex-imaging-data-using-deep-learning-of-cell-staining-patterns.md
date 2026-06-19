---
title: "PhenoBIC: operator-free single-cell spatial phenotyping in multiplex imaging data using deep learning of cell staining patterns"
title_zh: "PhenoBIC: 利用细胞染色模式的深度学习实现多重成像数据中无操作员单细胞空间表型分析"
authors: "Sankaranarayanan, A., Zhao, C., Hernandez, M. G., Clemens, E. A., Smythe, K. S., Kazerouni, A. S., Carr, L. L., Li, C. I., Partridge, S. C., Vinayak, S., Mittal, S."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.11.731702v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 深度学习用于多重成像中的单细胞空间表型分析，属于计算病理学领域
tldr: 多重成像分析中手动细胞表型分型耗时且依赖操作者。PhenoBIC使用预训练深度学习模型对细胞多重生物标志物信号进行图像分类，实现无操作员自动表型分型。在多种组织、面板和成像平台上，其F1分数约0.88，优于手动门控和其他机器学习方法。该模型开源并附带约140万人工标注标签，可通过QuPath界面部署。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有多重成像细胞表型分析需要人工干预，效率低且结果不一致，亟需自动化方法。
method: 开发了预训练深度学习模型PhenoBIC，基于细胞的多重生物标志物图像模式直接分类表型。
result: PhenoBIC的F1分数约0.88，在多个数据集上优于手动门控及其他机器学习方法。
conclusion: PhenoBIC实现了无操作员、高精度单细胞空间表型分析，并开源数据和模型。
---

## 摘要
多重成像是从单细胞水平上空间研究组织微环境以揭示生物学和临床见解的有价值工具。然而，目前大多数多重图像分析流程需要手动干预进行细胞表型分析，这减缓了进度、耗费人力，并产生依赖于操作者的输出。在此，我们开发了PhenoBIC，一个预训练的深度学习模型，用于对细胞中多重生物标志物信号（细胞的生物标志物印记）进行图像分类，以对细胞表型进行分类。我们证明PhenoBIC（F1分数约0.88）在细胞标志物表达分类方面优于手动设门（广泛使用）和其他基于机器学习的计算方法。我们跨多种生物标志物、组织采样策略（全活检和组织微阵列）、多重检测组合、成像平台和组织类型进行了验证。我们发布了内部训练和验证数据集，包含约140万个手动筛选的细胞表达真实标签。我们还开源了PhenoBIC，并通过QuPath界面实现了其在社区范围内的部署。

## Abstract
Multiplex imaging is a valuable tool for spatially examining tissue microenvironments at the single-cell level to uncover biological and clinical insights. However, most multiplex image analysis workflows currently require manual intervention for cell phenotyping, which slows progress, demands human effort, and yields operator-dependent outputs. Here, we developed PhenoBIC, a pre-trained deep learning model for image classification of the multiplexed biomarker signals in a cell (Biomarker Imprint of a Cell) to classify cell phenotypes. We show that PhenoBIC (F1-score [~]0.88) outperforms manual gating (widely used) and other machine learning-based computational approaches for cell marker expression classification. We validated this across multiple biomarkers, tissue sampling strategies (whole biopsies and tissue microarrays), multiplex panels, imaging platforms, and tissue types. We have released our in-house training and validation datasets of [~]1.4 million manually curated cell expression ground truth labels. We have also open-sourced PhenoBIC and enabled its community-wide deployment via the QuPath interface.