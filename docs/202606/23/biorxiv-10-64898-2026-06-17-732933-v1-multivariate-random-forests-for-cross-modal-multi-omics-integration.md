---
title: Multivariate Random Forests for Cross-Modal Multi-Omics Integration
title_zh: 多变量随机森林用于跨模态多组学整合
authors: "Zhang, W., Wang, L., Franzmann, E. J., Chen, X. S."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.732933v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 使用随机森林进行多组学整合，与基因组和图像数据融合相关
tldr: 多组学整合中，现有方法常合并全部数据导致单层强信号模糊，或依赖线性结构忽略非线性关系。本文提出multiRF方法，利用多元随机森林学习跨组学样本相似性，分解为共享与模态特异成分并分别聚类。模拟显示其优于现有方法，在TCGA头颈癌中共享成分对齐已知亚型，组学特异信号揭示免疫与发育生物学；在ADNI队列中共享信号关联认知衰退，DNA甲基化特异信号提供额外信息。该方法以开源R包发布。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有整合方法无法有效分离跨组学的共享与特异信号，且难以处理非线性关系。
method: 基于多元随机森林计算跨组学样本相似性，组合后回归预测共享成分，残差作为模态特异信号，分别聚类。
result: 模拟中恢复共享簇优于现有方法；TCGA数据共享成分对齐亚型，ADNI数据共享信号关联疾病转化。
conclusion: multiRF能提取公共疾病轴并保留单组学特异性生物学信号。
---

## 摘要
多组学研究广泛应用于生物医学研究的许多领域。在许多疾病中，一些信号在不同数据类型间共享，而另一些则在单一组学层中最强。当前的多组学聚类方法通常将所有数据类型合并为单一表示，这可能会模糊某一层中较强的生物学信号，或者依赖于可能遗漏跨数据类型更复杂关系的线性结构。我们引入multiRF，一种基于随机森林的方法，能处理复杂数据类型并分离多组学数据中的共享和模态特异性结构。multiRF通过多变量随机森林学习跨组学层的样本相似性，跨数据类型组合它们，并使用所得权重估计每个组学层中可由其他层预测的部分。剩余残差被视为模态特异性信号，允许共享和模态特异性的相似性分别聚类。在模拟中，multiRF恢复共享聚类的能力与已建立的整合方法相当或更好，同时在非线性数据结构下更可靠地分离模态特异性信号。在TCGA头颈部鳞状细胞癌中，共享成分与已建立参考分类的主要亚型结构一致，而基因和miRNA特异性成分揭示了额外的免疫和发育生物学。在具有匹配血液DNA甲基化和结构性MRI的ADNI队列中，共享的跨模态老化信号与未来向轻度认知障碍或阿尔茨海默病的转化相关，而DNAm特异性残差信号显示出探索性的额外信息。这些结果表明，multiRF可以恢复共同的疾病轴，同时保留特定于一种数据类型的生物学意义信号。multiRF作为开源R包在https://github.com/novawz/multiRF上提供。

## Abstract
Multi-omics studies are widely used across many areas of biomedical research. In many diseases, some signals are shared across data types, while others are strongest in a single omics layer. Current multi-omics clustering methods often either merge all data types into a single representation, which can blur biology that is strong in one layer, or rely on linear structure that may miss more complex relationships across data types. We introduce multiRF, a random-forest-based method that handles complex data types and separates shared and modality-specific structure for multi-omics data. multiRF learns sample similarities across omics layers from multivariate random forests, combines them across data types, and uses the resulting weights to estimate the part of each omics layer that is predictable from the others. The remaining residual is treated as modality-specific signal, allowing shared and modality-specific similarities to be clustered separately. In simulations, multiRF recovered shared clusters as well as or better than established integrative methods while more reliably separating modality-specific signal under nonlinear data structures. In TCGA head and neck squamous cell carcinoma, the shared component aligned with the main subtype structure across established reference classifications, while gene- and miRNA-specific components revealed additional immune and developmental biology. In the ADNI cohort with matched blood DNA methylation and structural MRI, the shared cross-modal aging signal was associated with future conversion to mild cognitive impairment or Alzheimer's disease, and a DNAm-specific residual signal showed exploratory additional information. These results show that multiRF can recover a common disease axis while retaining biologically meaningful signals specific to one data type. multiRF is available as an open-source R package at https://github.com/novawz/multiRF.