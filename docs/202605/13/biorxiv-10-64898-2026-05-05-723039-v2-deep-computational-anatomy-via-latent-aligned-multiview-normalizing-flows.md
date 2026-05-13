---
title: Deep Computational Anatomy via Latent-Aligned Multiview Normalizing Flows
title_zh: 基于潜空间对齐多视图归一化流的深度计算解剖学
authors: "Tustison, N. J., Avants, B. B., Cook, P. A., Gee, J. C., Stone, J. R."
date: 2026-05-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.723039v2.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 多模态数据集和生物成像
tldr: 本研究提出了一种名为LAMNr流的深度学习框架，旨在解决多模态异构数据中的共享特征提取问题。该方法利用归一化流的精确似然和双射特性，通过潜空间对齐约束，将复杂的生物图像流形展开为连续向量空间。它不仅能学习跨视图的共享子空间，还为计算解剖学中的群体模板和测地线插值提供了深度学习解释，并支持高效的跨视图数据补全。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在通过归一化流在异构多模态数据中学习共享的潜空间，以解决复杂生物图像数据的建模与分析难题。
method: 提出潜空间对齐多视图归一化流（LAMNr），利用形式化对齐约束将共享结构特征与视图特有变异分离。
result: 在成像表型和多模态MRI上的实验证明，该框架能有效进行跨视图归因、潜空间操作及测地线图像插值。
conclusion: 该框架为计算解剖学提供了深度学习基础，并通过开源工具包ANTsTorch促进了高效的数据转换与分析。
---

## 摘要
在建模复杂概率分布时，归一化流在经验数据与可处理的潜空间之间提供了精确似然的双射映射。在此基础上，潜空间对齐多视图归一化（LAMNr）流利用这些显著特性，在异构、多模态数据集之间学习共享的潜子空间，同时将采样的数据流形在拓扑上展开为连续的向量空间。形式化的潜空间对齐约束被用于建模与视图特定变异分离的共享结构特征，从而协调潜投影进入一个共享的几何子空间。通过在生物成像背景下应用这种变换，该框架为基础计算解剖学概念（如群体模板、潜空间距离和测地线成对图像插值）的深度学习解释奠定了潜在基础。此外，所提出的框架实现了闭式条件建模，用于精确的跨视图插补和其他潜空间操作。对影像衍生表型（IDPs）和多模态 MRI 的评估与说明展示了该框架及其潜在应用。为了进一步推动这项工作，我们提供了一个基于 PyTorch 的鲁棒且全面的 2D 和 3D 开源实现，并原生集成到 ANTsX 生态系统（即 ANTsTorch）中，以实现高效的训练以及后续的数据变换、操作和分析。

## Abstract
In modeling complex probability distributions, normalizing flows provide exact-likelihood, bijective mappings between empirical data and tractable latent spaces. Building on this foundation, latent-aligned multiview normalizing (LAMNr) flows leverage these salient properties to learn shared latent subspaces across heterogeneous, multimodal datasets while simultaneously topologically unfolding the sampled data manifold into a continuous vector space. Formal latent-alignment constraints are used to model shared structural features separate from view-specific variations, coordinating latent projections into a shared geometric subspace. By applying this transformation in the context of biological imaging, the framework establishes a potential basis for a deep learning interpretation of foundational computational anatomy concepts, such as the population template, latent distances, and geodesic pairwise image interpolation. Additionally, the proposed framework enables closed-form conditional modeling for exact cross-view imputation and other latent space manipulations. Evaluations and illustrations on both imaging-derived phenotypes (IDPs) and multimodal MRI demonstrate the proposed framework and potential applications. To further motivate our work, we provide a robust and comprehensive, 2D and 3D open-source implementation in PyTorch, natively integrated with the ANTsX ecosystem (i.e., ANTsTorch) for efficient training and subsequent data transformation, manipulation, and analysis.