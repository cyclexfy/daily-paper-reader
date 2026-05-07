---
title: Integrated Multi-Omics Analysis for the Identification of Disease-Associated Variations and Prognostic Biomarkers in Triple-Negative Breast Cancer (TNBC)
title_zh: 整合多组学分析用于识别三阴性乳腺癌（TNBC）中疾病相关变异及预后生物标志物
authors: "MANNEKUNTA, N., NATRAJAN, E."
date: 2026-05-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.03.722461v1.full.pdf"
tags: ["query:cpath"]
score: 8.5
evidence: 乳腺癌预后生物标志物的集成多组学分析
tldr: 三阴性乳腺癌（TNBC）具有高度异质性且缺乏靶向疗法。本研究通过整合TCGA队列的转录组和DNA甲基化数据，利用机器学习投票集成模型（LightGBM、随机森林和逻辑回归）构建了预后预测模型。研究识别出包含47个基因的预后特征，并在独立外部数据集中验证了其有效性，为TNBC患者的风险分层和治疗靶点开发提供了具有生物学解释性的多组学框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对三阴性乳腺癌高度异质性且缺乏有效靶向疗法的现状，旨在通过多组学整合分析寻找稳定的预后生物标志物。
method: 整合转录组与DNA甲基化数据，采用由LightGBM、随机森林和逻辑回归组成的机器学习集成模型进行生存预测，并利用SHAP值进行解释。
result: "成功识别出47个基因的预后特征，在外部验证集上达到74.77%的准确率，并揭示了关键的代谢与信号传导通路。"
conclusion: 该多组学机器学习流程能有效识别TNBC预后特征，具有良好的跨平台泛化能力，为临床风险分层和靶向治疗提供了重要参考。
---

## 摘要
背景：三阴性乳腺癌（TNBC）表现出显著的分子异质性，且缺乏针对性的受体疗法。单一组学方法不足以捕捉其复杂的调控机制，因此需要整合多组学框架来识别稳定的预后特征。方法：对来自 TCGA-BRCA 队列的匹配转录组和 DNA 甲基化数据进行归一化和数学整合，以分离疾病相关变异。训练了一个经过校准的机器学习投票集成模型（包括 LightGBM、随机森林和逻辑回归）来预测临床生存情况。通过独立分位数归一化，在独立微阵列队列（GSE58812）上测试了模型的泛化能力。SHAP（SHapley Additive exPlanations）值为生物学解释提供了支持。结果：差异和整合分析确定了一个包含 47 个基因的核心预后特征。集成分类器在未见过的临床患者中实现了 74.77% 的外部验证准确率（AUC 0.590）。SHAP 分析证实了这些特定生物标志物在驱动死亡率方面的生物学方向性。超几何通路富集分析突出了可作为靶点的代谢和信号网络。结论：该多组学机器学习流程识别出了一个对 TNBC 具有高度预后价值的 47 基因特征。该模型展示了强大的跨平台泛化能力，并为患者风险分层和指导未来治疗靶点开发提供了可解释的临床应用价值。

## Abstract
Background: Triple-negative breast cancer (TNBC) exhibits substantial molecular heterogeneity and lacks targeted receptor therapies. Single-omic approaches inadequately capture its regulatory complexity, necessitating integrated multi-omic frameworks to identify stable prognostic signatures. Methods: Matched transcriptomic and DNA methylation data from the TCGA-BRCA cohort were normalised and mathematically integrated to isolate disease-associated variations. A calibrated machine learning voting ensemble (comprising LightGBM, Random Forest, and Logistic Regression) was trained to predict clinical survival. Model generalisability was tested on an independent microarray cohort (GSE58812) using independent quantile normalisation. SHAP (SHapley Additive exPlanations) values provided biological interpretability. Results: Differential and integrative analyses identified a 47-gene master prognostic signature. The ensemble classifier achieved an external validation accuracy of 74.77% (AUC 0.590) on unseen clinical patients. SHAP analysis confirmed the biological directionality of these specific biomarkers in driving mortality. Hypergeometric pathway enrichment highlighted targetable metabolic and signalling networks. Conclusions: This multi-omic machine learning pipeline identifies a highly prognostic 47-gene signature for TNBC. The model demonstrates strong cross-platform generalisability and offers interpretable clinical utility for stratifying patient risk and guiding future therapeutic target development.