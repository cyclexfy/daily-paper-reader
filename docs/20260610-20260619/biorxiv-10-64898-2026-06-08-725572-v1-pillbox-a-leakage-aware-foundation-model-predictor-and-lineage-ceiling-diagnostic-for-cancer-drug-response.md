---
title: "Pillbox: A Leakage-Aware Foundation-Model Predictor and Lineage-Ceiling Diagnostic for Cancer Drug Response"
title_zh: "Pillbox: 一种泄漏感知的基础模型预测器及癌症药物反应中的谱系天花板诊断"
authors: "Hill, J. J. K., Ryoo, H. J., Ghanta, A., Singh, S., Anders, D., Jiao, E., Jeong, J."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.725572v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 使用基础模型预测癌症药物反应
tldr: 癌症药物响应预测受数据泄漏和谱系主导效应影响。Pillbox模型审计六种泄漏模式，融合CpGPT甲基化嵌入、CLAMP药物嵌入及基因表达主成分，通过FiLM条件图注意力集成，达到GDSC数据集R² 0.78（随机）和0.77（组织学盲）。提出跨架构残差相关诊断，揭示谱系上限约为0.03的差距。集成突变、甲基化等通道无提升，跨屏验证与PRISM测量复现性一致。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有预测模型常忽视数据泄漏和谱系主导，导致泛化性不足，需泄漏感知框架和定量诊断。
method: 结合CpGPT和CLAMP嵌入与基因表达主成分，经FiLM调制图注意力集成，并审计六种Asiaee泄漏模式。
result: 在GDSC上达到R² 0.78（随机）、0.77（组织学盲），残差相关诊断显示谱系上限0.03，额外通道无增益。
conclusion: Pillbox提供泄漏鲁棒预测和谱系上限诊断，跨屏验证与PRISM匹配，证明基础模型表示的饱和性。
---

## 摘要
我们提出Pillbox，一个预测器，其管道针对六种Asiaee泄漏模式进行了审计，并保留了一条通过逐折消融证明在硬划分上不承担负荷的残差路径。我们的模型结合了CpGPT甲基化嵌入、CLAMP药物嵌入以及每折拟合的基因表达主成分，这些组件通过基于特征线性调制（FiLM）条件的图注意力机制在STRING v12蛋白质-蛋白质相互作用图上进行融合。然后，我们将该模型与基于直方图的梯度提升回归基线进行α集成。在GDSC GSE68379数据集（987种细胞系，375种药物）上，使用种子42、7和123，集成模型在随机、组织学盲和位点盲划分上分别达到测试R平方0.78、0.77和0.76，细胞感知提升高于药物均值基线+0.054、+0.060和+0.037。作为特征堆叠饱和度的定量诊断，我们提出了跨架构残差相关性，并针对相同架构不同初始化的对照进行了校准。在组织学盲划分上，跨架构值为0.939，低于相同架构天花板0.974约0.03的残差相关性，这一差距被解释为在当前基础模型表示之上架构选择可用的提升空间，并且与长期观察到的组织谱系主导细胞系药物反应的现象一致。我们整合了精选的突变、甲基化和药物靶点表达通道，但一旦基础模型嵌入到位，这些通道并未改善预测。针对PRISM的跨屏幕验证在0.01 Spearman范围内匹配了GDSC到PRISM的测量可重复性天花板。

## Abstract
We present Pillbox, a predictor whose pipeline is audited against the six Asiaee leakage modes with the one residual pathway shown by per-fold ablation to be non-load-bearing on hard splits. Our model combines CpGPT methylation embeddings, CLAMP drug embeddings, and per-fold-fit gene-expression principal components which are fused by Feature-wise Linear Modulation (FiLM)-conditioned graph attention on the STRING v12 protein-protein interaction graph. Then we alpha-ensemble the model against a histogram-based gradient boosting regressor baseline. On GDSC GSE68379 (987 cell lines, 375 drugs) across seeds 42, 7, and 123, the ensemble reaches test R-Squared of 0.78, 0.77, and 0.76 on random, histology-blind, and site-blind splits respectively, with cell-aware lifts above the drug-mean floor of +0.054, +0.060, and +0.037. As a quantitative diagnostic for feature-stack saturation we propose the cross-architecture residual correlation, calibrated against a same-architecture-different-initialization control. On histology-blind splits the cross-architecture value of 0.939 falls short of the same-architecture ceiling of 0.974 by approximately 0.03 in residual correlation, a gap we interpret as the headroom available to architecture choice on top of the current foundation-model representation and consistent with the long-established observation that tissue lineage dominates cell-line drug response. We integrated curated mutation, methylation, and drug-target-expression channels, but these do not improve prediction once foundation-model embeddings are in place. Cross-screen validation against PRISM matches the GDSC-to-PRISM measurement reproducibility ceiling within 0.01 Spearman.