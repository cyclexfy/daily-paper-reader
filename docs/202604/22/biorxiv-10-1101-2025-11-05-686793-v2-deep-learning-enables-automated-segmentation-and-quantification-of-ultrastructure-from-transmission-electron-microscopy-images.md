---
title: Deep Learning Enables Automated Segmentation and Quantification of Ultrastructure from Transmission Electron Microscopy Images
title_zh: 深度学习实现透射电子显微镜图像中超微结构的自动分割与定量分析
authors: "Zou, A., Tan, W., Ji, J., Rojas-Miguez, F., Dodd, L., Oei, E., Vargas, S. R., Yang, H., Berasi, S. P., Chen, H., Henderson, J. M., Fan, X., Lu, W., Zhang, C."
date: 2026-04-17
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.05.686793v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 深度学习用于显微镜图像临床诊断中的自动分割
tldr: 透射电子显微镜（TEM）在生物医学研究中至关重要，但其数据分析高度依赖人工且效率低下。本研究开发了TEAMKidney深度学习框架，通过结合自训练语义分割与定制的全景分割模型，实现了对肾脏超微结构的自动化、高精度量化。该框架在处理多物种、多倍率图像方面表现出色，显著降低了临床病理和科研中的图像分析负担，达到了专家级测量精度。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对透射电镜图像分析中人工标注耗时耗力、缺乏统一标准且难以处理复杂超微结构的问题，开发自动化量化工具。
method: 提出TEAMKidney框架，结合基于自训练的语义分割阶段与专门针对TEM图像设计的全景分割模型。
result: "在12,991张图像上验证，成功识别肾小球基底膜和足突的病理变化，性能优于现有工具并与专家测量高度一致。"
conclusion: 深度学习能有效替代繁琐的人工追踪，在保持专家级精度的同时大幅提升临床诊断和生物医学研究的效率。
---

## 摘要
透射电子显微镜（TEM）已成为观察亚细胞超微结构的重要技术，广泛应用于临床诊断和生物医学研究。然而，由于缺乏专门的计算方法，TEM 数据的分析仍然极其耗费人力，且由于操作员之间的差异，往往缺乏一致性。在此，我们提出了 TEAMKidney，这是一个深度学习框架，用于在不同物种、放大倍数和仪器平台下对 TEM 图像中的超微结构进行准确且可扩展的测量。我们收集了来自多种肾脏疾病患者和不同动物模型的 12,991 张 TEM 图像。通过将基于自训练的语义分割阶段与针对 TEM 定制的全景分割模型相结合，我们解决了 TEM 数据分析中的两个主要挑战：缺乏准确标记的训练数据，以及难以实现复杂超微结构的高精度分割。将 TEAMKidney 应用于人类和动物图像，成功揭示了两种关键肾小球超微结构（肾小球基底膜和足细胞足突）中与疾病相关的变化。除了显著优于现有工具外，TEAMKidney 与临床评估方案中使用的病理专家测量结果高度一致。通过减少对手动描绘的依赖并保持专家级精度，TEAMKidney 证明了深度学习可以显著减轻临床病理学和生物医学研究环境中的图像分析负担。

## Abstract
Transmission electron microscopy (TEM) has become an essential technique for observing subcellular ultrastructure, and is widely used in both clinical diagnosis and biomedical research. However, analysis of TEM data remains extremely labor-intensive and often inconsistent across operators due to the lack of dedicated computational methods. Here, we present TEAMKidney, a deep learning framework for accurate and scalable measurement of ultrastructures in TEM images across species, magnifications, and instrument platforms. We collected 12,991 TEM images from patients with multiple kidney diseases and from different animal models. By combining a self-training-based semantic segmentation stage with a TEM-tailored panoptic segmentation model, we address two major challenges in TEM data analysis: the lack of accurately labeled training data and the difficulty of achieving high segmentation accuracy for complex ultrastructure. Application of TEAMKidney to both human and animal images successfully reveals disease-associated changes in two critical glomerular ultrastructures: the glomerular basement membrane and podocyte foot processes. In addition to significantly outperforming existing tools, TEAMKidney shows close agreement with pathological expert measurements used in clinical assessment protocols. By reducing dependence on manual tracing while preserving expert-level accuracy, TEAMKidney demonstrates that deep learning can substantially reduce the burden of image analysis in both clinical pathology and biomedical research settings.