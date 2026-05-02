---
title: A transcriptomic-driven segmentation and cell simulation framework for high-resolution spatial transcriptomics and cell-cell communication
title_zh: 一种用于高分辨率空间转录组学和细胞间通讯的转录组驱动分割与细胞模拟框架
authors: "Wanchai, V., Bustamante-Gomez, N. C., Kurilung, A., Beenken, K. E., Cortes, S., Smeltzer, M. S., Leung, Y.-K., Xiong, J., Almeida, M., O'Brien, C. A., Nookaew, I."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720489v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 依赖组织学图像确定空间边界的转录组驱动分割框架
tldr: 针对Visium HD等高分辨率空间转录组平台中传统图像依赖型分割方法在复杂组织（如高密度或矿化组织）中表现不佳的问题，本文开发了TENGU框架。该框架采用转录本信号优先的分割策略，并利用创新的细胞模拟算法优化边界，有效减少了信号串扰。TENGU集成了组织分割、细胞标注及空间细胞通讯分析，在多种挑战性生物样本中展现出卓越的性能，为解析复杂组织微环境提供了强有力的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的空间转录组分割方法过度依赖组织学图像，在处理高密度、炎症或矿化组织时容易导致信号串扰和聚类错误。
method: 提出TENGU框架，优先利用转录本密度进行分割，并结合组织图像补充及转录组驱动的模拟算法来迭代优化细胞边界。
result: 实验证明TENGU在小鼠脑部和骨髓炎模型中表现出更高的转录组区分度，并成功识别了结直肠癌中的关键细胞通讯信号。
conclusion: TENGU通过减轻对图像的依赖，为准确解码健康和病理组织的复杂功能微观结构提供了一个高效且鲁棒的计算方案。
---

## 摘要
Visium HD 空间转录组平台能够实现接近单细胞分辨率的全转录组分析。然而，用于定义空间边界的精确细胞分割在很大程度上依赖于组织学图像。当组织具有高细胞密度、炎症或矿化时，现有方法难以定义细胞，从而导致转录组信号渗透（bleed-through）和不准确的聚类。为了解决这一问题，我们开发了 TENGU（转录信号富集与分组单元），这是一个全面的端到端生物信息学软件包。与现有工具不同，TENGU 采用“转录优先”的分割方法，将转录信号密度作为主要模态，仅在未解决区域将组织学图像作为次要补充。这些初始边界通过一种新型的转录组驱动细胞模拟算法进一步优化。基于局部基因表达概率的边界迭代细化有效地减少了空间散射，并保留了生物学上独特的分子特征。该流程无缝集成了组织分割、高分辨率细胞类型注释以及基础的空间感知细胞间通讯（CCC）分析。我们在多种具有技术挑战性的微环境中，针对 10X Genomics 和 Bin2cell 流程对 TENGU 的细胞分割性能进行了严格基准测试。TENGU 在小鼠大脑中展示了卓越的转录组区分度，成功捕获了基质嵌入的骨细胞，并在小鼠骨髓炎模型中定位了关键的骨免疫 CCC 网络（Tgfb 和 Il1a）。TENGU 还在高度压缩的人类结直肠癌异种移植物中解析了物种特异性的促肿瘤信号枢纽（MDK-SDC4）。通过减轻传统依赖图像分割的限制，TENGU 提供了一个高度适应且稳健的计算框架，使研究人员能够准确解码健康和病理组织的复杂功能微解剖结构。

## Abstract
The Visium HD spatial transcriptomics platform enables transcriptome-wide profiling at near-single-cell resolution. However, accurate segmentation of cells to define spatial boundaries relies heavily on histological images. Previous approaches struggle to define cells when the tissues have high cell density, are inflamed, or are mineralized, leading to transcriptomic bleed-through and inaccurate clustering. To address this, we developed TENGU (Transcript-signal Enrichment and Grouping Unit), a comprehensive end-to-end bioinformatic software package. Unlike existing tools, TENGU employs a transcript-first segmentation approach, prioritizing transcript-signal density as the primary modality and utilizing histological images only as a secondary supplement in unresolved regions. These initial boundaries are further optimized through a novel transcriptomic-driven cell simulation algorithm. Iterative refinement of boundaries based on localized gene expression probabilities effectively minimizes spatial scattering and preserves biologically distinct molecular signatures. The pipeline seamlessly integrates tissue segmentation, high-resolution cell-type annotation, and basic spatially aware cell-cell communication (CCC) analysis. We rigorously benchmarked TENGU against the 10X Genomics and Bin2cell pipelines for cell segmentation across diverse and technically challenging microenvironments. TENGU demonstrated superior transcriptomic distinctness in the murine brain, successfully captured matrix-embedded osteocytes, and localized critical osteoimmune CCC networks (Tgfb and Il1a) in a murine model of osteomyelitis. TENGU also resolved species-specific, pro-tumorigenic signaling hubs (MDK-SDC4) within a highly compacted human colorectal cancer xenograft. By mitigating the constraints of traditional image-dependent segmentation, TENGU provides a highly adaptable and robust computational framework that empowers researchers to accurately decode the complex functional micro-anatomy of both healthy and pathological tissues.