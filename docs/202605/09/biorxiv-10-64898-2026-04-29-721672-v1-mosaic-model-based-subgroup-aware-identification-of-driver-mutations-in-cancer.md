---
title: "MOSAIC: Model-based, Subgroup-Aware Identification of Driver Mutations in Cancer"
title_zh: MOSAIC：基于模型且感知子群的癌症驱动突变识别
authors: "Campbell, K., Reyna, M. A."
date: 2026-05-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.29.721672v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 癌症基因组学中驱动突变的识别
tldr: 在癌症基因组学中，基因间的互斥模式常预示其生物学关联，但现有方法难以区分真实的生物学互斥与由患者亚群异质性引起的虚假信号。本文提出MOSAIC统计框架，通过对患者亚群异质性建模，有效增强了特定亚群的互斥信号并减少了结构性干扰。实验证明，MOSAIC在识别驱动突变和患者分层方面优于现有方法，并已开源。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决现有互斥分析方法无法区分生物学意义上的互斥与由患者亚群异质性导致的虚假互斥信号的问题。
method: 提出了一种名为MOSAIC的新型统计框架，该框架通过在互斥分析中对患者亚群的异质性进行建模来识别驱动突变。
result: 在模拟和真实数据中，MOSAIC成功增强了特定亚群的互斥信号，并有效减少了由组织学亚型等结构因素产生的干扰信号。
conclusion: MOSAIC在患者亚群分层和驱动突变识别方面比现有方法更具效力，为癌症基因组学研究提供了有力的工具。
---

## 摘要
在癌症基因组学中，基因组内互斥的重复模式可以指示共同的生物学背景以及参与肿瘤发生的过程。然而，现有方法并非旨在区分源于有意义的生物相互作用的互斥性与受潜在患者亚群异质性影响的互斥性。在这项工作中，我们介绍了 MOSAIC，这是一个在互斥性分析中对患者亚群异质性进行建模的新型统计框架。在模拟数据和来自癌症基因组图谱（TCGA）的真实数据实验中，我们展示了 MOSAIC 增强了特定亚群的互斥信号，包括年轻低级别胶质瘤患者中 IDH1 和 IDH2 之间的信号，同时减少了由潜在亚群结构产生的信号影响，例如与子宫内膜癌组织学亚型相关的不同基因组谱系。最后，我们证明了 MOSAIC 在患者亚群分层方面比现有的 p 值组合方法更强大。MOSAIC 作为一个开源工具可在 https://github.com/reynalab/mosaic 获取。

## Abstract
In cancer genomics, recurrent patterns of mutual exclusivity within a gene set can indicate shared biological context and involvement in tumorigenesis. However, existing methods are not designed to distinguish between mutual exclusivity arising from meaningful biological interactions from those influenced by heterogeneity between underlying patient subpopulations. In this work, we introduce MOSAIC, a novel statistical framework that models patient subgroup heterogeneity in mutual exclusivity analyses. In experiments with simulated data and real data from The Cancer Genome Atlas, we show that MOSAIC amplifies subgroup-specific mutual exclusivity signals, including between IDH1 and IDH2 in young low grade glioma patients, while reducing the effect of signals produced by underlying subgroup structures, such as distinct genomic lineages associated with histological subtypes of endometrial cancer. Finally, we demonstrate that MOSAIC is more powerful than existing p-value combination methods for patient subgroup stratification. MOSAIC is available as an open-source tool at https://github.com/reynalab/mosaic.