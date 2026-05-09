---
title: Cross-assay RNA modeling reveals cancer biomarkers
title_zh: 跨平台RNA建模揭示癌症生物标志物
authors: "Townsend, H. A., Jordan, K. R., Wolsky, R. J., Van Kleunen, L. B., Davidson, N. R., Behbakht, K., Sikora, M. J., Dowell, R. D., Clauset, A., Bitler, B. G."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.722009v1.full.pdf"
tags: ["query:cpath"]
score: 6.5
evidence: 整合转录组学平台用于癌症生物标志物发现
tldr: "针对癌症临床异质性和跨平台数据整合难题，本研究以高级别浆液性癌（HGSC）为模型，系统评估了bulk/单细胞RNA-seq、NanoString及芯片数据的整合策略。通过开发新的协调方法，研究成功整合了RNA-seq与NanoString数据，构建了预测疾病复发的高准确度模型（AUROC > 0.8），并识别出GBP4作为免疫重塑的关键生物标志物，为异质性癌症的精准医疗提供了跨平台建模框架。"
source: biorxiv
selection_source: fresh_fetch
motivation: 癌症的临床异质性和不同检测平台间的系统偏差限制了可靠生物标志物的发现。
method: 通过对比多种转录组平台数据并生成配对的新数据集，开发了跨平台的协调策略与预测模型。
result: 成功构建了预测复发准确率超过0.8的模型，并发现GBP4是反映免疫重塑和细胞毒性的关键预测因子。
conclusion: 本研究提供了一套整合多源转录组数据的框架，显著提升了异质性癌症的预测建模能力和生物标志物鉴定。
---

## 摘要
癌症的临床异质性对精准医学提出了重大挑战。跨不断发展的检测平台的有限队列规模阻碍了可靠的生物标志物发现。在此，我们系统地评估了如何整合来自四种转录组学平台的数据：大体（bulk）和单细胞（sc）RNA测序（RNA-seq）、NanoString以及微阵列（microarray），用于癌症的预测建模。我们以输卵管-卵巢来源的高级别浆液性癌（HGSC）作为模型系统，因为它在生物学和检测数据方面都具有高度的异质性。我们发现，在具有匹配的新辅助化疗前后样本的患者中使用基因表达的倍数变化可以减少患者间和检测间的变异性，但不足以克服平台特有的偏差。微阵列和单细胞RNA-seq数据表现出系统性偏差，而RNA-seq和NanoString在合并为单一训练队列方面表现出最大的潜力。为了减轻跨检测的局限性，我们生成了一个包含同时使用RNA-seq和NanoString进行分析的HGSC肿瘤样本的新数据集，并利用它来确定检测限和最佳协调策略。我们的方法能够整合队列，用于疾病复发的独立和组合RNA-seq及NanoString预测模型（测试集AUROC > 0.8），并在外部微阵列队列中得到了验证。我们利用基于单细胞和大体RNA-seq网络的分析，为预测模型中的基因提供机制背景。我们的模型表明，GBP4表达是复发的关键预测因子，并标志着向细胞毒性方向的免疫重塑。我们提供了一个交互式网络门户，以促进数据和结果的探索。这些发现指导了转录组数据的跨检测协调，并能够改进异质性癌症的预测建模。意义声明：我们提出了一个整合RNA-seq、NanoString、微阵列和单细胞转录组数据进行预测建模的框架，实现了异质性癌症中稳健的生物标志物发现，并将GBP4鉴定为免疫重塑的标志物。

## Abstract
The clinical heterogeneity of cancer poses a major challenge for precision medicine. Limited cohort sizes across evolving assay platforms impede reliable biomarker discovery. Here, we systematically evaluate how to integrate data from four transcriptomics platforms: bulk and single-cell (sc) RNA sequencing (RNA-seq), NanoString, and microarray for predictive modeling in cancer. We use high-grade serous carcinoma (HGSC) of tube-ovarian origin as a model system, as it is highly heterogeneous in both biology and assay data.

We find that using fold-change of gene expression in patients with matched pre- and post-neoadjuvant chemotherapy samples reduces inter-patient and inter-assay variability but is insufficient to overcome platform-specific biases. Microarray and scRNA-seq data exhibit systematic biases, while RNA-seq and NanoString show the most promise for combination into a single training cohort. To mitigate inter-assay limitations, we generate a new data set of HGSC tumor samples profiled with both RNA-seq and NanoString, and use it to identify the limits of detection and optimal harmonization strategies. Our approaches enable integration of cohorts for separate and combined RNA-seq and NanoString predictive models of disease recurrence (test-set AUROCs > 0.8), validated in external microarray cohorts.

We leverage single-cell and bulk RNA-seq network-based analyses to provide mechanistic context for genes in the predictive models. Our models indicate that GBP4 expression is a key predictor of recurrence and marks immune remodeling towards cytotoxicity. We provide an interactive web portal to facilitate exploration of data and results. These findings guide cross-assay harmonization of transcriptomic data and enable improved predictive modeling in heterogeneous cancers.

Statement of SignificanceWe present a framework for integrating RNA-seq, NanoString, microarray, and single-cell transcriptomic data for predictive modeling, enabling robust biomarker discovery in heterogeneous cancers and identifying GBP4 as a marker of immune remodeling.