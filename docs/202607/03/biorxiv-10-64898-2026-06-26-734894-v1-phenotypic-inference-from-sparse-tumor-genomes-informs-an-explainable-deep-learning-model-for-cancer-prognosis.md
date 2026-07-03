---
title: Phenotypic inference from sparse tumor genomes informs an explainable deep-learning model for cancer prognosis
title_zh: 从稀疏肿瘤基因组推断表型为可解释的癌症预后深度学习模型提供信息
authors: "Grant, S., Nath, A."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.26.734894v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 利用基因组数据进行深度学习癌症预后预测
tldr: 针对癌症体细胞变异临床效用有限及AI模型可解释性差的问题，提出PhenoMap框架从稀疏基因组中推断肿瘤表型状态，结合PhenoSurv深度生存模型进行预后预测。在9000个泛癌样本上表现优于现有方法，并揭示NOTCH1、SMARCA4、TGFb等关键预后因子。为精准肿瘤学提供了准确、可解释且临床可操作的决策支持工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有AI模型缺乏可解释性，难以捕捉基因组-表型交互，限制临床转化。
method: 基于9000个泛癌基因组和转录组，PhenoMap推断表达通路评分和表型特征，PhenoSurv整合重构损失、KL散度和生存损失进行学习。
result: PhenoSurv优于现有生存模型，发现NOTCH1/SMARCA4预测HR+乳腺癌，TGFb/FAT1预测肺腺癌，PI3K/肌醇代谢驱动脑癌预后。
conclusion: PhenoMap与PhenoSurv为精准肿瘤学提供准确、可解释且临床可操作的模型。
---

## 摘要
体细胞基因组改变在癌症中被广泛分析，并且仍是个性化治疗的主要来源，但其临床效用仅限于少数可操作的靶点。AI/ML模型提供了捕捉全基因组复杂性的机会，但临床转化受到可解释性差的阻碍，通常限于单基因效应，并忽略了高阶表型相互作用。为解决这一问题，我们开发了PhenoMap，一个从体细胞变异推断肿瘤表型状态的机器学习框架。基于9000个泛癌基因组和转录组训练，PhenoMap准确重建了基于表达的通路富集分数和整合的标志性癌症表型，实现了在表型、通路和基因尺度上的多层次解释。PhenoMap捕获了乳腺癌、肺癌和脑癌的分子亚型和关键耐药通路。我们在PhenoSurv中利用了这些特征，PhenoSurv是一个深度生存模型，整合了表型重建损失、Kullback-Leibler散度和生存损失，以学习生物学基础的预测因子。PhenoSurv优于最先进的生存模型，同时提供了稳健的机制解释。NOTCH1信号传导和SMARCA4突变成为激素受体阳性乳腺癌的主要预后因素。TGFb信号传导和炎症小体（可能由FAT1调节）预测了肺腺癌结局，而肌醇代谢和PI3K信号传导是脑癌的关键驱动因素。总之，PhenoMap和PhenoSurv为精准肿瘤学提供了准确、可解释且临床可操作的模型。

## Abstract
Somatic genomic alterations are widely profiled in cancer and remain the primary source for personalized therapy, yet their clinical utility is limited to few actionable targets. AI/ML models offer opportunities to capture genome-wide complexities, but clinical translation is hindered by poor interpretability, often limited to single-gene effects, and overlooks higher-order phenotypic interactions. To address this, we developed PhenoMap, a machine-learning framework that infers tumor phenotypic states from somatic variants. Trained on 9,000 pan-cancer genomes and transcriptomes, PhenoMap accurately reconstructs expression-based pathway enrichment scores and consolidated hallmark cancer phenotypes, enabling multilevel interpretation at phenotype, pathway, and gene scales. PhenoMap captured molecular subtypes and key resistance pathways across breast, lung, and brain cancers. We leveraged these features in PhenoSurv, a deep survival model integrating phenotypic reconstruction loss, Kullback-Leibler divergence, and survival loss to learn biologically-grounded predictors. PhenoSurv outperformed state-of-the-art survival models while providing robust mechanistic explanations. NOTCH1 signaling and SMARCA4 mutations emerged as a major prognostic factor in hormone receptor-positive breast cancer. TGFb signaling and inflammasomes, potentially modulated by FAT1, predicted lung adenocarcinoma outcomes, while inositol metabolism and PI3K signaling were key drivers in brain cancer. Together, PhenoMap and PhenoSurv provide accurate, interpretable, and clinically actionable models for precision oncology.