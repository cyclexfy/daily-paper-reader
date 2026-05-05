---
title: "CenSegNet: a generalist high-throughput deep learning framework for centrosome phenotyping at spatial and single-cell resolution in heterogeneous tissues"
title_zh: CenSegNet：一种用于异质组织中空间和单细胞分辨率中心体表型分析的通用高通量深度学习框架
authors: "Cheng, J., Fan, K., Bailey, M., Du, X., Jena, R., Savva, C., Reed, E., Gou, M., Zuo, P., Beers, S., Cutress, R., Cai, X., Elias, S."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.15.676250v3.full.pdf"
tags: ["query:cpath"]
score: 7.5
evidence: 用于上皮癌中心体表型分析的深度学习
tldr: 针对上皮性癌症中中心体异常（CA）的空间复杂性和表型异质性，本文开发了CenSegNet深度学习框架。该框架采用双分支架构和不确定性引导优化，实现了跨组织、跨模态的高分辨率中心体及上皮结构分割。通过对大规模乳腺癌样本的单细胞空间分析，揭示了CA亚型与临床特征及预后的关联，为癌症病理研究提供了高效、开源的表型分析平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的图像分析方法难以解决上皮性癌症中中心体异常的空间复杂性和表型异质性问题。
method: 开发了名为CenSegNet的模块化深度学习框架，采用双分支架构结合不确定性引导优化，实现高分辨率、上下文感知的分割。
result: 在大规模乳腺癌样本分析中，该模型准确量化了数值和结构性CA，并发现结构性CA与患者总生存期及多种临床病理特征显著相关。
conclusion: CenSegNet是一个可扩展且通用的空间中心体表型分析平台，为系统研究中心体在癌症及其他疾病中的失调提供了有力工具。
---

## 摘要
中心体异常（CA）是上皮性癌症的一个标志，但由于传统图像分析的局限性，其空间复杂性和表型异质性仍未得到很好的解决。我们提出了 CenSegNet（中心体分割网络），这是一个模块化的深度学习框架，用于跨多种组织类型对中心体和上皮结构进行高分辨率、上下文感知的分割。通过集成双分支架构与不确定性引导的细化，CenSegNet 在免疫荧光和免疫组化模态中均实现了最先进的性能和泛化能力，在准确性和形态保真度方面优于现有模型。应用于包含来自 127 名患者的 911 个乳腺癌样本核心的组织微阵列（TMAs），CenSegNet 首次实现了单细胞分辨率下数量和结构性 CA 的大规模、空间解析定量。这些 CA 亚型在机制上是解耦的，表现出截然不同的空间分布、年龄依赖性动态，并与组织学肿瘤分级、激素受体状态、基因组改变和淋巴结受累相关。结构性 CA 水平还与总生存期相关，支持了空间解析 CA 模式的临床相关性。肿瘤边缘不一致的 CA 谱与局部侵袭性和间质重塑有关。为了支持广泛采用和可重复性，CenSegNet 以开源 Python 库的形式发布。总之，我们的研究结果将 CenSegNet 确立为一个可扩展、通用的平台，用于完整组织中空间解析的中心体表型分析，从而能够系统地剖析该细胞器的生物学及其在癌症和其他上皮疾病中的失调。

## Abstract
Centrosome abnormalities (CA) are a hallmark of epithelial cancers, yet their spatial complexity and phenotypic heterogeneity remain poorly resolved due to limitations in conventional image analysis. We present CenSegNet (Centrosome Segmentation Network), a modular deep learning framework for high-resolution, context-aware segmentation of centrosomes and epithelial architecture across diverse tissue types. Integrating a dual-branch architecture with uncertainty-guided refinement, CenSegNet achieves state-of-the-art performance and generalisability across both immunofluorescence and immunohistochemistry modalities, outperforming existing models in accuracy and morphological fidelity. Applied to tissue microarrays (TMAs) containing 911 breast cancer sample cores from 127 patients, CenSegNet enables the first large-scale, spatially resolved quantification of numerical and structural CA at single-cell resolution. These CA subtypes are mechanistically uncoupled, exhibiting distinct spatial distributions, age-dependent dynamics, and associations with histological tumour grade, hormone receptor status, genomic alterations, and nodal involvement. Structural CA levels are additionally associated with overall survival, supporting the clinical relevance of spatially resolved CA patterns. Discordant CA profiles at tumour margins are linked to local aggressiveness and stromal remodelling. To support broad adoption and reproducibility, CenSegNet is released as an open-source Python library. Together, our findings establish CenSegNet as a scalable, generalisable platform for spatially resolved centrosome phenotyping in intact tissues, enabling systematic dissection of the biology of this organelle and its dysregulation in cancer and other epithelial diseases.