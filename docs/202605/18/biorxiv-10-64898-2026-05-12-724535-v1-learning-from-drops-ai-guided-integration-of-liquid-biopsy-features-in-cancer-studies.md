---
title: "Learning from Drops: AI-Guided Integration of Liquid Biopsy Features in Cancer Studies"
title_zh: 滴水见微：人工智能引导的癌症研究中液体活检特征整合
authors: "Andueza, M., Villoslada-Blanco, P., De Dreuille, B., Alonso, L., Sabroso-Lasa, S., Pantel, K., Alix-Panabieres, C., Lopez de Maturana, E., Malats, N."
date: 2026-05-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.12.724535v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: AI引导的癌症研究中液体活检特征整合
tldr: 本研究针对癌症早期检测和监测的需求，探讨了液体活检（LB）与人工智能（AI）的结合。由于高通量测序产生的数据量巨大且复杂，AI成为整合这些信息的关键。文章评估了当前AI在LB领域的应用现状，并提出了一套完整的方法论指南，涵盖从研究设计、数据预处理（如归一化和批次校正）到机器学习模型选择及验证的各个环节，旨在提升生物标志物的敏感性并推动临床转化。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决液体活检产生的大规模复杂数据难以有效整合的问题，利用AI提升癌症检测的精准度。
method: 调研了现有文献并构建了一套包含数据清洗、特征提取、深度学习模型构建及内外部验证的标准化流程。
result: 明确了AI在处理液体活检多维特征中的关键作用，并提供了应对缺失数据、离群值及模型解释性挑战的具体工具和策略。
conclusion: 为液体活检科研社区提供了系统性的AI指导框架，有助于弥合技术差距并加速AI驱动的癌症诊断研究。
---

## 摘要
癌症是全球主要的健康问题，其发病率和死亡率不断上升。早期检测、肿瘤表征和疾病监测对于及时有效的治疗至关重要，最终能降低死亡率。液体活检 (LB) 已成为一种有价值的检测工具，提供了一种非侵入性方法来测定体液中源自肿瘤的生物标志物，并展现出显著的转化潜力。为了提高生物标志物的灵敏度，高通量测序平台产生了海量数据。人工智能 (AI) 在实现庞大且复杂的数据整合方面发挥着关键作用。本研究旨在评估液体活检领域基于 AI 的整合研究现状，并提供方法学指导。首先，我们通过 PubMed 检索发现，整合液体活检特征的研究文献较少，尤其是应用 AI 的研究。在采用 AI 方法时，明确研究目标对于指导后续的方法学环节至关重要，包括研究设计、患者筛选标准、样本量、液体活检特征的性质以及待收集的元数据。具体而言，我们提出了数据预处理的策略和工具，包括归一化和批次校正，以及异常值和缺失数据的处理。此外，我们推荐了多种用于特征选择的机器学习/深度学习方法，以确保模型的鲁棒性，并强调了对所选模型进行严格内部和外部验证的重要性。评估临床实用性和可解释性往往被忽视，但对于实际应用至关重要。总之，我们为液体活检科学界提供了一套基于 AI 的方法学指南，旨在架起这两个领域的桥梁，并增强液体活检特征的整合分析。

## Abstract
Cancer is a major global health issue with rising incidence and mortality. Early detection, tumor characterization, and disease surveillance are crucial for timely and effective treatment, ultimately reducing mortality rates. Liquid biopsy (LB) has emerged as a valuable detection tool offering a non-invasive method to determine tumor-derived biomarkers in body fluids with demonstrated translational potential. To increase biomarker sensitivity, high-throughput sequencing platforms deliver massive volumes of data. Artificial Intelligence (AI) is pivotal in enabling huge and complex data integration. This contribution aims to assess the current state of integrative AI-based research in the LB field and provide methodological guidance. First, we conducted a PubMed search and found that the literature is sparse in studies integrating LB features, particularly by applying AI. When adopting the latter approach, defining the study objectives is crucial to guide the subsequent methodological aspects, including study design, patient selection criteria, sample size, nature of the LB features, and metadata to collect. Specifically, we propose strategies and tools for data preprocessing, including normalization and batch correction, as well as handling outliers and missing data. Furthermore, we recommend various Machine/Deep Learning approaches for feature selection techniques to ensure model robustness, and we highlight the importance of undergoing rigorous internal and external validations of the selected models. Assessing clinical utility and interpretability is often overlooked but fundamental for real-world implementation. In conclusion, we provide the LB scientific community with an AI-based methodological guidance to bridge the two fields and enhance the integrative analysis of LB features.