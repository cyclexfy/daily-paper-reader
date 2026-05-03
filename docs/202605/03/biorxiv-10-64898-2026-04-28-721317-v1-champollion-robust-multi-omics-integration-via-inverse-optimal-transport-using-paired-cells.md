---
title: "CHAMPOLLION: Robust Multi-Omics Integration via Inverse Optimal Transport Using Paired Cells"
title_zh: CHAMPOLLION：通过配对细胞利用逆最优传输实现稳健的多组学整合
authors: "Samaran, J., Peyre, G., Cantini, L."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721317v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 整合多个分子层和跨模态度量学习
tldr: 本研究提出CHAMPOLLION，一种基于正则化最优传输的多组学集成方法。针对现有桥接集成方法解释性差且对参考数据规模敏感的问题，该方法通过学习可解释的跨模态度量来对齐非配对细胞，并捕捉分子特征间的关系。在RNA-蛋白质和RNA-ATAC数据集上的实验证明其在小样本和未知细胞类型下表现优异，并能揭示如CD18和MEF2C等生物学关联。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的多组学桥接集成方法缺乏可解释性，且在配对参考数据规模有限或覆盖不足时表现不稳定。
method: 利用正则化最优传输学习可解释的跨模态度量，驱动非配对细胞对齐并捕捉分子特征间的相互作用。
result: 在多项基准测试中优于现有方法，即使在配对细胞极少或存在未知细胞类型的情况下也能保持高精度。
conclusion: CHAMPOLLION不仅实现了稳健的多组学对齐，还能通过揭示跨模态分子关系为生物学研究提供新见解。
---

## 摘要
全面捕捉细胞身份需要整合多个分子层级。桥接整合（Bridge integration），即利用配对的多组学参考数据集来对齐单模态数据集，已成为一种实用的解决方案。然而，现有方法的可解释性有限，且在不使用正则化的情况下利用配对信息，使其对样本量和覆盖范围的限制较为敏感。我们提出了 CHAMPOLLION，它利用正则化最优传输来学习一种可解释的跨模态度量，在捕捉分子特征之间关系的同时，驱动非配对细胞的对齐。在 RNA-蛋白质和 RNA-ATAC 数据集上的基准测试表明，CHAMPOLLION 优于现有方法，在配对细胞较少的情况下仍能保持准确，甚至能泛化到未见过的细胞类型。除了对齐之外，CHAMPOLLION 还揭示了具有生物学意义的跨模态关系：在单细胞 RNA-蛋白质数据中，它强调了 CD18 在多种癌症中的潜在作用；在结合了 scRNA-seq 和 scATAC-seq 的人类扁桃体图谱中，它表明 MEF2C 可能在脑部以外（特别是浆细胞样树突状细胞中）调节炎症反应。

## Abstract
Fully capturing cellular identity requires integrating multiple molecular layers. Bridge integration, i.e. aligning unimodal datasets using a paired multi-omic reference, has emerged as a practical solution, yet existing methods offer limited interpretability and use paired information without regularization, making them sensitive to limited size and coverage. We introduce CHAMPOLLION, which uses regularized optimal transport to learn an interpretable cross-modal metric that drives the alignment of unpaired cells while capturing relationships between molecular features. Benchmarks on RNA-protein and RNA-ATAC datasets show that CHAMPOLLION outperforms existing approaches, remaining accurate with few paired cells and even generalizing to unseen cell types. Beyond alignment, CHAMPOLLION reveals biologically meaningful cross-modal relationships, highlighting in scRNA-protein data a potential role for CD18 across multiple cancers, and, in a human tonsil atlas combining scRNA-seq and scATAC-seq, suggesting that MEF2C may regulate inflammatory responses beyond the brain, notably in plasmacytoid dendritic cells.