---
title: "Bio-BLIP: A Multimodal Architecture for Transferable Reasoning in Genomic Variant Interpretation"
title_zh: Bio-BLIP：一种用于基因组变异解释中可迁移推理的多模态架构
authors: "Gupta, A., Buendia, A., Kundaje, A., Leskovec, J."
date: 2026-05-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.12.724740v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 整合DNA、基因背景、蛋白质和文献的多模态架构
tldr: Bio-BLIP 是一种新型多模态架构，通过 Q-former 机制整合 DNA、基因、蛋白质和文本数据，解决了基因组变异解释中异构证据融合的难题。该模型将生物学嵌入转化为 LLM 的输入前缀，在人类遗传变异注释预训练后，无需微调即可在变异优先级排序等任务中实现卓越的零样本推理，显著优于现有模型并提供透明的推理过程。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的多模态生物 AI 系统通常局限于特定任务且难以整合跨尺度的异构生物证据，限制了其通用推理能力。
method: 提出基于 Q-former 的架构，将 DNA、基因、蛋白质和文本模态整合为固定长度的前缀，引导大语言模型进行推理。
result: "在变异特征生成上比顶尖 LLM 准确率提升 29.8%，并在零样本下游任务中优于现有的基因组语言模型。"
conclusion: Bio-BLIP 证明了原生多模态架构在生物学通用推理中的潜力，为跨尺度生物数据分析提供了可扩展且透明的解决方案。
---

## 摘要
在生物学中提出科学假设需要整合 DNA 序列、基因背景、蛋白质功能和既往文献中的异构证据。现有的多模态 AI 系统通过文本化或将生物嵌入投影到微调后的语言模型中，向推理模型展示生物证据。然而，这些模型通常针对其微调的特定任务集进行了高度优化。在这里，我们提出了 Bio-BLIP，这是一种基于 Q-former 的多模态架构，它利用生物嵌入和大型语言模型（LLM），在无需特定任务微调的情况下泛化到复杂的推理任务。Bio-BLIP 的关键在于一种新的神经网络架构，它通过一个主 Q-former 模型整合了四种数据模态——DNA、基因、蛋白质和文本，该模型将特定模态的信息整合为 LLM 主干网络的固定长度前缀。Bio-BLIP 在人类遗传变异注释任务上进行了预训练，在生成准确变异特征方面比前沿 LLM 提高了 29.8%。我们在变异优先级排序和靶基因预测的下游基因组任务上对 Bio-BLIP 进行了零样本评估。在孟德尔疾病的调控变异优先级排序方面，Bio-BLIP 优于两种无对齐的基因组语言模型。在靶基因预测任务中，Bio-BLIP 通过在困难案例中利用学习到的基因组变异知识，提高了相对于 LLM 的准确性。我们的模型产生了丰富且透明的推理轨迹。在具有多尺度数据和多样化下游任务特征的生物学领域，Bio-BLIP 为实现原生多模态、可泛化的推理迈出了一步。

## Abstract
Developing scientific hypotheses in biology requires integrating heterogeneous evidence across DNA sequence, gene context, protein function, and prior literature. Existing multimodal AI systems expose biological evidence to reasoning models through textification or by projecting biological embeddings into fine-tuned language models. However, these models are typically highly optimized the specific set of tasks for which they are fine-tuned. Here we present Bio-BLIP, a multimodal Q-former based architecture which leverages biological embeddings and a LLM to generalize to complex reasoning tasks without task-specific fine-tuning. The key to Bio-BLIP is a new neural network architecture that integrates four data modalities - DNA, genes, proteins, and text - through a master Qformer model, which integrates the modality-specific information into a fixed-length prefix for the LLM backbone. Bio-BLIP is pretrained on the task of human genetic variant annotation and achieves a 29.8% increase in generating accurate variant features over frontier LLMs. We evaluate Bio-BLIP zero-shot on downstream genomic tasks of variant prioritization and target gene prediction. Bio-BLIP outperforms two alignment-free genomic language models on regulatory variant prioritization for Mendelian disease. Across the target gene prediction task, Bio-BLIP improves accuracy over LLMs by leveraging learned genomic variant knowledge in difficult cases. Our model produces rich, transparent reasoning traces. In biological domains characterized by multiple scales of data and varied downstream tasks, Bio-BLIP offers a step toward natively multimodal, generalizable reasoning.