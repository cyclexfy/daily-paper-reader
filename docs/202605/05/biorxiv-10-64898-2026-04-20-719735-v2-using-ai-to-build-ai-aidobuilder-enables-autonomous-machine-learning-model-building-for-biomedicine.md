---
title: "Using AI to Build AI: AIDO.Builder Enables Autonomous Machine Learning Model Building for Biomedicine"
title_zh: 用AI构建AI：AIDO.Builder实现生物医学自主机器学习模型构建
authors: "Guo, H., Liang, Y., Cheng, X., Ellington, C., Xie, P., Song, L., Xing, E."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.20.719735v2.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 生物医学自动化机器学习模型构建
tldr: 生物医学领域机器学习模型的开发通常需要大量专家经验和手动迭代。本文提出 AIDO.Builder，一个全自动化的智能体系统，仅需自然语言描述即可自主完成从管道设计、架构选择到代码调试的整个生命周期。该系统通过自动反馈机制不断优化模型，支持从头训练或微调基础模型，在减少人工干预的同时显著提升了生物医学 AI 开发的效率和性能。
source: biorxiv
selection_source: fresh_fetch
motivation: 生物医学数据具有高度异构性、标注稀疏且评估协议复杂，使得手动构建有效的预测模型极具挑战且耗时。
method: 开发了名为 AIDO.Builder 的智能体系统，通过自然语言任务描述驱动，利用自动反馈循环自主设计、执行并迭代优化模型代码与训练流程。
result: 在多种生物医学基准测试中，AIDO.Builder 能够产生与人类专家方案极具竞争力的模型，同时消除了繁琐的手动迭代过程。
conclusion: 该研究展示了利用 AI 自动化构建 AI 模型的能力，为加速生物医学研究中的可靠模型开发提供了高效的新途径。
---

## 摘要
机器学习加速了生物医学发现，但创建有效的预测模型需要专门的人类专业知识和繁重的手动工作。研究人员必须迭代地设计流水线、选择架构并调试代码。由于该领域常见的异构数据集、稀疏标注和复杂的评估协议，这一挑战在生物医学领域尤为严峻。我们提出了AIDO.Builder，这是一个智能体人工智能系统，可完全自动化生物医学模型开发的整个生命周期。仅需提供自然语言任务描述和目标指标，AIDO.Builder即可自主构建可执行的训练和评估流水线。该系统选择合适的建模策略，执行实验，并利用自动化反馈循环迭代修改其自身的代码、配置和训练程序。它通过从头训练专用模型或利用预训练基础模型通过任务自适应构建预测模型，从而灵活地适应新任务。我们展示了在多种生物医学基准测试中，AIDO.Builder产生了与人类方案相比极具竞争力的解决方案，同时消除了以往稳健模型开发所需的手动迭代。通过自动化将原始数据转化为可靠的AI模型，AIDO.Builder展示了如何利用AI本身来加速生物医学研究中的AI应用。

## Abstract
Machine learning accelerates biomedical discovery, but creating effective predictive models requires specialized human expertise and demanding manual effort. Researchers must iteratively design pipelines, select architectures, and debug code. This challenge is particularly severe in biomedicine because of the heterogeneous datasets, sparse annotations, and complex evaluation protocols that are common in the domain. We present AIDO.Builder, an agentic artificial intelligence system that fully automates the entire life-cycle of biomedical model development. Provided only with a natural language task description and a target metric, AIDO.Builder autonomously constructs executable training and evaluation pipelines. The system selects suitable modeling strategies, executes experiments, and uses automated feedback-loop to iteratively revise its own code, configurations, and training procedures. It flexibly adapts to new tasks by training specialized models de novo or by using pretrained foundation models to build predictive models through task-appropriate adaptation. We show that across diverse biomedical benchmarks, AIDO. Builder produces highly competitive solutions against human alternatives, while eliminating the manual iteration previously required for robust model development. By automating the translation of raw data into reliable AI models, AIDO.Builder demonstrates how AI itself can be used to accelerate AI for biomedical research.