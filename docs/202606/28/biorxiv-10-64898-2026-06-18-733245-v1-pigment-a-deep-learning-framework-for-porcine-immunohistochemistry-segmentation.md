---
title: "PIGMENT: A deep learning framework for Porcine Immunohistochemistry seGMENTation"
title_zh: PIGMENT：一种用于猪免疫组化图像分割的深度学习框架
authors: "Ambastha, P., Dadashkarimi, J., Annavazala, S. K. C., Parker, D., Diaz-Arrastia, R., Song, H., Smith, D. H., Dolle, J.-P., Johnson, V. E., Wolf, J. A., Verma, R."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733245v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 深度学习方法用于免疫组化组织图像分割，适用于病理学
tldr: "创伤性脑损伤后轴突损伤的量化依赖费时的手动标注，限制了可重复性。PIGMENT框架基于SegFormer-B0，结合有限专家标注与APP特异性增强，实现阳性病理的自动化分割。在猪白质切片上达到86%的实例级检测率，并生成全切片损伤负荷图。该方法为组织学与影像学对齐提供了可扩展的量化工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 手动量化APP病理耗时长且不一致，限制组织学与影像学对照研究。
method: 采用SegFormer-B0架构，结合专家标注及APP特异性增强，应对稀疏、形态多样的阳性特征。
result: 在猪白质切片上实现0.86实例级检测率，多样本训练提升性能。
conclusion: PIGMENT生成全切片损伤图，可扩展用于组织学-影像学关联分析。
---

## 摘要
创伤性脑损伤会产生广泛的轴突损伤，可通过淀粉样前体蛋白（APP）免疫组化进行组织学评估，该技术以细胞分辨率标记受损的轴突轮廓[1,2]。然而，APP病理的量化仍是一个主要瓶颈：标注是手动的、耗时的、空间局部的，且不同评估者之间存在差异，限制了可扩展性和可重复性。在将组织学作为神经影像或其他组织水平测量参考的研究中，这一限制尤为重要，因为细胞水平的APP病理必须以能与影像异常对齐的空间形式进行量化。

在此，我们介绍PIGMENT，一种用于猪白质组织学中APP阳性病理自动分割和量化的标注高效深度学习框架。PIGMENT采用紧凑的SegFormer-B0架构，在来自三头猪的四张APP染色切片的525个专家标注的512×512像素图块上训练。由于APP阳性轮廓稀疏、碎片化、染色变异且形态多样，PIGMENT将有限的专家标签与针对APP的增广相结合，旨在模拟APP阳性强度、大小、连续性、碎片化和局部组织背景的变异。

我们使用实例级检测率（衡量离散APP阳性成分是否被定位）评估了PIGMENT。在保留的APP染色数据上，PIGMENT的平均实例级检测率达到0.86。在所测试的配置中，包含来自不同动物切片的训练集实现了最高的平均检测率，这表明在标签有限的条件下，标注多样性可能是一个重要因素。

通过将有限的高置信度专家标注扩展为全切片APP负担图，PIGMENT为表征创伤性轴突损伤的程度和空间分布提供了一个可扩展的框架。这些图可能支持未来将组织学损伤负担与影像衍生测量对齐的研究。

## Abstract
Traumatic brain injury produces widespread axonal damage can be assessed histologically using amyloid precursor protein (APP) immunohistochemistry, which labels injured axonal profiles at cellular resolution [1, 2]. However, quantification of APP pathology remains a major bottleneck: annotation is manual, time-consuming, spatially localized, and variable across raters, limiting scalability and reproducibility. This limitation is particularly important in studies that use histology as a reference for neuroimaging or other tissue-level measurements, where cellular APP pathology must be quantified in a spatial form that can be aligned with imaging abnormalities.

Here, we introduce PIGMENT, an annotation-efficient deep-learning framework for automated segmentation and quantification of APP-positive pathology in porcine white matter histology. PIGMENT uses a compact SegFormer-B0 architecture trained on 525 expert-annotated 512 x 512-pixel tiles from four APP-stained sections across three pigs. Because APP-positive profiles are sparse, fragmented, stain-variable, and morphologically diverse, PIGMENT combines limited expert labels with APP-specific augmentation designed to model variation in APP-positive intensity, size, continuity, fragmentation, and local tissue context.

We evaluated PIGMENT using an instance-level detection rate that measures whether discrete APP-positive components are localized. Across held-out APP-stained data, PIGMENT achieved a mean instance-level detection rate of 0.86. Across the configurations tested, the highest mean detection rate was achieved by a training set that included sections from different animals, suggesting that annotation diversity may be an important factor under limited-label conditions.

By extending limited high-confidence expert annotations into whole-section APP burden maps, PIGMENT provides a scalable framework for characterizing the extent and spatial distribution of traumatic axonal injury. These maps may support future studies that align histological injury burden with imaging-derived measures.