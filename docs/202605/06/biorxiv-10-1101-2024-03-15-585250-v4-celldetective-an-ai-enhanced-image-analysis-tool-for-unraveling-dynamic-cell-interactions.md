---
title: "Celldetective: an AI-enhanced image analysis tool for unraveling dynamic cell interactions"
title_zh: Celldetective：一种用于揭示动态细胞相互作用的AI增强型图像分析工具
authors: "Torro, R., Diaz Bello, B., El Arawi, D., Dervanova, K., Ammer, L., Dupuy, F., Chames, P., Sengupta, K., Limozin, L."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.1101/2024.03.15.585250v4.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 用于多模态和多维生物成像数据的人工智能增强分析工具
tldr: Celldetective是一款基于Python的开源图像分析工具，旨在解决免疫学和免疫治疗研究中多模态、多维动态细胞交互分析的难题。该工具集成了AI驱动的分割、追踪及单细胞事件自动检测功能，并提供直观的图形界面。通过对双特异性抗体介导的免疫细胞交互和抗体依赖性细胞毒性（ADCC）等数据集的分析，展示了其在处理复杂生物系统和混合细胞群体中的高效性能。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对免疫学研究中多模态、多维动态细胞交互数据分析困难且缺乏高效端到端工具的现状。
method: 开发了一个集成AI分割、追踪和自动化事件检测功能的开源Python软件，并配备交互式图形用户界面。
result: 成功应用于分析双特异性抗体介导的免疫效应细胞交互及抗体依赖性细胞毒性事件等原始数据集。
conclusion: Celldetective为生物成像领域提供了一个强大且通用的分析平台，能有效提升复杂细胞交互研究的效率和准确性。
---

## 摘要
分析捕捉不同细胞群体之间动态相互作用的多模态和多维数据是当前生物成像领域的一项挑战，特别是在免疫学和免疫治疗研究背景下。在此，我们介绍了 Celldetective，这是一款基于 Python 的开源软件工具，旨在对基于图像的体外免疫和免疫治疗实验进行高性能、端到端的分析。Celldetective 专为混合细胞群体的多条件、二维多通道延时显微成像而设计。尽管它针对免疫学实验的需求进行了优化，但它仍广泛适用于任何涉及相互作用细胞群体的生物系统。该软件将基于 AI 的分割、追踪和自动单细胞事件检测无缝集成在一个直观的图形界面中，支持交互式可视化、标注和训练选项。我们通过原始数据集展示了其功能，这些数据集包括由双特异性抗体介导的单个免疫效应细胞与激活表面的相互作用，以及抗体依赖性细胞毒性事件中的成对相互作用。

## Abstract
Analysis of multimodal and multidimensional data capturing dynamic interactions between diverse cell populations is a current challenge in bioimaging, especially in the context of immunology and immunotherapy research. Here, we introduce Celldetective, an open-source Python-based software tool designed for high-performance, end-to-end analysis of image-based in vitro immune and immunotherapy assays. Celldetective is purpose-built for multicondition, 2D multi-channel time-lapse microscopy of mixed cell populations. Although it is optimised for the needs of immunology assays, it is nevertheless broadly applicable to any biological system involving interacting cell populations. The software seamlessly integrates AI-based segmentation, tracking, and automated single-cell event detection, all within an intuitive graphical interface that supports interactive visualisation, annotation, and training options. We showcase its capabilities with original datasets of single immune effector cell interactions with an activating surface mediated by bispecific antibodies, and pairwise interactions in antibody-dependent cell cytotoxicity events.