---
title: Cross-Species Adaptation of RETFound for Rodent OCT Age Estimation Reveals Strong CNN Baselines in Data-Scarce Space Biology
title_zh: RETFound 在啮齿动物 OCT 年龄估计中的跨物种迁移揭示了数据稀缺空间生物学中强大的 CNN 基准模型
authors: "Hayati, A., Gong, J., Nagesh, V., Avci, P., Ong, A. Y., Masalkhi, M., Engelmann, J., Karouia, F., Scott, R. T., Keane, P. A., Costes, S. V., Sanders, L. M."
date: 2026-04-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.22.720210v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: RETFound视网膜基础模型的适配
tldr: 本研究探讨了在数据稀缺的太空生物学背景下，将人类视网膜基础模型RETFound跨物种迁移至大鼠OCT图像进行年龄预测的效果。通过对比RETFound（结合LoRA微调）与预训练的Xception CNN模型，发现虽然人类基础模型具备跨物种迁移能力，但在小样本设置下，传统的CNN基准模型表现更优。该研究为太空生物学中的视网膜生物标志物开发提供了可重复的基准框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对太空生物学成像数据稀缺的问题，评估人类视网膜基础模型在跨物种（啮齿动物）任务中的泛化能力。
method: 使用LoRA技术微调RETFound模型，并与预训练的Xception CNN模型在大鼠OCT数据集上进行年龄预测性能对比。
result: 实验显示Xception模型的预测精度（MAE=19.01天）优于RETFound+LoRA（MAE=26.20天）。
conclusion: 人类视网膜基础模型可有效迁移至啮齿动物研究，但在小样本跨物种场景下，强力的CNN基准模型可能更具优势。
---

## 摘要
空间生物学成像研究通常受限于严重的数据稀缺性，这限制了鲁棒机器学习生物标志物的发展。啮齿动物航天和空间模拟数据集为测试迁移学习策略提供了重要的临床前环境，但人类视网膜基础模型在多大程度上能泛化到啮齿动物光学相干断层扫描（OCT）仍不清楚。在本研究中，我们针对 NASA 开放科学数据存储库数据集 OSD-679 中的 Brown Norway 大鼠 OCT B 扫描，对 RETFound（一种在 160 万张视网膜图像上预训练的人类视网膜 Vision Transformer）的跨物种迁移进行了基准测试，用于实足年龄预测。我们使用低秩自适应（LoRA）对 RETFound 进行了调整，并在匹配的 3 折大鼠级交叉验证下评估了对照组动物的性能。我们将 RETFound+LoRA 与在匹配协议下预训练于 ImageNet 的强大 Xception 基准模型进行了比较，并包含了一个从零开始训练/随机初始化的 ViT 作为负对照架构检查。评估指标包括平均绝对误差（MAE）、R2 和双眼间平均绝对差（MAD）。RETFound+LoRA 实现了 MAE = 26.20 +/- 5.03 天，R2 = 0.744 +/- 0.049。然而，Xception 在主要基准测试中表现更好（MAE = 19.01 +/- 7.67 天，R2 = 0.853 +/- 0.082），且匹配折比较也倾向于 Xception，尽管考虑到折数较少，应谨慎解释这一结果。在匹配的对照评估中，双眼间的一致性得以保持，且显著性图将模型注意力定位在解剖学上合理的视网膜内层区域。总之，这些结果表明人类视网膜基础模型可以以科学有效的方式迁移到啮齿动物 OCT，但也表明在小样本跨物种设置中，强大的 CNN 基准模型可能优于基于 Transformer 的模型。本预印本为未来空间生物学中的视网膜生物标志物开发提供了一个可重复的基准和基线框架。

## Abstract
Space-biology imaging studies are often constrained by severe data scarcity, limiting the development of robust machine-learning biomarkers. Rodent spaceflight and space-analog datasets provide an important preclinical setting for testing transfer-learning strategies, but the extent to which human retinal foundation models can generalize to rodent optical coherence tomography (OCT) remains unclear. Here, we benchmark cross-species adaptation of RETFound, a human retinal Vision Transformer pretrained on 1.6 million retinal images, for chronological age prediction from Brown Norway rat OCT B-scans in the NASA Open Science Data Repository dataset OSD-679. We adapted RETFound using Low-Rank Adaptation (LoRA) and evaluated performance on control animals under matched 3-fold rat-level cross-validation. We compared RETFound+LoRA with a strong ImageNet-pretrained Xception baseline under matched protocols and included a scratch/random ViT as a negative-control architecture check. Metrics included mean absolute error (MAE), R2, and inter-eye mean absolute difference (MAD). RETFound+LoRA achieved MAE = 26.20 +/- 5.03 days with R2 = 0.744 +/- 0.049. However, Xception performed better in the primary benchmark (MAE = 19.01 +/- 7.67 days, R2 = 0.853 +/- 0.082), and the matched-fold comparison favored Xception, although this result should be interpreted cautiously given the small number of folds. Inter-eye consistency was maintained across the matched control evaluation, and saliency maps localized model attention to anatomically plausible inner retinal regions. Together, these results show that human retinal foundation models can transfer to rodent OCT in a scientifically useful way, but also that strong CNN baselines may outperform transformer-based models in small-sample cross-species settings. This preprint provides a reproducible benchmark and baseline framework for future retinal biomarker development in space biology.