---
title: "OmicsNavigator: An auditable scientific partner for scalable hypothesis validation in spatial omics"
title_zh: OmicsNavigator：用于空间组学中可扩展假设验证的可审计科学伙伴
authors: "Li, Y., Vakharia, N., Liang, W., Mayer, A. T., Luo, R., Trevino, A. E., Wu, Z."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.1101/2025.07.21.665821v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 利用大语言模型分析多模态空间组学数据
tldr: 空间组学数据的高维性和复杂性使其转化为可检验的生物学发现面临挑战。OmicsNavigator基于大型语言模型，直接推理视觉和分子等多模态输入，实现知识引导的空间结构注释。通过将高维数据转化为文本解释，系统支持零样本生物标志物检索和患者级疾病概况重建。在糖尿病肾病、肾移植排斥和COVID-19肺病理数据集上验证，表明其能生成基于证据的、人类可读的见解，有望加速空间生物学发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决高维空间组学数据难以转化为可检验生物学发现的研究瓶颈。
method: 提出基于大型语言模型的OmicsNavigator系统，直接推理多模态输入，将高维数据转化为文本解释，并借助预注册、人类审计蓝图进行假设验证。
result: 在多种病理数据集上实现零样本生物标志物检索、疾病概况重建，并生成基于证据的见解。
conclusion: OmicsNavigator作为可审计的科学伙伴，能有效加速空间生物学发现。
---

## 摘要
将高维度、空间解析的分子数据集转换为可测试的生物学发现仍是一个主要的研究瓶颈。这里，我们提出了OmicsNavigator，一个基于自主大型语言模型的系统，用于空间组学数据的端到端数据探索和假设验证。OmicsNavigator直接对空间组学数据的多模态输入（包括视觉和分子特征）进行推理，以执行空间结构的知识引导注释。我们表明，通过将高维度数据转换为文本解释，OmicsNavigator能够实现组织生物标志物的零样本语义检索，并从原始组学观测中重建患者水平的疾病谱。此外，OmicsNavigator具有一个由预注册、人工审计蓝图控制的客观假设验证引擎。通过在涵盖多种病理条件（包括糖尿病肾病、肾移植排斥和COVID-19肺部病理）的数据集上验证该系统，我们证明OmicsNavigator能从空间组学数据中生成基于证据、人类可读的见解，具有加速空间生物学发现的潜力。

## Abstract
Translating high-dimensional, spatially resolved molecular datasets into testable biological findings remains a major research bottleneck. Here, we present Omic-sNavigator, an autonomous large language model-powered system for end-to-end data exploration and hypothesis validation on spatial omics data. OmicsNaviga-tor reasons directly over the multi-modal inputs of spatial omics data, including visual and molecular signatures, to perform knowledge-guided annotation of spatial structures. We show that by transforming high-dimensional data into textual interpretations, OmicsNavigator enables zero-shot semantic retrieval of tissue biomarkers and the reconstruction of patient-level disease profiles from raw omics observations. Furthermore, OmicsNavigator features an objective hypothesis validation engine governed by pre-registered, human-audited blueprints. By validating the system across datasets spanning diverse pathological conditions including diabetic kidney disease, kidney transplant rejection, and COVID-19 pulmonary pathology, we demonstrate that OmicsNavigator generates evidence-based, human-readable insights from spatial omics data, with potential to accelerate spatial biology discoveries.