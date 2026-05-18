---
title: "Tsallis-Gated Autoencoder: A Nonextensive Physics-Informed Approach for Unsupervised Anomaly Detection in Glioblastoma Multiforme RNA-seq Data"
authors: "Assuncao Monteiro, S., Alves Barbosa da Silva, F."
date: 2026-05-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.13.724767v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 多形性胶质母细胞瘤RNA-seq数据中的异常检测
tldr: 针对胶质母细胞瘤（GBM）基因表达数据的高异质性和重尾分布挑战，本研究提出了一种受非广泛统计力学启发的Tsallis-GAE模型。该模型通过可学习的Tsallis q-softmax门控机制取代传统注意力机制，在TCGA-GBM数据集的无监督异常检测中实现了0.977的AUC-ROC，显著优于传统自编码器，为复杂生物系统的异常识别提供了物理驱动的新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统机器学习方法难以处理胶质母细胞瘤RNA-seq数据中显著的基因组异质性和重尾分布特性。
method: 提出Tsallis-GAE架构，利用受非广泛物理学启发的、带可学习熵指数q的Tsallis q-softmax门控机制和平均场平滑迭代进行特征提取。
result: 在TCGA-GBM数据集上，该模型达到了0.977的AUC-ROC，相比传统自编码器提升了约0.07，且参数q自发收敛于非广泛状态。
conclusion: 实验证明结合非广泛统计力学的物理信息架构能更有效地捕捉复杂生物数据中的异常结构，具有优于传统启发式方法的表征能力。
---

## Abstract
Glioblastoma multiforme (GBM) is characterised by profound genomic heterogeneity and heavy-tailed gene-expression distributions that challenge conventional machine-learning methods. We introduce the Tsallis-Gated Autoencoder (Tsallis-GAE), a physics-informed architecture that replaces classical softmax attention with a learnable Tsallis q-softmax followed by mean-field smoothing iterations, motivated by recent work on curved statistical manifolds and dense associative networks. Trained on the full TCGA-GBM RNA-seq cohort (391 samples, top 2,000 high-variance genes) under a rigorous 80/20 hold-out protocol, the Tsallis-GAE achieves a mean AUC-ROC of 0.977 +/- 0.002 across five independent seeds, compared to 0.906 +/- 0.003 for a matched-capacity Vanilla autoencoder trained under the identical protocol. The matched-capacity Vanilla autoencoder is statistically indistinguishable from a LocalOutlierFactor baseline (AUC 0.906 vs 0.906), confirming that the +0.07 AUC gain over the Vanilla AE stems from the gated attention architecture rather than from the use of a neural network per se. A fixed-q Softmax-AE ablation (q = 1 by construction) achieves AUC 0.976 +/- 0.001, only +0.001 below the Tsallis-GAE (DeLong p = 0.44); the physically meaningful contribution of the learnable q is its spontaneous convergence to the non-extensive regime described below. The three attention blocks each carry an independent learnable entropic index q; across 5 seeds x 3 blocks = 15 measurements, q converges spontaneously to 1.554 +/- 0.019, strictly bounded away from the Boltzmann-Gibbs limit q = 1 and in the moderate non-extensivity regime characteristic of complex biological systems. Cross-detector validation against OneClassSVM and LocalOutlierFactor pseudo-labels yields Tsallis-GAE AUCs of 0.998 and 0.992 respectively, indicating that the learned representation captures anomaly structure intrinsic to the data rather than the decision boundary of any single labeling heuristic. We declare that DeLong's paired test on the present test-set size (n = 79) does not certify the +0.07 AUC gap as formally significant (p approx. 0.26); a 5-fold cross-validation over the full cohort, which would supply the needed statistical power, is left to future work. The source code is available upon reasonable request to the corresponding author.