---
title: "GAE-Δ: A Graph-Learning Framework for Gene Network Rewiring and Clinical Outcome Prediction from Multi-Omics Data"
title_zh: GAE-Δ：一种用于基因网络重连及多组学数据临床结局预测的图学习框架
authors: "Tang, Z., Chen, Z., Chen, M., Wang, Y., Ennis, S., Niranjan, M., Ewing, R."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.726880v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 多组学癌症结局预测，计算病理学相关文献
tldr: 本文提出GAE-Δ框架，利用图自编码器处理多组学数据，构建表型特异性基因网络，通过对比嵌入向量捕捉基因在不同条件下的网络角色变化，用于基因优先级排序和临床结局预测。在五种癌症数据上，其预测性能优于MOFA+等基线方法，且鉴定的基因显著富集已知癌症驱动基因。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以从多组学数据中捕捉表型特异性基因网络重连及其对临床结局的影响。
method: 针对两种表型组分别构建基因图，联合训练图自编码器得到共享隐空间的嵌入，通过对比嵌入差表征基因跨表型的网络角色变化，并进行多组学融合与分类。
result: 在五种癌症生存预测中，GAE-Δ在三个队列中AUC显著优于MOFA+，其余两个持平；共识基因在三个队列中显著富集癌症驱动基因（富集倍数11-17倍），而基线方法均未达到显著。
conclusion: GAE-Δ通过深度网络整合多组学数据，既提升了结局预测性能，又捕捉到线性因子方法遗漏的生物信号，有助于机制发现。
---

## 摘要
癌症的进展和结局部分源于遗传和/或环境扰动引起的分子网络变化。这些网络变化跨越多个相互关联的网络层级，包括体细胞突变积累、蛋白质-蛋白质相互作用改变以及基因表达失调。本文描述了一种基于图自编码器的框架（图自编码器-Δ（GAE-Δ）），用于表征多组学数据中表型特异性基因角色转变。给定分层为两个对比表型组的样本和一个先验基因相互作用网络，GAE-Δ为每个组学模态构建组特异性基因图，并为每个模态联合训练一个共享的图自编码器于两个组图上，使得两个组的条件嵌入共享一个共同潜在空间。对比这些嵌入定义了每个基因的多组学嵌入转变表示，反映了其网络角色在不同表型背景下的重组。这些基因级别转变随后用于无监督基因优先级排序、多组学后期融合和样本级别分类。应用于五个具有生存终点的TCGA癌症类型，GAE-Δ与基于经典网络的方法和多组学矩阵分解方法（MOFA+、iNMF）相比，实现了具有竞争力或更优的预测性能，在五个队列中的三个队列中AUC显著高于MOFA+，其余两个队列统计上持平。除预测性能外，共识转变基因在五个队列中的三个队列中显著富集了已知癌症驱动基因（超几何检验p<0.01；富集倍数11-17倍），而矩阵分解基线在五个队列中零个达到p<0.05（每癌种最佳p=0.06），表明GAE-Δ捕捉到了线性因子方法遗漏的生物信号。总之，GAE-Δ方法通过基于深度网络的疾病相关多组学数据整合，既改进了结局分类，又促进了生物学和机制发现。

## Abstract
Cancer progression and outcomes are driven in part by changes to molecular networks thatresult from genetic and/or environmental perturbations. These network changes manifestacross multiple interconnected network layers and include accumulation of somatic mutations, altered protein-protein interactions and dysregulated gene-expression. Here wedescribe a graph autoencoder based framework (Graph Autoencoder-Delta (GAE-{Delta})), for characterizing phenotype-specific gene role shifts across multiomics data. Given samples stratified into two contrasting phenotypic groups and a prior gene interaction network,GAE-{Delta} constructs group-specific gene graphs for each omics modality and trains, for each modality, a single graph autoencoder jointly on both group graphs, so that the two group conditional embeddings share a common latent space. Contrasting these embeddings defines a multiomics embedding-shift representation for each gene that reflects how its network role reorganizes across phenotypic contexts. These gene-level shifts are subsequently used for unsupervised gene prioritization, multiomics late fusion andsample-level classification. Applied to five TCGA cancer types with a survival endpoint, GAE-{Delta} achieves competitive or superior predictive performance compared with classical network based methods and multiomics matrix factorisation methods (MOFA+, iNMF), with statistically significant AUC gains over MOFA+ in three of five cohorts and statistical ties on the remaining two. Beyond predictive performance, the consensus shift genes are significantly enriched for known cancer drivers in three of five cohorts (hypergeometric p < 0.01; 11 - 17x fold enrichment), whereas matrix factorisation baselines reach p < 0.05 in zero of five cohorts (best per cancer p = 0.06), indicating that GAE-{Delta} captures biological signal that linear factor methods miss. In summary, the GAE- {Delta} approach provides for both improved outcome classification as well as for biological and mechanistic discovery through deep network-based integration of disease-associated multi-omics data.