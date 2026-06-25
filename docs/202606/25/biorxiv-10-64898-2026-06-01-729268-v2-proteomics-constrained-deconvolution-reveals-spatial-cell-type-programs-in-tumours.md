---
title: Proteomics-constrained deconvolution reveals spatial cell-type programs in tumours
title_zh: 蛋白质组学约束的反卷积揭示肿瘤中的空间细胞类型程序
authors: "Isik, E. B., Haley, M. J., Anbaki, A. A., Bere, L., Roncaroli, F., Piper Hanley, K., Couper, K., Wedge, D. C., Sellers, R., Baker, A., Oliveira, P., Ashton, J., Bristow, R. G., Alvarez, M. A., Georgaka, S., Rattray, M."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729268v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 利用蛋白质组学约束的空间转录组解卷积用于肿瘤分析
tldr: 空间转录组学解析细胞类型混合物具挑战性，尤其肿瘤异质性高且无单细胞参考。本文提出PISTACHIO，一种基于约束非负矩阵分解与负二项似然的蛋白质组学知情空间转录组解卷积方法，通过成像质谱流式导出空间细胞类型约束。相比Cell2location和STdeconvolve，PISTACHIO在合成和真实肿瘤数据中提升空间分布恢复，对细胞类型分配误差稳健，且运行快速。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有解卷积方法依赖高质量单细胞参考、可扩展性差或缺乏可解释性，难以处理肿瘤中混合细胞群体。
method: 提出PISTACHIO，结合成像质谱流式数据导出空间细胞类型约束，采用约束非负矩阵分解与负二项似然，无需概率先验。
result: 在合成和真实肿瘤数据中，PISTACHIO相比Cell2location和STdeconvolve更好恢复空间细胞类型分布，对误差稳健，运行时间短。
conclusion: PISTACHIO为大规模空间转录组学提供可靠、高效且可解释的解卷积框架，揭示了肿瘤空间细胞型程序。
---

## 摘要
准确解析空间转录组学中的细胞类型混合仍然具有挑战性，尤其是在细胞群混合且可能缺乏匹配单细胞参考或对齐不良的异质性肿瘤中。当前的反卷积方法要么需要高质量的单细胞RNA测序参考，要么存在可扩展性限制，或者缺乏可解释性。我们提出了PISTACHIO，一种基于约束非负矩阵分解和负二项似然的蛋白质组学信息空间转录组反卷积框架。PISTACHIO不采用概率先验，而是整合来自配对成像质谱流式技术的空间细胞类型约束，强制执行生物学基础的稀疏性和细胞类型存在的明确空间可行性。与Cell2location和STdeconvolve相比，PISTACHIO在合成和真实肿瘤数据集中改善了空间细胞类型分布的恢复。我们的方法在细胞类型分配错误下保持鲁棒性，在中等噪声下与真实值的相关性保持较高，并在标准硬件上实现快速运行，支持实际大规模部署。

## Abstract
Accurately resolving cell-type mixtures in spatial transcriptomics remains challenging, particularly in heterogeneous tumours where cell populations are intermixed and matched single-cell references may be unavailable or poorly aligned. Current deconvolution approaches either require high-quality scRNA-seq references, suffer from scalability limitations, or lack interpretability. We introduce PISTACHIO, a proteomics-informed spatial transcriptomics deconvolution framework based on constrained non-negative matrix factorization with a negative-binomial likelihood. Rather than using probabilistic priors, PISTACHIO incorporates spatial cell-type constraints derived from paired Imaging Mass Cytometry, enforcing biologically grounded sparsity and explicit spatial feasibility of cell-type presence. PISTACHIO improved recovery of spatial cell-type distributions compared with Cell2location and STdeconvolve across synthetic and real tumour datasets. Our approach remains robust under cell-type assignment errors, maintaining high correlation with ground-truth under moderate noise, and achieves fast runtime on standard hardware, enabling practical large-scale deployment.