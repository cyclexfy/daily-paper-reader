---
title: AI-based separation of malignant cell- and microenvironment-specific gene expression from bulk RNA sequencing enhances biomarker interpretation
title_zh: 基于人工智能的从大体RNA测序中分离恶性细胞和微环境特异性基因表达的方法增强了生物标志物的解读
authors: "Zolotar, A., Wiebe, D., Petrosyants, A., Shpak, B., Khotkina, N., Beliaeva, V., Ivleva, E., Balabanian, L., Chelushkin, M., Dyikanov, D., Savchenko, M., Yong, S. T., Litvinov, D., Zotova, A., Kuznetsov, A., Zaitsev, A., Sharun, A., Kosmin, A., Nomie, K., Abdou, M., Sarachakov, A., Bagaev, A."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721082v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 用于个性化癌症诊断和生物标志物解释的机器学习
tldr: 针对大块RNA测序中非恶性肿瘤微环境细胞干扰导致生物标志物解读困难的问题，本研究开发了基于机器学习的工具Helenus。该工具通过在2亿多个合成RNA谱上进行训练，能够精确分离恶性细胞与非恶性细胞的基因表达贡献。实验证明Helenus在识别肿瘤特异性靶点和预测免疫治疗反应方面具有高准确性，为个性化癌症诊断和治疗提供了关键的生物学洞察。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统大块RNA测序受肿瘤微环境细胞干扰，难以准确区分恶性细胞与非恶性细胞的基因表达贡献。
method: 开发了名为Helenus的机器学习工具，利用超过2亿个涵盖多种肿瘤类型和纯度的合成RNA谱进行训练。
result: Helenus实现了高精度的基因表达分离，并成功揭示了拷贝数变异及抗体偶联药物靶点在肿瘤细胞上的特异性表达。
conclusion: Helenus通过精确识别生物标志物的表达来源，显著提升了对肿瘤生物学和免疫治疗反应的理解，助力个性化癌症医疗。
---

## 摘要
基于大体RNA测序（RNA-seq）的基因表达分析是用于个性化癌症诊断、疾病监测和治疗决策的有前景的工具。然而，其临床应用受到非恶性肿瘤微环境细胞干扰的限制，这些细胞在低纯度肿瘤的转录组数据中可能占据主导地位。虽然像Kassandra这样的细胞解卷积方法可以从大体RNA-seq中预测数字化的细胞百分比，但用于描绘肿瘤各组分基因表达贡献的方法仍然有限。为了克服这一局限性，我们开发了Helenus，这是一种基于机器学习的工具，可以分离恶性细胞和非恶性细胞之间的基因表达。Helenus在代表多种肿瘤类型和纯度的超过2亿个合成RNA谱上进行了训练，在分离基因表达来源方面表现出极高的准确性。Helenus还揭示了真实的基因组-RNA相关性，例如拷贝数变异以及治疗性抗体偶联药物靶点在肿瘤细胞上的特异性表达。通过精确识别生物标志物的表达，Helenus为肿瘤生物学和免疫治疗反应提供了关键见解，为更有效的个性化癌症护理铺平了道路。

## Abstract
Bulk RNA sequencing (RNA-seq)-based gene expression analysis is a promising tool for personalized cancer diagnostics, disease monitoring, and treatment decision-making. However, its clinical utility is limited by interference from non-malignant tumor microenvironment cells, which can dominate transcript data in low-purity tumors. While cell deconvolution methods like Kassandra can predict digital cell percentages from bulk RNA-seq, approaches for delineating the gene expression contribution of tumor compartments remain limited. To overcome this limitation, we developed Helenus, a machine-learning-based tool that separates gene expression between malignant and non-malignant cells. Trained on over 200 million synthetic RNA profiles representing diverse tumor types and purities, Helenus demonstrated high accuracy in separating gene expression origin. Helenus also uncovered true genomic-RNA correlations such as copy number alterations and the expression of therapeutic antibody-drug conjugate targets specifically on tumor cells. Helenus provides critical insights into tumor biology and immunotherapy response by precisely identifying biomarker expressions, paving the way for more effective personalized cancer care.