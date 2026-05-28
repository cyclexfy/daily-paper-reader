---
title: Counterfactual Explanations for Graph Neural Networks in Patient Outcome Prediction
title_zh: 图神经网络在患者结局预测中的反事实解释
authors: "Chaidos, N., Dimitriou, A., Calzi, H., Casiraghi, E., Stamou, G., Valentini, G."
date: 2026-05-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.18.725906v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 可解释图神经网络用于癌症患者预后预测
tldr: 反事实解释算法在表格医疗数据上成功，但缺乏对患者相似性网络（PSN）中图神经网络（GNN）预测的解释。本文提出首个针对PSN的CE算法，采用对比GNN主干和模型无关的反事实搜索方法，在合成数据和阿尔茨海默病队列上取得了与基线方法相竞争的结果，填补了医疗网络可解释性空白。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有CE算法主要针对表格数据，缺乏对PSN中GNN预测的解释方法。
method: 提出结合对比GNN主干和模型无关反事实搜索的CE算法，用于解释PSN中的诊断和预后预测。
result: 在合成数据和阿尔茨海默病患者队列上，该算法与表格CE算法及GNNExplainer表现相当。
conclusion: 首次为PSN提供反事实解释，具有竞争力，可解释GNN在医疗网络中的预测。
---

## 摘要
反事实解释（CE）算法已成功应用于揭示表格医疗数据中驱动计算诊断和预后预测的主要因素。最近，一种新的网络医学范式被引入用于患者诊断和预后，使用患者相似性网络（PSNs），即患者作为节点、其临床和生物分子相似性作为边的图。在此背景下，包括图神经网络（GNNs）在内的基于图的算法可以利用个体患者特征以及他们在临床和生物分子相似个体网络中的关系进行预测。在这项工作中，我们提出了第一个专门用于解释PSNs中诊断和预后预测的CE算法。除了对比GNN主干外，我们引入了一种通用的、与模型无关的反事实搜索方法，该方法与任何底层分类器兼容。在合成数据和一组阿尔茨海默病患者的初步结果表明，我们的算法在与经典的基于表格的CE算法以及用于解释基于图的分类任务的成熟方法GNNExplainer相比，具有竞争力。

## Abstract
Counterfactual Explanation (CE) algorithms have been successfully applied to uncover the main factors driving computational diagnostic and prognostic predictions on tabular medical data. Recently, a new Network Medicine paradigm has been introduced for patient diagnosis and prognosis using Patient Similarity Networks (PSNs), i.e. graphs where patients are represented as nodes and their clinical and biomolecular similarities as edges. In this context, graph-based algorithms, including Graph Neural Networks (GNNs), can provide predictions using not only individual patient features but also their relations within a network of clinically and biomolecularly similar individuals. In this work, we propose the first CE algorithm tailored to explain diagnostic and prognostic predictions within PSNs. Alongside a contrastive GNN backbone, we introduce a versatile, model-agnostic counterfactual search method compatible with any underlying classifier. Preliminary results on synthetic data and on a cohort of patients affected by the Alzheimers disease show that our algorithm is competitive both with seminal tabular based CE algorithms and GNNExplainer, a well-established method for explaining graph-based classification tasks.