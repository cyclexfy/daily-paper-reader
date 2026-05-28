---
title: Domain-adversarial learning predicts clinically actionable drug combination synergy in leukemia patients using bulk transcriptomics data
title_zh: 域对抗学习利用批量转录组数据预测白血病患者临床可行的药物组合协同作用
authors: "Zhu, J., Kong, W., Do, T. H. L., Kummer, S., Kivioja, J., Romero-Becerra, R., Rousu, J., Miihkinen, M., Tyner, J., Zenz, T., Aittokallio, T."
date: 2026-05-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.18.725869v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 利用域对抗学习预测白血病药物协同作用
tldr: 针对深度学习的药物协同预测模型因依赖细胞系数据而难以反映患者异质性的问题，本文提出领域对抗神经网络(DANN)用于个性化药物协同预测。DANN通过领域对抗学习校正细胞系与患者数据分布差异，在AML和CLL样本中提升预测准确性，并优先识别临床可操作的高置信度组合（如venetoclax方案），为精准血液学提供可靠工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有深度学习药物协同预测模型依赖细胞系数据，无法捕捉患者转录组特征和表型反应的异质性，导致跨领域预测精度不足。
method: 提出领域对抗神经网络(DANN)，通过对抗训练使特征提取器混淆细胞系与患者领域，同时维持协同预测任务，实现跨领域共性特征学习。
result: 在AML和CLL样本中，DANN在真实数据约束下显著提升预测准确性，且预测的协同组合与临床常用方案（如venetoclax）高度吻合，同时提供不确定性估计以筛选高置信度预测。
conclusion: DANN提供了一种系统化方法，通过领域适应和不确定性量化提升药物协同预测的准确性和可靠性，推动精准血液学临床转化。
---

## 摘要
深度学习在药物组合协同作用预测中越来越受欢迎；然而，深度学习模型需要来自细胞系药物基因组筛选的大规模训练数据集，这些数据集难以捕捉患者中观察到的转录组特征和表型反应的异质性。为此，我们开发了一种域对抗神经网络（DANN）用于个性化药物协同作用预测，该网络考虑了细胞系和患者领域之间的系统性差异。在应用于AML和CLL患者样本时，我们展示了DANN如何在现实数据约束下提高预测准确性。模型预测显示，临床使用的组合（如基于venetoclax的方案）具有更高的协同作用，支持其识别具有药学和临床意义的组合的能力。DANN估计预测不确定性并优先考虑高置信度的组合预测，以帮助临床转化。总之，DANN提供了一种系统的方法来提高跨领域药物协同作用预测的准确性和可靠性，推动了与精准血液学转化要求相一致的方法的发展。

## Abstract
Deep learning has gained popularity in drug combination synergy prediction; however, DL models require large training datasets from cell line pharmacogenomic screens that poorly capture the heterogeneity in transcriptomic features and phenotypic responses seen in patients. To that end, we developed a domain-adversarial neural network (DANN) for personalized drug synergy prediction that accounts for systematic differences between cell line and patient domains. In applications to AML and CLL patient samples, we demonstrate how DANN boosts prediction accuracy under realistic data constraints. The model predictions demonstrated elevated synergy among clinically used combinations, such as venetoclax-based regimens, supporting its ability to identify both pharmaceutically and clinically meaningful combinations. DANN estimates prediction uncertainty and prioritizes high-confidence combination predictions to aid clinical translation. Together, DANN provides a systematic approach to improving accuracy and reliability in cross-domain drug synergy prediction, advancing the development of methods that are aligned with the translational requirements of precision hematology.