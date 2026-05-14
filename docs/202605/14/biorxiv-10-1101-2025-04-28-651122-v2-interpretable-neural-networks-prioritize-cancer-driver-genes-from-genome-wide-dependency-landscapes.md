---
title: Interpretable neural networks prioritize cancer driver genes from genome-wide dependency landscapes
title_zh: 可解释神经网络从全基因组依赖图谱中优先筛选癌症驱动基因
authors: "Yin, Q., Chen, L."
date: 2026-05-10
pdf: "https://www.biorxiv.org/content/10.1101/2025.04.28.651122v2.full.pdf"
tags: ["query:cpath"]
score: 7.5
evidence: 连接突变与通路活性及药物反应的可解释神经网络
tldr: 本研究提出xNNDriver和xAEDriver两个可解释神经网络框架，通过整合DepMap基因依赖性、通路活性和药物反应来识别癌症驱动基因。xNNDriver利用监督学习评估突变的功能足迹，xAEDriver则通过自编码器捕捉组合功能状态。模型成功识别了已知驱动基因并揭示了药物敏感性关联，为癌症机制研究和药物研发提供了高效的假设生成工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 识别癌症驱动基因及其治疗影响是计算癌症生物学中的核心挑战，需要从大规模功能数据中提取可解释的信号。
method: 开发了监督式通路引导模型xNNDriver和无监督自编码器模型xAEDriver，将基因突变与全基因组依赖性景观相连接。
result: 模型成功恢复了已知驱动基因，并发现驱动变异表示与细胞系的药物敏感性及特定生物通路活性显著相关。
conclusion: 研究证明基因依赖性景观包含丰富的致癌功能信息，可解释深度学习为优先排序驱动基因和发现治疗脆弱性提供了新框架。
---

## 摘要
识别癌症驱动基因及其治疗影响仍是计算癌症生物学的核心挑战。我们引入了 xNNDriver 和 xAEDriver，这是两个可解释的神经网络框架，将癌症突变与全基因组 DepMap 基因依赖性、通路活性和药物反应模式联系起来。xNNDriver 是一个监督式通路引导模型，用于评估基因的突变状态是否编码在全基因组依赖图谱中；我们将模型拟合度解释为驱动潜力评分，该评分量化了这种突变-依赖信号的强度，并优先筛选具有广泛功能足迹的基因。在 3,008 个候选基因中，xNNDriver 找回了主要的已知驱动基因，并突出了文献支持的候选基因，而通路分析揭示了与代谢、生长因子信号传导和免疫调节相关的生物学一致程序。为了捕捉组合功能状态，xAEDriver 使用无监督自动编码器来学习驱动变异表示 (DVRs)，即受已知驱动突变频率分布引导的潜在二元特征。DVRs 捕捉细胞系特异性的依赖模式和表达模式，并与药物敏感性和通路活性相关。总之，这些可解释的深度学习模型证明了基因依赖图谱编码了丰富、可解释的致癌功能信号，并为优先筛选驱动基因、通路和治疗漏洞以进行进一步实验验证提供了一个假设生成框架。作者总结：癌症通常由赋予肿瘤细胞生长优势的遗传变化驱动，但发现哪些变化重要以及它们如何影响细胞行为仍然困难。在本研究中，我们利用癌症细胞系的大规模基因编辑数据，探究细胞所依赖的基因模式是否能揭示其癌症驱动改变的信息。我们开发了连接突变模式、细胞生存依赖性和生物通路的可解释神经网络模型。一个模型优先筛选其突变状态在整个细胞中留下清晰功能特征的基因。第二个模型总结了每个细胞系中更广泛的、组合的类驱动状态。这些总结与已知的癌症生物学、组织类型和药物反应差异相关联，表明功能依赖数据包含有关癌症机制的有用线索。通过将突变模式与功能依赖和通路活性联系起来，我们的方法有助于识别候选癌症驱动因素和可解释的药物反应模式，从而指导未来的实验研究。使模型具有可解释性，使研究人员能够从大型筛选数据集转向对癌症驱动过程的生物学解释。

## Abstract
Identifying cancer driver genes and their therapeutic impact remains a core challenge in computational cancer biology. We introduce xNNDriver and xAEDriver, two interpretable neural network frameworks that connect cancer mutations with genome-wide DepMap gene dependencies, pathway activity, and drug-response patterns. xNNDriver is a supervised pathway-guided model that evaluates whether a genes mutation status is encoded in the genome-wide dependency landscape; we interpret model fitness as a driver potential score, which quantifies the strength of this mutation-dependency signal and prioritizes genes with broad functional footprints. Across 3,008 candidate genes, xNNDriver recovers major established drivers and highlights literature-supported candidates, while pathway analyses reveal biologically coherent programs related to metabolism, growth factor signaling, and immune regulation. To capture combinatorial functional states, xAEDriver uses an unsupervised autoencoder to learn Driver Variant Representations (DVRs), latent binary features guided by the frequency distribution of known driver mutations. DVRs capture cell-line-specific dependency patterns and expression patterns and are associated with drug sensitivity and pathway activity. Together, these interpretable deep learning models demonstrate that gene dependency landscapes encode rich, interpretable signals of oncogenic function and provide a hypothesis-generating framework for prioritizing drivers, pathways, and therapeutic vulnerabilities for further experimental validation.

Author summaryCancer is often driven by genetic changes that give tumor cells a growth advantage, but finding which changes matter and how they affect cell behavior remains difficult. In this study, we used large-scale gene-editing data from cancer cell lines to ask whether the pattern of genes a cell depends on can reveal information about its cancer-driving alterations. We developed interpretable neural-network models that connect mutation patterns, cell survival dependencies, and biological pathways. One model prioritizes genes whose mutation status leaves a clear functional signature across the cell. A second model summarizes broader, combined driver-like states in each cell line. These summaries were linked to known cancer biology, tissue type, and differences in drug response, suggesting that functional dependency data contain useful clues about cancer mechanisms. By connecting mutation patterns with functional dependencies and pathway activity, our approach helps identify candidate cancer drivers and interpretable drug-response patterns that can guide future experimental studies. Making the models interpretable allows researchers to move from large screening datasets toward biological explanations of cancer-driving processes.