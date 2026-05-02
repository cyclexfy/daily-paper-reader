---
title: "Using AI to Build AI: AIDO.Builder Enables Autonomous Machine Learning Model Building for Biomedicine"
title_zh: 用 AI 构建 AI：AIDO.Builder 实现生物医学领域的自主机器学习模型构建
authors: "Guo, H., Liang, Y., Cheng, X., Ellington, C., Xie, P., Song, L., Xing, E."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.20.719735v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 生物医学自主机器学习模型构建
tldr: 本研究针对生物医学领域机器学习模型开发中对专家经验的高度依赖和繁琐的手动迭代问题，提出了AIDO.Builder。这是一个智能体AI系统，仅需自然语言描述和目标指标，即可自主完成从策略选择、代码编写到实验执行及反馈优化的全生命周期开发。该系统在多个生物医学基准测试中表现出与人类专家相当的竞争力，显著加速了生物医学研究中的AI模型构建过程。
source: biorxiv
selection_source: fresh_fetch
motivation: 生物医学数据复杂且标注稀疏，导致构建有效的预测模型需要耗费大量专家精力和手动迭代。
method: 开发了名为AIDO.Builder的智能体系统，通过自然语言指令自主构建、执行并利用反馈循环迭代优化训练与评估流水线。
result: 在多样化的生物医学基准测试中，该系统生成的解决方案达到了与人类专家相当的水平，且无需手动干预。
conclusion: AIDO.Builder证明了利用AI自动化构建AI模型的可行性，为加速生物医学研究提供了高效的自动化工具。
---

## 摘要
机器学习加速了生物医学发现，但创建有效的预测模型需要专门的人类专业知识和繁重的手动工作。研究人员必须迭代地设计流水线、选择架构并调试代码。由于该领域常见的异构数据集、稀疏标注和复杂的评估协议，这一挑战在生物医学中尤为严峻。我们提出了 AIDO.Builder，这是一个智能体人工智能系统，可完全自动化生物医学模型开发的整个生命周期。仅需提供自然语言任务描述和目标指标，AIDO.Builder 即可自主构建可执行的训练和评估流水线。该系统选择合适的建模策略，执行实验，并利用自动反馈循环迭代地修改其自身的代码、配置和训练程序。它通过从头训练专用模型或利用预训练基础模型通过任务自适应构建预测模型，从而灵活地适应新任务。我们展示了在多种生物医学基准测试中，AIDO.Builder 产生了与人类方案相比极具竞争力的解决方案，同时消除了以往稳健模型开发所需的手动迭代。通过自动化将原始数据转化为可靠的 AI 模型，AIDO.Builder 展示了 AI 本身如何被用于加速生物医学研究中的 AI 发展。

## Abstract
Machine learning accelerates biomedical discovery, but creating effective predictive models requires specialized human expertise and demanding manual effort. Researchers must iteratively design pipelines, select architectures, and debug code. This challenge is particularly severe in biomedicine because of the heterogeneous datasets, sparse annotations, and complex evaluation protocols that are common in the domain. We present AIDO.Builder, an agentic artificial intelligence system that fully automates the entire life-cycle of biomedical model development. Provided only with a natural language task description and a target metric, AIDO.Builder autonomously constructs executable training and evaluation pipelines. The system selects suitable modeling strategies, executes experiments, and uses automated feedback-loop to iteratively revise its own code, configurations, and training procedures. It flexibly adapts to new tasks by training specialized models de novo or by using pretrained foundation models to build predictive models through task-appropriate adaptation. We show that across diverse biomedical benchmarks, AIDO.Builder produces highly competitive solutions against human alternatives, while eliminating the manual iteration previously required for robust model development. By automating the translation of raw data into reliable AI models,AIDO.Builder demonstrates how AI itself can be used to accelerate AI for biomedical research.