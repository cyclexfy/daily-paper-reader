---
title: Unifying the Electron Microscopy Multiverse through a Large-scale Foundation Model
title_zh: 通过大规模基础模型统一电子显微镜多元宇宙
authors: "He, L., Shi, R., Wang, W., Fang, G., Cai, Y., Ma, L."
date: 2026-05-12
pdf: "https://www.biorxiv.org/content/10.1101/2025.04.13.648639v4.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于电子显微镜图像的大规模基础模型
tldr: 本研究针对电子显微镜（EM）图像分析中数据异质性和工作流碎片化的问题，推出了首个大规模EM基础模型EM-DINO。该模型在包含500万张图像的EM-5M数据集上进行预训练，能够捕捉多尺度特征。基于此，研究者开发了OmniEM架构，实现了统一的图像修复与分割。该工具包不仅在多项任务中超越了现有模型，还提供了Napari插件，为标准化EM分析和亚细胞结构研究提供了强有力的支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 电子显微镜图像存在高度异质性和工作流碎片化，阻碍了大规模、跨任务的生物结构分析。
method: 提出了在500万张图像数据集上预训练的EM-DINO基础模型，并构建了用于密集预测任务的OmniEM架构。
result: OmniEM在图像修复和2D/3D细胞器分割任务中均优于特定任务模型，且能从低分辨率输入生成高质量分割。
conclusion: 该研究通过整合数据集、基础模型和工具插件，为电子显微镜领域的标准化分析和生物学发现提供了端到端的解决方案。
---

## 摘要
电子显微镜（EM）图像的准确分析对于探索纳米级生物结构至关重要，但数据异质性和碎片化的工作流程阻碍了可扩展的洞察。在大型、多样化数据集上预训练的图像基础模型为学习跨任务的可迁移表示提供了一个稳健的框架。在此，我们介绍了 EM-DINO，这是首个在 EM-5M 上预训练的 EM 图像基础模型。EM-5M 是一个经过策划和标准化的 EM 大型语料库（包含 500 万张图像），涵盖了多种物种、组织、实验方案和分辨率。EM-DINO 的多尺度嵌入捕获了丰富的图像特征，支持多种应用，包括器官特异性模式识别、图像去重和高质量图像修复。基于这些表示，我们开发了 OmniEM，这是一种用于统一密集预测的 U 型架构，在图像修复和分割方面均优于特定任务模型。在修复基准测试中，OmniEM 的性能与 EM 特有的扩散模型相当，同时减少了可能误导解释的伪影。它在 2D 和 3D 线粒体分割以及多类别细胞器分割任务中也优于以往的方法。此外，我们展示了 OmniEM 从低分辨率输入生成高分辨率分割的集成能力，为在遗留和高通量 EM 数据集中进行精细的亚细胞分析提供了可能。EM-5M、EM-DINO、OmniEM 以及集成的 Napari 插件共同构成了一个用于标准化 EM 分析的综合端到端工具包，促进了对细胞和亚细胞的理解，并加速了新型细胞器形态和疾病相关变化的发现。

## Abstract
Accurate analysis of electron microscopy (EM) images is essential for exploring nanoscale biological structures, yet data heterogeneity and fragmented workflows hinder scalable insights. Pretrained on large, diverse datasets, image foundation models provide a robust framework for learning transferable representations across tasks. Here, we introduce EM-DINO, the first EM image foundational model pretrained on EM-5M, a large curated and standardized EM corpus (5 million images) encompassing multiple species, tissues, protocols, and resolutions. EM-DINOs multi-scale embeddings capture rich image features that support multiple applications, including organ-specific pattern recognition, image deduplication, and high quality image restoration. Building on these representations, we developed OmniEM, a U-shaped architecture for unified dense prediction that achieves superior performance compared with task-specific models in both image restoration and segmentation. In restoration benchmarks, OmniEM matches the performance of the EM-specific diffusion model while reducing spurious structural artifacts that could mislead interpretation. It also outperforms previous methods across 2D and 3D mitochondrial segmentation, as well as multi-class organelle segmentation tasks. Furthermore, we demonstrate OmniEMs integrated capability to generate high-resolution segmentations from low-resolution inputs, offering the potential to enable fine-scale subcellular analysis in legacy and high-throughput EM datasets. Together, EM-5M, EM-DINO, OmniEM, and an integrated Napari plugin comprise a comprehensive end-to-end toolkit for standardized EM analysis, advancing cellular and subcellular understanding and accelerating the discovery of novel organelle morphologies and disease-related alterations.