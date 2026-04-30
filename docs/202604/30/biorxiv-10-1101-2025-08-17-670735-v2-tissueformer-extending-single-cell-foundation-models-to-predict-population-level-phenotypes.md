---
title: "TissueFormer: Extending single-cell foundation models to predict population-level phenotypes"
title_zh: TissueFormer：扩展单细胞基础模型以预测群体级表型
authors: "Benjamin, A. S., Zador, A."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.17.670735v2.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 扩展单细胞基础模型以预测群体水平的表型
tldr: 针对现有单细胞分析方法忽略细胞组成和组织层面信息的局限，本文提出TissueFormer，这是一种基于Transformer的神经网络，能够从单细胞RNA谱群组中推断群体水平的表型。该模型在预测新冠肺炎严重程度和脑皮层区域识别任务中表现优异，超越了现有的基础模型和机器学习方法，为高精度诊断和自动化脑图谱构建提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的单细胞分析方法大多基于孤立的细胞谱，忽略了对推断组织身份和样本表型至关重要的细胞组成信息。
method: 提出了一种名为TissueFormer的Transformer架构，能够整合单细胞群组信息以预测群体水平的标签，同时保留单细胞分辨率。
result: 在新冠病情预测和脑空间转录组分析中，TissueFormer的性能均优于单细胞基础模型及基于伪批量或细胞组成的传统方法。
conclusion: TissueFormer为预测受细胞多样性和组织结构影响的群体水平表型提供了一个通用且高效的计算框架。
---

## 摘要
单细胞RNA测序技术为基因表达提供了前所未有的见解，并为诊断和组织注释开辟了新路径。目前，大多数解释单细胞数据的计算方法是基于孤立的单细胞转录组图谱来预测标签或属性。这种方法忽略了样本内的细胞组成，而这对于推断组织身份或其他样本级表型通常至关重要。为了解决这一局限性，我们提出了TissueFormer，这是一种基于Transformer的神经网络，它在保留单细胞分辨率的同时，从单细胞RNA图谱组中推断群体级标签。我们将TissueFormer应用于两项任务：从血液样本的单细胞RNA测序中预测COVID-19的严重程度，以及从老鼠大脑的空间转录组数据中预测皮层区域身份。TissueFormer的表现优于应用于伪批量（pseudobulk）和细胞类型组成的单细胞基础模型及机器学习方法。TissueFormer更高的性能有望实现更准确的诊断，并能够直接从空间转录组数据中自动构建单只老鼠的高分辨率脑区图谱。应用于视觉输入受到发育干扰的老鼠时，这些图谱显示预测的视觉皮层区域显著减少，说明了如何量化神经解剖学的个体差异。更广泛地说，TissueFormer为预测任何受细胞多样性和组织级组织影响的群体级表型提供了一个框架。

## Abstract
Single-cell RNA sequencing technologies have enabled unprecedented insights into gene expression and opened new pathways for diagnostics and tissue annotation. At present, most computational approaches for interpreting single-cell data predict labels or properties based on isolated single-cell transcriptomic profiles. This approach overlooks the cellular composition within a sample, which is often critical for inferring tissue identity or other sample-level phenotypes. To address this limitation, we introduce TissueFormer, a Transformer-based neural network that infers population-level labels from groups of single-cell RNA profiles while retaining single-cell resolution. We applied TissueFormer to two tasks: predicting COVID-19 severity from single-cell RNA sequencing of blood samples, and predicting cortical area identity from spatial transcriptomic data in mouse brains. TissueFormer outperformed single-cell foundation models and machine learning methods applied to pseudobulk and cell type composition. TissueFormer's higher performance promises more accurate diagnostics and enables the automated construction of high-resolution brain region maps in individual mice directly from spatial transcriptomic data. Applied to mice with developmental perturbations to visual input, these maps revealed a significant reduction in predicted visual cortex area, illustrating how individual differences in neuroanatomy can be quantified. More broadly, TissueFormer provides a framework for predicting any population-level phenotypes which are influenced by cellular diversity and tissue-level organization.