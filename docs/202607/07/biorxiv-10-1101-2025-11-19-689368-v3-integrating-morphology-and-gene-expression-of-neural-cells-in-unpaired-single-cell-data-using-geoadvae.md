---
title: Integrating morphology and gene expression of neural cells in unpaired single-cell data using GeoAdvAE
title_zh: 使用GeoAdvAE整合非配对单细胞数据中神经细胞的形态和基因表达
authors: "Du, J. T., Chartrand, T., Jayadev, S., Prater, K. E., Lin, K. Z."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.19.689368v3.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 形态与基因表达的未配对多模态整合
tldr: 整合单细胞形态与单细胞RNA-seq面临数据非配对和特征不对应的挑战。GeoAdvAE采用几何感知对抗自编码器，耦合模态特异性变分自编码器并加入Gromov-Wasserstein正则化和对抗判别器，将非配对的形态和转录组嵌入共享潜空间，保持重建保真度和跨模态几何。基于patch-seq神经元真值验证，其跨模态细胞类型匹配准确率优于最优传输、潜对齐等基线方法。应用于5xFAD阿尔茨海默病模型98个微胶质细胞形态和3万余转录组，恢复了一维整合轴，集成梯度归因揭示DNA修复和细胞杀伤等转录变化，并发现疾病相关微胶质特征与形态解耦。GeoAdvAE为无法进行联合测量时的细胞形式与功能连接提供了可扩展且可解释的方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 单细胞形态与转录组缺乏共同测量，且数据非配对，限制了探索细胞形态转变的转录基础。
method: GeoAdvAE通过对抗自动编码器框架，结合模态特定VAE、Gromov-Wasserstein正则化和对抗判别器，将非配对形态和转录组对齐到共享潜空间。
result: 在patch-seq神经元上跨模态细胞类型匹配准确率最佳；在阿尔茨海默病微胶质细胞中恢复形态-转录组轴，揭示疾病相关基因和解耦现象。
conclusion: GeoAdvAE为单细胞形态和转录组的无配对整合提供了可扩展解释性方法，适用于无法联合测量的情景。
---

## 摘要
背景：在许多疾病中观察到细胞形态转变，但其功能作用仍不清楚，因为很少有技术在同一细胞中同时分析形态和功能。将单细胞形态与转录组学联系起来很困难：两种模态没有特征对应关系，且通常在不同细胞中测量。

方法：我们提出GeoAdvAE，一种用于单细胞形态和单细胞RNA测序的对角线（非配对）整合的几何感知对抗自编码器。GeoAdvAE将模态特异性变分自编码器与Gromov-Wasserstein正则化器和对抗判别器相结合，将非配对的形态和转录组嵌入到共享的潜在空间中，同时保持重建保真度和跨模态几何结构。

结果：使用具有联合形态-RNA测量的patch-seq神经元作为真实值，GeoAdvAE在对角线整合方法中实现了最佳的跨模态细胞类型匹配准确性，优于最优传输、潜在对齐和对抗基线。应用于来自5xFAD阿尔茨海默病模型的98个CAJAL量化小胶质细胞形态和31,948个单细胞转录组，GeoAdvAE恢复了一个对齐两种模态的一维轴。集成梯度归因突出了转录组变化（分支状小胶质细胞中的DNA修复；变形虫状小胶质细胞中的细胞杀伤），提名了基因标记（Ms4a6b；Ftl1 /Fth1），并揭示了与形态解耦的疾病相关小胶质细胞特征。

结论：当形态和转录组的联合分析不可行时，GeoAdvAE提供了一种可扩展且可解释的方法来连接细胞的“形态”和“功能”。我们的方法公开于https://github.com/turbodu222/GeoAdVAE。

## Abstract
BackgroundCellular morphological transitions are observed across many diseases, yet their functional role remains unclear because few technologies profile form and function in the same cell. Linking single-cell morphology to transcriptomics is difficult: the two modalities share no feature correspondence and are typically measured in different cells.

MethodsWe present GeoAdvAE, a geometry-aware adversarial autoencoder for diagonal (unpaired) integration of single-cell morphology and single-cell RNA sequencing. GeoAdvAE couples modality-specific variational autoencoders with a Gromov-Wasserstein regularizer and an adversarial discriminator to embed unpaired morphologies and transcriptomes into a shared latent space that preserves both reconstruction fidelity and cross-modal geometry.

ResultsUsing patch-seq neurons with joint morphology-RNA measurements as ground truth, GeoAdvAE attains the best cross-modal cell-type matching accuracy among diagonal integration methods, outperforming optimal-transport, latent-alignment, and adversarial baselines. Applied to 98 CAJAL-quantified microglial morphologies and 31,948 single-cell transcriptomes from the 5xFAD Alzheimers disease model, GeoAdvAE recovers a one-dimensional axis that aligns the two modalities. Integrated-gradient attribution highlights transcriptomic shifts (DNA repair in ramified microglia; cell killing in amoeboid microglia), nominates gene markers (Ms4a6b; Ftl1 /Fth1), and reveals disease-associated microglia signatures that are decoupled from morphology.

ConclusionsGeoAd-vAE provides a scalable and interpretable approach to connecting cellular "form" and "function" when joint profiling of morphology and transcriptomics is impractical. Our method is publicly available at https://github.com/turbodu222/GeoAdVAE.