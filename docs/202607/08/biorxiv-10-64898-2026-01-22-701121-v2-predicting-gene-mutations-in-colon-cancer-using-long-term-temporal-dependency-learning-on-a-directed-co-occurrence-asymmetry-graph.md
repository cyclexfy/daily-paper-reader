---
title: Predicting Gene Mutations in Colon Cancer Using Long-Term Temporal Dependency Learning on a Directed Co-Occurrence Asymmetry Graph
title_zh: 使用有向共现不对称图上的长期时间依赖性学习预测结肠癌基因突变
authors: "Sumrell, C. R., Shishkin, A., Okeke, E., Zelikovsky, A., Moussa, M. R."
date: 2026-07-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.22.701121v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 使用深度学习预测结肠癌基因突变
tldr: 结肠癌肿瘤发生遵循逐步突变模式，但推断依赖关系困难。提出有向共现不对称图，从2344个样本中推断突变路径，并设计条件共享LSTM注意力模型预测目标基因突变。图派生路径显著提升精准率和召回率，注意力机制可有效加权前驱突变。该工作为癌症突变预测提供了图引导的时序建模新方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 结肠癌突变依赖关系难以从数据中推断，现有频率排序基线的预测性能有限。
method: 构建有向共现不对称图获得突变路径，并用条件共享LSTM加注意力沿路径预测基因突变状态。
result: 图派生路径相比频率排序显著提升精准率和召回率，注意力共享LSTM取得有竞争力的AUC和高召回率。
conclusion: 图引导的路径和注意力机制有效提升突变预测性能，为肿瘤基因组分析提供新思路。
---

## 摘要
结肠直肠肿瘤发生遵循逐步突变进展模式，但从突变数据推断依赖性仍然具有挑战性。我们提出一个有向共现不对称图，从覆盖23,858个突变基因的2,344个结肠腺癌样本中推断出基于图的突变路径。我们引入了一个基因条件的共享长短期记忆模型，带注意力机制，沿着推断的路径预测突变状态。注意力机制学习直接对信息丰富的前驱突变进行加权，而基因嵌入使共享模型适应每个目标基因。我们将此模型与标准的逐基因LSTM和扩张卷积神经网络架构进行比较。基于图的路径在精确率和召回率上显著优于复现的频率排序基线，加权路径整体表现最佳。基于注意力的共享LSTM在ROC曲线下面积上具有竞争力且召回率高，表明对前驱突变的注意力为靶基因预测提供了有用的表示。

## Abstract
Colorectal tumorigenesis follows stepwise mutational progression patterns, but inferring dependencies from mutation data remains challenging. We propose a directed co-occurrence asymmetry graph to infer graph-derived mutational paths from 2,344 colon adenocarcinoma samples covering 23,858 mutated genes.We introduce a gene-conditioned shared Long Short-Term Memory (LSTM) model with attention to predict mutation status along inferred paths. The attention mechanism learns to weight informative predecessor mutations directly, while gene embeddings adapt the shared model to each target gene. We compare this model with standard per-gene LSTM and dilated Convolutional Neural Network (CNN) architectures. Graph-derived paths substantially improved precision and recall over the reproduced frequency-ordering baseline, with weighted paths performing best overall. The attention-based shared LSTM achieved competitive area under the ROC curve (AUC) and high recall, indicating that attention over predecessor mutations provides a useful representation for target-gene prediction.