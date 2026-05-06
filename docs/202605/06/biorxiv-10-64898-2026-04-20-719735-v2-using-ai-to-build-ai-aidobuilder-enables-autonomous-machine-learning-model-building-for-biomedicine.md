---
title: "Using AI to Build AI: AIDO.Builder Enables Autonomous Machine Learning Model Building for Biomedicine"
title_zh: 用AI构建AI：AIDO.Builder实现生物医学自主机器学习模型构建
authors: "Guo, H., Liang, Y., Cheng, X., Ellington, C., Xie, P., Song, L., Xing, E."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.20.719735v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 生物医学自主机器学习模型构建
tldr: AIDO.Builder是一个旨在自动化生物医学机器学习模型构建的智能体系统。针对生物医学数据异构、标注稀疏等挑战，该系统仅需自然语言描述即可自主设计、执行并迭代优化训练流水线。它能灵活运用从头训练或微调基础模型等策略，在多个基准测试中达到与人类专家相当的水平，显著降低了模型开发的门槛与成本。
source: biorxiv
selection_source: fresh_fetch
motivation: 生物医学领域模型开发过程复杂且高度依赖专家经验，亟需自动化工具来降低人工迭代成本。
method: 开发了名为AIDO.Builder的智能体系统，通过自然语言指令自主构建、执行并利用反馈循环迭代优化模型代码与配置。
result: 在多样化的生物医学基准测试中，该系统生成的解决方案表现出与人类专家方案相当的竞争力。
conclusion: AIDO.Builder证明了利用AI自动化构建AI模型的可行性，能有效加速生物医学研究中的模型开发进程。
---

## 摘要
机器学习加速了生物医学发现，但创建有效的预测模型需要专门的人类专业知识和繁重的手动工作。研究人员必须迭代地设计流水线、选择架构并调试代码。由于该领域常见的异构数据集、稀疏标注和复杂的评估协议，这一挑战在生物医学领域尤为严峻。我们提出了AIDO.Builder，这是一个智能体人工智能系统，可完全自动化生物医学模型开发的整个生命周期。仅需提供自然语言任务描述和目标指标，AIDO.Builder即可自主构建可执行的训练和评估流水线。该系统选择合适的建模策略，执行实验，并利用自动反馈循环迭代修改其自身的代码、配置和训练程序。它通过从头训练专用模型或利用预训练基础模型进行任务适配，灵活地适应新任务。我们展示了在多种生物医学基准测试中，AIDO.Builder产生了与人类方案相比极具竞争力的解决方案，同时消除了以往稳健模型开发所需的手动迭代。通过自动化将原始数据转化为可靠的AI模型，AIDO.Builder展示了如何利用AI本身来加速生物医学研究中的AI应用。

## Abstract
Machine learning accelerates biomedical discovery, but creating effective predictive models requires specialized human expertise and demanding manual effort. Researchers must iteratively design pipelines, select architectures, and debug code. This challenge is particularly severe in biomedicine because of the heterogeneous datasets, sparse annotations, and complex evaluation protocols that are common in the domain. We present AIDO.Builder, an agentic artificial intelligence system that fully automates the entire life-cycle of biomedical model development. Provided only with a natural language task description and a target metric, AIDO.Builder autonomously constructs executable training and evaluation pipelines. The system selects suitable modeling strategies, executes experiments, and uses automated feedback-loop to iteratively revise its own code, configurations, and training procedures. It flexibly adapts to new tasks by training specialized models de novo or by using pretrained foundation models to build predictive models through task-appropriate adaptation. We show that across diverse biomedical benchmarks, AIDO. Builder produces highly competitive solutions against human alternatives, while eliminating the manual iteration previously required for robust model development. By automating the translation of raw data into reliable AI models, AIDO.Builder demonstrates how AI itself can be used to accelerate AI for biomedical research.