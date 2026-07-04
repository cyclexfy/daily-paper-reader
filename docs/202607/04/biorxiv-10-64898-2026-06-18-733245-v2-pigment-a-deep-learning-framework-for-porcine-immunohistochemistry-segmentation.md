---
title: "PIGMENT: A deep learning framework for Porcine Immunohistochemistry seGMENTation"
title_zh: PIGMENT：一种用于猪免疫组化分割的深度学习框架
authors: "Ambastha, P., Dadashkarimi, J., Annavazala, S. K. C., Parker, D., Diaz-Arrastia, R., Song, H., Donahue, R. P., Smith, D. H., Dolle, J.-P., Johnson, V. E., Wolf, J. A., Verma, R."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733245v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 面向计算病理学的免疫组化分割深度学习框架
tldr: 创伤性脑损伤导致轴突损伤，APP免疫组化可标记损伤轴突，但手动量化耗时且可重复性差。为此提出PIGMENT，基于SegFormer-B0和特定数据增强，从少量标注中学习分割APP阳性病理。在猪白质组织学上达到0.86实例检测率，实现全切片损伤负担映射，支持与影像对齐的规模化分析。
source: biorxiv
selection_source: fresh_fetch
motivation: 手动量化APP病理效率低、变异大，限制可重复性和规模化，尤其在组织学与影像对齐的研究中。
method: 使用紧凑SegFormer-B0架构，结合525张标注图块和APP特异性增强策略，模拟染色强度、大小、碎片化等变化。
result: 在保留测试集上实现平均实例检测率0.86，跨动物训练集效果最佳。
conclusion: PIGMENT通过扩展有限标注实现全切片APP负担映射，为创伤性轴突损伤的空间量化提供可扩展框架。
---

## 摘要
创伤性脑损伤会产生广泛的轴突损伤，可通过淀粉样前体蛋白（APP）免疫组化在组织学上评估，该方法以细胞分辨率标记受损的轴突轮廓[1, 2]。然而，APP病理学的定量仍然是一个主要瓶颈：标注是手动的、耗时的、空间局部的，且在不同评估者之间存在差异，限制了可扩展性和可重复性。这一限制在将组织学作为神经影像或其他组织水平测量参考的研究中尤为重要，因为细胞层面的APP病理学必须以能够与影像异常对齐的空间形式进行定量。

在此，我们介绍PIGMENT，一种用于猪白质组织学中APP阳性病理学自动分割和定量的高效标注深度学习框架。PIGMENT采用紧凑的SegFormer-B0架构，该架构使用来自三只猪的四个APP染色切片的525个专家标注的512×512像素瓦片进行训练。由于APP阳性轮廓稀疏、破碎、染色可变且形态多样，PIGMENT将有限的专家标签与针对APP的增强相结合，旨在模拟APP阳性强度、大小、连续性、破碎性和局部组织背景的变化。

我们使用实例级检测率来评估PIGMENT，该检测率衡量离散的APP阳性成分是否被定位。在留出的APP染色数据上，PIGMENT的平均实例级检测率达到0.86。在测试的配置中，包含来自不同动物切片的训练集取得了最高的平均检测率，这表明在有限标签条件下，标注多样性可能是一个重要因素。

通过将有限的高置信度专家标注扩展到整个切片的APP负荷图，PIGMENT提供了一个可扩展的框架，用于表征创伤性轴突损伤的程度和空间分布。这些图可能支持未来将组织学损伤负荷与影像衍生测量对齐的研究。

## Abstract
Traumatic brain injury produces widespread axonal damage can be assessed histologically using amyloid precursor protein (APP) immunohistochemistry, which labels injured axonal profiles at cellular resolution [1, 2]. However, quantification of APP pathology remains a major bottleneck: annotation is manual, time-consuming, spatially localized, and variable across raters, limiting scalability and reproducibility. This limitation is particularly important in studies that use histology as a reference for neuroimaging or other tissue-level measurements, where cellular APP pathology must be quantified in a spatial form that can be aligned with imaging abnormalities.

Here, we introduce PIGMENT, an annotation-efficient deep-learning framework for automated segmentation and quantification of APP-positive pathology in porcine white matter histology. PIGMENT uses a compact SegFormer-B0 architecture trained on 525 expert-annotated 512 x 512-pixel tiles from four APP-stained sections across three pigs. Because APP-positive profiles are sparse, fragmented, stain-variable, and morphologically diverse, PIGMENT combines limited expert labels with APP-specific augmentation designed to model variation in APP-positive intensity, size, continuity, fragmentation, and local tissue context.

We evaluated PIGMENT using an instance-level detection rate that measures whether discrete APP-positive components are localized. Across held-out APP-stained data, PIGMENT achieved a mean instance-level detection rate of 0.86. Across the configurations tested, the highest mean detection rate was achieved by a training set that included sections from different animals, suggesting that annotation diversity may be an important factor under limited-label conditions.

By extending limited high-confidence expert annotations into whole-section APP burden maps, PIGMENT provides a scalable framework for characterizing the extent and spatial distribution of traumatic axonal injury. These maps may support future studies that align histological injury burden with imaging-derived measures.