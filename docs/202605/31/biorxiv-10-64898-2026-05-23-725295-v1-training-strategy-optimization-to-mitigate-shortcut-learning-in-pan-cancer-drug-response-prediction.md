---
title: Training Strategy Optimization to Mitigate Shortcut Learning in Pan-Cancer Drug Response Prediction
title_zh: 训练策略优化以减轻泛癌药物反应预测中的捷径学习
authors: "Shimamoto, K., Ito, T., Lysenko, A., Tsunoda, T."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.23.725295v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 泛癌药物反应预测
tldr: "域适应模型在泛癌药物响应预测中依赖癌症类型区分而非药物敏感性，导致高泛癌精度掩盖特定类型性能差。根源是训练数据中血液癌细胞系过度响应造成类不平衡。提出在CODE-AE框架下结合适度过采样（30%非响应者比例）与类别权重调整，在5/11个外部患者队列中显著提升预测准确性。表明纠正类不平衡比直接排除不平衡亚型更有效，联合优化数据组成与平衡策略是关键。"
source: biorxiv
selection_source: fresh_fetch
motivation: 发现域适应模型在泛癌药物响应预测中因癌症类型类不平衡出现捷径学习，仅区分癌症类型而非学习药物敏感性。
method: "在CODE-AE框架下，结合排除不平衡癌症类型与调整类平衡，采用适度过采样（30%非响应者比例）加类别权重。"
result: "适度过采样（30%非响应者比例）加类别权重在5/11个外部患者队列中显著提升预测准确性。"
conclusion: 纠正类不平衡比直接排除不平衡亚型更有效，联合优化训练数据组成与平衡策略对构建稳健泛癌模型至关重要。
---

## 摘要
背景
体内药物反应预测是精准医学中的一个核心挑战，但标记临床数据的稀缺性仍然需要使用大规模癌细胞系资源进行模型训练。领域自适应方法旨在通过对齐跨领域的特征分布，将从源领域（细胞系）学到的知识迁移到目标领域（患者），这是一种有前景的方法，用于弥合体外模型与体内患者之间的差距。然而，我们观察到这些方法在泛癌评估指标与癌症类型特异性预测准确性之间可能存在显著差异。这种性能差距值得对其潜在预测特征进行详细研究。

结果
我们发现训练数据中癌症类型特异性的类别不平衡会导致领域自适应模型陷入捷径学习，即模型主要区分癌症类型，而不是捕捉药物敏感性的实际生物学决定因素。为了解决这一问题，我们提出了一种结合两种方法的策略：（1）从训练数据中排除导致不平衡的癌症类型，（2）通过过采样和类别加权调整类别平衡，同时保留导致不平衡的癌症类型。在与CODE-AE（上下文感知去混叠自编码器）框架结合测试的所有配置中，适度过采样（30%非响应者比例）与类别加权的组合取得了最佳性能，在来自TCGA和GEO的11个外部患者队列中，有5个队列的预测准确性显著提高。

结论
我们的发现表明，适当的类别不平衡校正——而非全面排除不平衡的癌症亚型——能够有效利用跨癌症类型共享的生物学相关信息进行药物反应预测。本研究强调了在开发用于精准医学应用的稳健泛癌药物反应预测模型时，联合优化训练数据组成和类别平衡调整策略的关键重要性。

亮点
- 发现了当前药物反应预测领域自适应模型中的一个关键差异：高泛癌准确性常常掩盖了特定癌症类型内的较差性能。
- 揭示了根本原因为“捷径学习”，模型倾向于区分癌症组织类型（血液肿瘤 vs. 实体瘤）而非学习个体药物敏感性。
- 发现训练数据中存在严重的类别不平衡，血液肿瘤细胞系在多种化疗药物中表现出不成比例的药物响应性。
- 提出了一种与架构无关的修复方法，使用CODE-AE框架：适度过采样（30%少数类比例）结合类别加权。
- 在11个外部患者队列中的5个队列中展示了显著改进，表明校正类别偏差比简单地排除有问题数据更有效。

## Abstract
BackgroundPrediction of in vivo drug response is a central challenge in precision medicine, but the scarcity of labeled clinical data still necessitates the use of large-scale cancer cell line resources for model training. Domain adaptation methods, which aim to transfer knowledge learned from a source domain (cell lines) to a target domain (patients) by aligning feature distributions across domains, are a promising approach to bridge the gap between in vitro models and in vivo patients. However, we observed that these methods can exhibit a significant discrepancy between pan-cancer evaluation metrics and cancer type-specific prediction accuracy. This performance gap warrants a detailed investigation into their underlying predictive characteristics.

ResultsWe discovered that cancer-type-specific class imbalances in training data can lead domain adaptation models to engage in shortcut learning, where they primarily discriminate between cancer types rather than capturing the actual biological determinants of drug sensitivity. To address this, we propose a strategy of combining two approaches: (1) excluding cancer types causing imbalance from the training data, and (2) adjusting class balance through oversampling and class weighting while retaining cancer types causing the imbalance. Among all configurations tested in conjunction with the CODE-AE (Context-aware Deconfounding AutoEncoder) framework, the combination of moderate oversampling (30% non-responder ratio) with class weighting achieved the best performance, significantly improving prediction accuracy in 5 out of 11 external patient cohorts from TCGA and GEO.

ConclusionsOur findings demonstrate that appropriate class imbalance correction--rather than wholesale exclusion of imbalanced cancer subtypes--enables effective utilization of biologically relevant information shared across cancer types for drug response prediction. This study highlights the critical importance of jointly optimizing training data composition and class balance adjustment strategies in developing robust pan-cancer drug response prediction models for precision medicine applications.

HighlightsO_LIIdentified a critical discrepancy in current domain adaptation models for drug response prediction: high pan-cancer accuracy often masks poor performance within specific cancer types.
C_LIO_LIRevealed the root cause as "shortcut learning," where models tend to distinguish between cancer tissue types (hematological vs. solid) rather than learning individual drug sensitivity.
C_LIO_LIDiscovered severe class imbalance in training data, with hematological cell lines being disproportionately drug-responsive across multiple chemotherapeutics.
C_LIO_LIProposed an architecture-agnostic fix using the CODE-AE framework: moderate oversampling (30% minority ratio) combined with class weighting.
C_LIO_LIDemonstrated significant improvements in 5 of 11 external patient cohorts, showing that correcting class bias is more effective than simply excluding problematic data.
C_LI