---
title: A general method for bootstrapping dense 3D segmentations from sparse 2D annotations
title_zh: 一种从稀疏2D标注引导生成稠密3D分割的通用方法
authors: "Thiyagarajan, V. V., Sheridan, A., Harris, K. M., Manor, U."
date: 2026-05-10
pdf: "https://www.biorxiv.org/content/10.1101/2024.06.14.599135v3.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 在显微镜成像中从稀疏2D标注引导3D分割
tldr: 本研究针对三维显微数据分割中密集标注成本高昂的问题，提出了一种从稀疏二维标注引导生成密集三维实例分割的轻量级框架。该方法结合了预测二维边界的网络和预训练的跨切片连接网络，在多种显微数据集上实现了与专家标注相当的精度，同时将人工标注时间缩短了1000倍，显著降低了三维训练数据的获取门槛。
source: biorxiv
selection_source: fresh_fetch
motivation: 训练高精度的三维分割模型通常需要极其昂贵且耗时的密集三维真值标注。
method: 利用在稀疏标签上训练的二维网络预测切片边界，并结合在合成数据上预训练的三维网络推断切片间的连通性。
result: 该方法在电子显微镜和活细胞成像等多种数据集上达到了专家级精度，并将标注时间减少了三个数量级。
conclusion: 该框架通过将二维基础模型扩展到三维，极大地降低了生成密集三维训练数据的成本和难度。
---

## 摘要
分析体积显微成像数据需要稠密分割，但训练准确的机器学习模型需要极其昂贵的3D真值（ground-truth）。为了克服这一瓶颈，我们提出了一个轻量级框架，直接从稀疏的2D标注中引导生成稠密的3D实例分割。在稀疏标签上训练的2D网络可预测每个切片上的完整边界，而在合成数据上预训练的3D网络则推断切片间的连通性，以构建连贯的3D体积。我们在涵盖电子显微镜、扩展显微镜和活细胞显微镜的多种数据集上验证了这种2D到3D的方法。令人惊讶的是，在这些快速生成的伪真值上训练的3D模型，其准确率与在专家稠密标注上训练的模型相当，使人工标注时间减少了高达1000倍。即使考虑到下游的校对工作，总重建成本也降低了一个数量级。该方法使稠密3D训练数据的生成变得大众化，将2D基础模型无缝扩展到了第三维度。

## Abstract
Analyzing volumetric microscopy data requires dense segmentation, yet training accurate machine learning models demands prohibitively expensive 3D ground-truth. To overcome this bottleneck, we present a lightweight framework that bootstraps dense 3D instance segmentations directly from sparse 2D annotations. A 2D network trained on sparse labels predicts complete boundaries on every section, and a 3D network pre-trained on synthetic data infers inter-section connectivity to build coherent 3D volumes. We validated this 2D-to-3D method across diverse datasets spanning electron, expansion, and live-cell microscopy. Strikingly, 3D models trained on these rapidly generated pseudo ground-truths achieve accuracy comparable to those trained on dense expert annotations, yielding up to a 1,000-fold reduction in human annotation time. Even accounting for downstream proofreading, total reconstruction costs drop by an order of magnitude. This approach democratizes the generation of dense 3D training data, seamlessly extending 2D foundation models into the third dimension.