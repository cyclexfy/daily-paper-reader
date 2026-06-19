---
title: "Pillbox: A Leakage-Aware Foundation-Model Predictor and Lineage-Ceiling Diagnostic for Cancer Drug Response"
title_zh: Pillbox：一种泄漏感知的基础模型预测器及癌症药物反应的谱系天花板诊断方法
authors: "Hill, J. J. K., Jiao, E., Singh, S., Ghanta, A., Anders, D., Jeong, J., Ryoo, H. J."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.725572v2.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于癌症药物反应的基座模型预测器
tldr: 癌症药物反应预测常因数据泄露导致性能虚高。Pillbox针对六种泄露模式审计管道，结合CpGPT甲基化、CLAMP药物嵌入和基因表达主成分，利用FiLM条件图注意力融合并在STRING蛋白互作图上传播，再与梯度提升回归集成。在GDSC数据集上，随机、组织盲和位点盲分割下测试R²分别达0.78、0.77和0.76，细胞感知提升约0.04-0.06。提出交叉架构残差相关诊断，发现组织谱系主导反应，当前架构离表示上限仅差0.03，说明改进空间有限。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决药物反应预测中的数据泄露问题，并诊断特征堆栈饱和性与组织谱系对预测的主导作用。
method: 融合CpGPT甲基化嵌入、CLAMP药物嵌入和基因表达主成分，通过FiLM条件图注意力在STRING PPI图上建模，再与梯度提升回归基线集成。
result: GDSC上随机、组织盲、位点盲分割R²达0.78/0.77/0.76，细胞感知提升0.054/0.060/0.037；交叉架构诊断显示组织谱系限制预测上限。
conclusion: 组织谱系主导细胞系药物反应，当前架构仅差0.03残差相关到天花板，额外突变/甲基化特征无增益。
---

## 摘要
我们提出Pillbox，一种预测器，其流程针对六种Asiaee泄漏模式进行了审计，其中一种残余通路通过逐折消融分析证实对硬分割没有承载作用。我们的模型结合了CpGPT甲基化嵌入、CLAMP药物嵌入以及逐折拟合的基因表达主成分，通过特征线性调制（FiLM）条件化的图注意力机制在STRING v12蛋白质-蛋白质相互作用图上进行融合。然后，我们将模型与基于直方图的梯度提升回归基线进行α集成。在GDSC GSE68379数据集（987个细胞系，375种药物）上，跨种子42、7和123，集成模型在随机、组织学盲和部位盲分割上的测试R平方分别达到0.78、0.77和0.76，细胞感知提升高于药物均值基线+0.054、+0.060和+0.037。作为特征栈饱和的定量诊断，我们提出了跨架构残差相关性，并通过相同架构不同初始化的对照进行了校准。在组织学盲分割上，跨架构残差相关性值为0.939，低于相同架构天花板0.974约0.03，这一差距被解释为在当前基础模型表示之上架构选择可用的提升空间，并且与长期观察到的组织谱系主导细胞系药物反应的结论一致。我们整合了精心整理的突变、甲基化和药物靶点表达通道，但一旦基础模型嵌入就位，这些通道并未改善预测。针对PRISM的跨屏幕验证与GDSC到PRISM的测量可重复性天花板在0.01 Spearman范围内匹配。

## Abstract
We present Pillbox, a predictor whose pipeline is audited against the six Asiaee leakage modes with the one residual pathway shown by per-fold ablation to be non-load-bearing on hard splits. Our model combines CpGPT methylation embeddings, CLAMP drug embeddings, and per-fold-fit gene-expression principal components which are fused by Feature-wise Linear Modulation (FiLM)-conditioned graph attention on the STRING v12 protein-protein interaction graph. Then we alpha-ensemble the model against a histogram-based gradient boosting regressor baseline. On GDSC GSE68379 (987 cell lines, 375 drugs) across seeds 42, 7, and 123, the ensemble reaches test R-Squared of 0.78, 0.77, and 0.76 on random, histology-blind, and site-blind splits respectively, with cell-aware lifts above the drug-mean floor of +0.054, +0.060, and +0.037. As a quantitative diagnostic for feature-stack saturation we propose the cross-architecture residual correlation, calibrated against a same-architecture-different-initialization control. On histology-blind splits the cross-architecture value of 0.939 falls short of the same-architecture ceiling of 0.974 by approximately 0.03 in residual correlation, a gap we interpret as the headroom available to architecture choice on top of the current foundation-model representation and consistent with the long-established observation that tissue lineage dominates cell-line drug response. We integrated curated mutation, methylation, and drug-target-expression channels, but these do not improve prediction once foundation-model embeddings are in place. Cross-screen validation against PRISM matches the GDSC-to-PRISM measurement reproducibility ceiling within 0.01 Spearman.