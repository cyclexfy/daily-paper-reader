---
title: Morphological fingerprints enable machine learning based inference of neuroblastoma cell states without transcriptomics
title_zh: 形态学指纹助力基于机器学习的神经母细胞瘤细胞状态推断，无需依赖转录组学
authors: "Zamloot, V., Pan, Y., Park, J."
date: 2026-05-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.12.724731v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 从形态指纹推断癌细胞状态的机器学习框架
tldr: 本研究提出一种基于机器学习的形态学分析框架，旨在解决癌症细胞状态推断依赖转录组学导致的成本高、无法实时监测的问题。以神经母细胞瘤为模型，该方法通过高维形态指纹精准识别ADRN和MES状态，且与单细胞转录组高度一致。研究证明形态学能捕捉细胞状态转换的连续轨迹，为高通量表型分析和细胞可塑性实时追踪提供了可扩展、非破坏性的新方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的转录组学分析在推断癌症细胞状态时存在成本高、通量低且无法实现实时无损监测的局限性。
method: 开发了一种机器学习形态学分析框架，利用高维形态指纹直接推断神经母细胞瘤的肾上腺素能和间充质细胞状态。
result: 研究发现形态学定义的细胞状态与单细胞转录组谱高度吻合，并能揭示不同扰动下细胞状态转换的连续轨迹。
conclusion: 细胞形态可作为细胞状态的可扩展且非破坏性读数，为癌症细胞可塑性的实时追踪和高通量表型筛选提供了统一框架。
---

## 摘要
推断癌症细胞状态对于理解致癌机制和预测临床结果至关重要，但目前对转录组分析的依赖限制了其可扩展性和实时监测能力。在本研究中，我们证明细胞形态学提供了细胞身份及其动态的一种低维、可观察的表征。以神经母细胞瘤（NB）作为模型系统，我们建立了一个机器学习-形态学分析框架，能够直接从高维形态学指纹中推断肾上腺素能（ADRN）和间充质（MES）细胞状态，而无需依赖转录组测量。通过与单细胞RNA测序（scRNA-seq）进行基准对比，我们证明了在单细胞分辨率下，由形态学定义的细胞状态与转录组谱高度一致。我们进一步展示了细胞状态的转换在形态学定义的状态空间内表现为连续轨迹。针对不同调节层（包括ROCK信号传导和通过EZH2进行的表观遗传调节）的扰动，会驱动细胞沿共同的表型轴产生收敛的轨迹。总之，这些结果确立了细胞形态学作为一种可扩展且非破坏性的细胞状态读数，而机器学习则为高通量表型分析和癌症细胞状态可塑性的实时追踪提供了一个统一的框架。

## Abstract
Inference of cancer cell states is essential for understanding oncogenic mechanisms and predicting clinical outcomes, yet current reliance on transcriptomic profiling limits scalability and real-time monitoring. Here, we show that cell morphology provides a low-dimensional, observable representation of cellular identity and its dynamics. Using neuroblastoma (NB) as a model system, we establish a machine learning- morphology profiling framework that infers adrenergic (ADRN) and mesenchymal (MES) cell states directly from high-dimensional morphological fingerprints without reliance on transcriptomic measurements. By benchmarking against single-cell RNA sequencing (scRNA-seq), we demonstrate that morphology-defined states closely align with transcriptomic profiles at single-cell resolution. We further show that cell state transitions are represented as continuous trajectories within a morphology-defined state space. Perturbations targeting distinct regulatory layers, including ROCK signaling and epigenetic regulation via EZH2, drive convergent trajectories along a shared phenotypic axis. Together, these results establish cell morphology as a scalable and non-destructive readout of cell state with machine learning providing a unified framework for high-throughput phenotyping and real-time tracking of cancer cell state plasticity.