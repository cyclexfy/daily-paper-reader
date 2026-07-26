---
title: "SPgen: Proteome-wide Spatial Proteomics generation using multi-modality foundation models"
title_zh: SPgen：利用多模态基础模型进行蛋白质组范围内的空间蛋白质组学生成
authors: "Li, J., Yang, K., Che, Q., Zheng, D., Wei, W., Jin, C., Yuan, Y."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.16.739037v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于空间蛋白质组学预测的多模态基础模型
tldr: 空间蛋白质组学技术仅测量小部分蛋白质，成本高且受噪声干扰。SPgen多模态基础模型整合蛋白质序列、功能注释、转录组和空间信息，学习可迁移表示。在多个数据集上准确重建空间模式，降低噪声，实现全蛋白质组预测。该模型可泛化至未实验测量的蛋白质，拓展空间蛋白质组学应用。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739037-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1546, \"height\": 1431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739037-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1501, \"height\": 1705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739037-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1502, \"height\": 2495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739037-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1534, \"height\": 1733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739037-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1618, \"height\": 2156, \"label\": \"Figure\"}]"
motivation: 现有空间蛋白质组学技术覆盖蛋白少，依赖配对数据，难以泛化至未测量蛋白。
method: SPgen整合蛋白质序列、功能注释、转录组和空间信息，构建多模态基础模型学习可迁移表示。
result: 在多种数据集上准确重建空间模式，降低测量噪声，实现全蛋白质组空间预测。
conclusion: SPgen为空间蛋白质组学提供可泛化的全蛋白质组预测框架，突破实验测量限制。
---

## 摘要
空间蛋白质组学测量蛋白质在组织内的空间分布，为组织功能、疾病和治疗反应提供重要见解。然而，当前的空间蛋白质组学技术仅能分析蛋白质组的一小部分，并受限于成本和测量噪声。最近的AI方法能够从转录组或组织病理学数据预测空间蛋白表达，但通常局限于仅覆盖数十种蛋白质的配对数据集，限制了其泛化到实验测量蛋白质面板之外的能力。本文提出SPgen，一个用于蛋白质组范围空间蛋白预测的多模态基础模型框架。SPgen整合蛋白质序列、功能注释、转录组图谱和空间信息，学习可迁移的表征，从而能够推断超出实验测量蛋白质范围的蛋白表达。在多样化的空间蛋白质组学数据集上，SPgen准确重建了测量的空间模式，降低了测量噪声，并实现了蛋白质组范围内的空间预测。

## Abstract
Spatial proteomics (SP) measures the spatial distribution of proteins within tissues, providing important insights into tissue function, disease, and therapeutic response. However, current SP technologies profile only a small fraction of the proteome and are limited by cost and measurement noise. Recent AI approaches enable predicting spatial protein expression from transcriptomic or histopathological data, but are typically restricted to paired datasets covering only tens of proteins, limiting their ability to generalize beyond experimentally measured protein panels. Here we present SPgen, a multi-modal foundation-model framework for proteome-wide spatial protein prediction. SPgen integrates protein sequences, functional annotations, transcriptomic profiles, and spatial information to learn transferable representations that enable inference beyond experimentally profiled proteins. Across diverse spatial proteomics datasets, SPgen accurately reconstructs measured spatial patterns, reduces measurement noise, and enables proteome-wide spatial prediction.