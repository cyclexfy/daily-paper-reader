---
title: A modular generalist-specialist AI framework for ROI selection across spatial profiling workflow
title_zh: 一种用于空间剖析工作流程中ROI选择的模块化通用-专用AI框架
authors: "Castillo, S. P., Gautam, T., Pinao Gonzales, K. B., Salvatierra, M. E., Serrano, A., Ercan, C., Rodriguez, B. L., Acosta, P., Chen, P., Shokrollahi, Y., Lau, A., Kwong, L. N., Huse, J. T., Pan, X., Patient Mosaic Team,, Solis Soto, L. M., Yuan, Y."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.26.734862v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于空间分析中AI引导的ROI选择，涉及多种肿瘤类型
tldr: 空间分子谱分析中ROI选择对可重复性至关重要。本文开发了模块化通用-专业AI框架ASTROS，基于55种肿瘤类型的蛋白质参考图谱，通过混合通用-专业策略实现了信号保留、病理一致性、放置一致性和计算效率的平衡。该框架还支持虚拟染色预览和跨平台部署，显著降低了评估者间变异。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有ROI选择依赖人工，主观性强且缺乏可重复性，亟需自适应、可复用的AI框架降低变异。
method: 构建蛋白质参考图谱，开发ASTROS模型，并对比专用、通用及混合策略，实现平衡的ROI选择。
result: 混合策略在信号保留、病理一致性等指标最优，验证了虚拟染色及Visium/HD可行性。
conclusion: 该框架有效减少评估者间差异，提升空间谱分析的可重复性与通用性。
---

## 摘要
感兴趣区域（ROI）的选择通常是空间分子剖析和许多病理学任务中的关键步骤，对研究可重复性和生物学可解释性具有重要影响。为了提供一个可重复且自适应的AI引导ROI选择框架，我们开发了一种跨空间剖析平台的模块化通用-专用解决方案。在一个包含来自160个组织供体的55种肿瘤类型的队列中，使用NanoString数字空间剖析和多重免疫荧光进行分析，我们首先建立了一个蛋白质剖析参考图谱，捕获了区室特异性的免疫、检查点、基质和增殖模式。然后，我们开发了用于ROI选择的AI专用任务导向模型（ASTROS），并测试了包括仅专用（ASTROS）、仅通用（PLIP/GFM）以及混合通用-专用策略在内的全面基准测试，结果表明后者在幻灯片级别信号保存、病理学家参考一致性、幻灯片内放置一致性和大幻灯片计算效率之间提供了平衡的权衡。我们进一步证明了虚拟染色用于ROI预览的可行性，以及针对其他空间组学技术（Visium和Visium HD工作流程）的模块化ROI放置。总之，这些结果支持了我们提出的框架，该框架能够满足空间剖析实验中减少评分者间变异性、提高可重复性和多功能性的未满足需求。

## Abstract
Selection of regions of interest (ROIs) is often a crucial step in spatial molecular profiling and many pathology tasks, with substantial implications for research reproducibility and biological interpretability. To provide a reproducible and adaptive framework for AI-guided ROI selection, we developed a modular generalist-specialist solution across spatial profiling platforms. In a cohort comprising 55 tumor types from 160 tissue donors profiled using NanoString Digital Spatial Profiling and multiplex immunofluorescence, we first established a protein-profiling reference atlas capturing compartment-specific immune, checkpoint, stromal, and proliferation patterns. We then developed an AI Specialist Task-Oriented Model for ROI Selection (ASTROS) and tested comprehensive benchmarks considering specialist-only (ASTROS), generalist-only (PLIP/GFM), and hybrid generalist-specialist strategies, showing that the latter provides a balanced tradeoff across slide-level signal preservation, pathologist-reference concordance, within-slide placement consistency, and large-slide computational efficiency. We further demonstrated the feasibility of virtual staining for ROI preview and modular ROI placement for other spatial omics technologies, Visium and Visium HD workflows. Together, these results support our proposed framework to enable ROI selection responding to unmet needs for reducing inter-rater variability, reproducibility, and versatility in spatial profiling experiments.