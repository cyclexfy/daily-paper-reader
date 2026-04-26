---
title: Foundation cell segmentation models performance on live microscopy and spatial-omics data
title_zh: 基础细胞分割模型在活体显微成像和空间组学数据上的性能表现
authors: "Miao, Y., Surguladze, N., Lerner, J., Poysungnoen, K., Ariano, K., Li, Y., Zhu, Y., Van Batavia, K., Jepson, J., Van De Klashorst, J., Ni, B. Y. X., Armstrong, A., Rahman, R., Horstmeyer, R., Hickey, J. W."
date: 2026-04-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.18.719315v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 在组织成像上评估CellSAM和Cellpose等基础细胞分割模型
tldr: 本研究系统评估了Cellpose-SAM、CellSAM、Mesmer等多种通用细胞分割模型在活细胞显微镜及CODEX空间组学数据上的表现。研究发现，Cellpose-SAM在相位对比图像中表现优异，SAM系列模型在荧光细胞数据中更具优势，而在复杂的CODEX组织图像中各模型表现各异。研究强调了分割模型的选择会直接影响细胞聚类等下游生物学分析结果，为科研人员根据数据特征选择最优工具提供了参考。
source: biorxiv
selection_source: fresh_fetch
motivation: 尽管通用细胞分割模型不断涌现，但缺乏针对不同成像模态及其对下游生物学分析影响的系统性比较评估。
method: 对比评估了Cellpose cyto3、Cellpose-SAM、microSAM、CellSAM、Mesmer和InstanSeg等模型在相位对比、荧光及CODEX多重荧光组织图像上的性能。
result: Cellpose-SAM和SAM类模型分别在相位对比和荧光图像中表现强劲，而CODEX数据中各模型在细胞类型鉴定等下游分析中表现出不同的优劣势。
conclusion: 细胞分割模型的选择应基于数据集特性和具体分析需求，而非盲目依赖单一的通用方法。
---

## 摘要
准确的细胞分割是生物成像数据定量分析的关键步骤。深度学习的最新进展促使了通用分割模型的开发，这些模型在多种成像模态下表现稳健，包括无标记相差成像、荧光细胞培养成像以及多重荧光组织成像。然而，在下游生物学分析层面，对这些模型的系统性比较仍然有限。为了填补这一空白，我们在相差和荧光细胞培养图像上评估了几种近期的分割模型，包括 Cellpose cyto3、Cellpose-SAM、{micro}SAM 和 CellSAM。此外，我们还纳入了 Mesmer 和 InstanSeg，用于对通过索引共检测（CODEX）技术生成的多重荧光组织图像进行基准测试。研究发现，Cellpose-SAM 在相差图像上表现出色，而基于 SAM 的模型在荧光细胞培养数据上始终表现良好。相比之下，在 CODEX 数据集上，没有单一模型能始终优于其他模型。相反，每个模型都表现出独特的优势和局限性，这导致了下游分析（包括聚类和细胞类型鉴定）的差异。总之，我们的研究强调了根据数据集特征和分析目标选择分割模型的重要性，而不是依赖单一的通用方法。

## Abstract
Accurate cell segmentation is an essential step for quantitative analysis of biological imaging data. Recent advances in deep learning have led to the development of generalist segmentation models that perform robustly across multiple imaging modalities, including label-free phase contrast, fluorescence cell culture, and multiplexed fluorescence tissue imaging. However, systematic comparisons of these models at the level of downstream biological analysis remain limited. To address this gap, we evaluated several recent segmentation models, including Cellpose cyto3, Cellpose-SAM, {micro}SAM, and CellSAM, on phase contrast and fluorescence cell culture images. In addition, Mesmer and InstanSeg were included for benchmarking on multiplexed fluorescence tissue images generated using CO-Detection by IndEXing (CODEX). We found that Cellpose-SAM achieved strong performance on phase contrast images, while SAM-based models consistently performed well on fluorescence cell culture data. In contrast, no single model consistently outperformed others on CODEX datasets. Instead, each model exhibited distinct strengths and limitations, which led to differences in downstream analyses, including clustering and cell type identification. Together, our study emphasizes the importance of selecting segmentation models based on dataset characteristics and analytical goals, rather than relying on a single universal approach.