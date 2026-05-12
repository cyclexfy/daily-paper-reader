---
title: Clone-level multi-modal prediction of tumour drug response
title_zh: 克隆水平的肿瘤药物反应多模态预测
authors: "Duchemin, Q., Trejo Banos, D., Bertolini, A., Ferreira, P. F., Schill, R., Lienhard, M., Wegmann, R., Tumor Profiler Consortium,, Snijder, B., Stekhoven, D., Beerenwinkel, N., Singer, F., Obozinski, G., Kuipers, J."
date: 2026-05-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.06.723206v1.full.pdf"
tags: ["query:cpath"]
score: 7.5
evidence: 整合DNA和RNA测序的肿瘤药物反应多模态预测
tldr: 肿瘤异质性是精准医疗的挑战，不同克隆对药物反应各异。本文提出scClone2DR框架，通过整合单细胞DNA、RNA测序与体外药筛数据，在克隆层面预测药物反应。该方法在模拟和黑色素瘤、白血病临床样本中表现优异，能识别耐药克隆并提升临床预后预测准确性，为克隆感知的精准肿瘤学奠定了基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 肿瘤内部不同克隆的遗传和表型差异导致其对治疗反应不一，传统的整体预测方法难以应对这种异质性。
method: 开发了名为scClone2DR的概率多模态框架，整合单细胞DNA/RNA测序与体外药物筛选数据进行克隆级预测。
result: 在模拟实验和黑色素瘤及白血病患者样本中，该方法准确识别了异质性克隆反应，并显著提升了临床结果的预测性能。
conclusion: 建模肿瘤进化和克隆多样性对于准确预测药物反应至关重要，是实现更有效精准医疗的关键。
---

## 摘要
肿瘤异质性是精准肿瘤学面临的主要挑战，因为遗传和表型不同的肿瘤克隆对治疗的反应可能不同。为了解决这一问题，我们推出了 scClone2DR，这是一个概率多模态框架，通过整合单细胞 DNA 和 RNA 测序以及离体药物筛选数据，在单个肿瘤克隆水平上预测药物反应。在模拟实验中，scClone2DR 在恢复真实药物效应和克隆敏感性方面显著优于其他替代方案。应用于 60 例黑色素瘤和 21 例急性髓系白血病患者样本时，该方法识别出了异质性的克隆反应，产生了具有生物学意义的特征排名，突出了可能对治疗产生耐药性的克隆，并且与忽略克隆结构的模型相比，提高了对临床结果的预测准确性。这些结果表明，对肿瘤进化和克隆多样性进行建模对于准确预测药物反应至关重要，并为更有效、具备克隆意识的精准肿瘤学奠定了基础。

## Abstract
Tumour heterogeneity presents a major challenge for precision oncology, as genetically and phenotypically distinct tumour clones may respond differently to therapy. To address this, we introduce scClone2DR, a probabilistic multi-modal framework that predicts drug responses at the level of individual tumour clones by integrating single-cell DNA and RNA sequencing with ex-vivo drug-screening data. In simulations, scClone2DR substantially outperforms alternatives in recovering true drug effects and clonal sensitivities. Applied to 60 melanoma and 21 acute myeloid leukaemia patient samples, the method identifies heterogeneous clonal responses, yields biologically meaningful feature rankings, highlights clones that may be resistant to treatment, and improves the prediction of clinical outcomes compared to models ignoring clonal structure. These results demonstrate that modelling tumour evolution and clonal diversity is crucial for accurate drug-response prediction and provides a foundation for more effective, clone-aware precision oncology.