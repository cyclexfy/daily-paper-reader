---
title: Predicting subclonal TP53 mutations from tumor spatial transcriptomics data using a graph convolutional neural network
title_zh: 利用图卷积神经网络从肿瘤空间转录组数据预测亚克隆TP53突变
authors: "Luijts, T., Hoogstoel, S., Pappaert, E., De Meester, E., Van Nieuwerburgh, F., Van Hamme, E., De Schepper, S., Willaert, W., Vral, A., Hoorens, I., Van den Eynden, J."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.08.737173v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 从空间转录组数据预测癌症TP53突变
tldr: "空间转录组数据无法直接获取驱动基因突变信息。本文提出MuT-GCNN，一种图卷积神经网络，从空间转录组数据预测TP53亚克隆突变。基于虚拟ST数据和真实DNA测序训练，模型在多种癌症中精准率与召回率超95%，对单次突变敏感。在鳞状细胞癌真实数据中验证，可有效揭示TP53突变空间位置，助力肿瘤异质性研究。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737173-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1506, \"height\": 1667, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737173-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1553, \"height\": 1077, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737173-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1579, \"height\": 814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737173-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1635, \"height\": 1202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737173-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1635, \"height\": 1364, \"label\": \"Figure\"}]"
motivation: 空间转录组数据缺乏体细胞驱动突变信息，需计算方法从表达数据推断突变状态。
method: 采用图卷积神经网络MuT-GCNN，利用虚拟ST和匹配DNA测序数据训练，预测TP53亚克隆。
result: "在多种癌症中精度和召回率超95%，对单次hit突变敏感，主要依赖p53信号基因表达。"
conclusion: MuT-GCNN可从ST数据揭示TP53亚克隆突变位置，为研究肿瘤异质性提供新方法。
---

## 摘要
空间转录组学（ST）革新了我们对肿瘤生物学的理解，但本质上缺乏上游体细胞驱动突变的信息。我们开发了一种空间感知的图卷积神经网络（MuT-GCNN），可直接从ST数据推断TP53克隆。MuT-GCNN通过从大量现有RNA和匹配DNA测序数据模拟克隆的虚拟ST切片进行训练。该模型性能优越，在大多数分析的癌症类型中，精确率和召回率均超过95%。它对单次命中突变敏感，主要受癌细胞中p53信号基因表达的影响。在公开的鳞状细胞癌（SCC）数据上展示了模型潜力后，我们使用从4个皮肤SCC样本获得的连续切片进行ST和匹配DNA测序的直接验证。随着ST数据的日益丰富和即将到来的ST图谱，MuT-GCNN可以揭示TP53（人类癌症中最常突变的基因）亚克隆改变的位置。

## Abstract
Spatial transcriptomics (ST) has revolutionized our understanding of tumor biology but inherently lacks information on the upstream somatic driver mutations. We developed a spatially-aware graph convolutional neural network (MuT-GCNN) that infers TP53 clones directly from ST data. MuT-GCNN was trained on virtual ST slides with clones simulated from a large collection of existing RNA and matched DNA sequencing data. The model is highly performant with precision and recall values exceeding 95% in most analysed cancer types. It is sensitive for single hit mutations and is primarily informed by the expression of p53 signalling genes in cancer cells. After demonstrating the potential of the model on publicly available squamous cell carcinoma (SCC) data, a direct validation was performed using ST and matched DNA sequencing from serial slices obtained from 4 cutaneous SCC samples. With the increasing availability of ST data and upcoming ST atlases, MuT-GCNN can unveil the location of (sub)clonal alterations in TP53, the most frequently mutated gene in human cancer.