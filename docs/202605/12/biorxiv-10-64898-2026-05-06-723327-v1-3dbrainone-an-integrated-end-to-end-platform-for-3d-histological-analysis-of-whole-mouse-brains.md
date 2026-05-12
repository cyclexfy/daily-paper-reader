---
title: "3DBrainOne: an integrated end-to-end platform for 3D histological analysis of whole mouse brains"
title_zh: 3DBrainOne：用于全小鼠脑3D组织学分析的集成端到端平台
authors: "Park, Y.-G., Kim, D."
date: 2026-05-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.06.723327v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于全器官成像的3D组织学分析和深度学习
tldr: 3DBrainOne是一个集成在ImageJ中的端到端全脑3D组织学分析平台，旨在解决大规模成像数据处理中的工具匮乏问题。它涵盖了从图像预处理、基于深度学习的细胞计数、多通道共定位到脑区图谱对齐及定量分析的完整流程。该平台提供直观的GUI界面，支持人工校验，显著降低了神经科学研究中全脑定量分析的门槛。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对全脑3D成像数据量巨大且缺乏集成化、易用的定量分析工具这一瓶颈问题。
method: 开发了一个基于ImageJ的插件，结合DoG斑点检测算法与ResNet18深度学习分类器进行细胞计数，并集成图谱对齐模块。
result: 实现了高精度的全脑自动细胞计数、多通道共定位分析以及基于脑区的体积定量，并支持可视化检查与手动修正。
conclusion: 3DBrainOne是一个功能全面、跨平台且用户友好的工具，将有力推动实验神经科学中的3D组织学定量研究。
---

## 摘要
细胞分辨率下的三维（3D）全器官成像与分析（称为3D组织学）为整个器官内细胞的组织和相互作用提供了深刻见解。然而，由于缺乏集成的、用户友好的工具，这些海量数据集的定量分析仍然是一个重大瓶颈。在此，我们推出了3DBrainOne，这是一个端到端的ImageJ插件，它在单一平台内简化了从小鼠脑原始图像预处理到区域定量分析的关键3D组织学分析流程。3DBrainOne具有一个稳健的全脑细胞计数模块，该模块使用高斯差分（DoG）斑点检测算法，随后配合基于ResNet18的深度学习分类器，实现了高保真的自动全脑细胞计数，并提供图形用户界面（GUI）用于分析结果的视觉检查和人工校正。3DBrainOne还支持多通道共定位分析。此外，该平台还包括脑图谱对齐和脑区域体积定量模块，从而实现脑区域分辨的细胞计数和结构分析。作为ImageJ插件，3DBrainOne兼容多种操作系统和硬件。总之，3DBrainOne是一个集成、多功能且易于使用的平台，将促进实验神经科学中的3D组织学分析。

## Abstract
Three-dimensional (3D) whole-organ imaging and analysis at cellular resolution (termed 3D histology) provide profound insights into the organization and interactions of cells throughout organs. However, the quantitative analysis of these massive datasets remains a significant bottleneck due to the lack of integrated, user-friendly tools. Here, we present 3DBrainOne, an end-to-end ImageJ plugin that streamlines the essential 3D histological analysis of the mouse brain, from raw image preprocessing to region-wise quantification, within a single platform. 3DBrainOne features a robust whole-brain cell-counting module that uses a Difference-of-Gaussians (DoG) blob detection algorithm followed by a ResNet18-based deep learning classifier, enabling high-fidelity automatic whole-brain cell counting with a graphical user interface (GUI) for visual inspection and manual curation of analysis results. 3DBrainOne also supports multi-channel colocalization analysis. Furthermore, this platform includes modules for atlas alignment and brain-region-wise volumetric quantification, enabling brain region-resolved cell counting and structural analyses. As an ImageJ plugin, 3DBrainOne is compatible with a range of operating systems and hardware. In summary, 3DBrainOne is an integrated, versatile, and easy-to-use platform that will facilitate 3D histological analyses in experimental neuroscience.