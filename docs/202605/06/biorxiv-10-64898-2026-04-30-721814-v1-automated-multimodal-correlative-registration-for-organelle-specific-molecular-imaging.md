---
title: Automated Multimodal Correlative Registration for Organelle-Specific Molecular Imaging
title_zh: 针对细胞器特异性分子成像的自动化多模态关联配准
authors: "Lu, C., ZHAO, K., Cui, D., Chen, G., Yang, Q., Yang, H., Zhao, M., Song, K., Nikan, M., Li, Z., Zhao, S., Cen, J., Qiu, X., Young, S., Bennett, C. F., Seth, P., Chen, K., Qi, X., Jiang, H."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721814v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 分子成像的多模态相关配准
tldr: 本研究针对亚细胞药物分布制图中的人工关联难题，开发了一种AI驱动的自动化多模态配准流水线。该方法通过整合双向光流和置信度引导的仿射变换，实现了NanoSIMS化学图像与电子显微镜超微结构图像的精准关联。通过利用形态丰富的离子通道引导稀疏治疗信号，克服了低信噪比挑战。该平台在多种细胞和组织中验证了其有效性，为研究药物在细胞器水平的分布提供了高效、通用的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的NanoSIMS与电子显微镜关联成像过程高度依赖人工且效率低下，阻碍了对药物在亚细胞水平分布的深入理解。
method: 提出一种集成双向光流、置信度引导仿射变换和自动模板匹配的AI流水线，利用形态丰富的离子通道信息辅助稀疏信号的跨尺度配准。
result: 在多种细胞和组织样本中成功实现了寡核苷酸及抗体药物的自动化精准对齐，揭示了特定细胞器内的药物分布模式。
conclusion: 该研究建立了一个通用的自动化多模态配准平台，显著提升了细胞器级分子成像的效率，为亚细胞药理学研究提供了有力支持。
---

## 摘要
绘制亚细胞药物分布图对于理解转运和脱靶效应至关重要。纳米二次离子质谱（NanoSIMS）能够对标记的治疗药物进行化学成像，但信号解读需要与电子显微镜进行超微结构关联，这是一个繁琐的人工过程。我们提出了一种自动化的 AI 驱动流程，用于关联化学和超微结构图像，实现了细胞和组织中分子的多尺度、细胞器精准成像。该方法集成了双向光流、置信度引导的仿射变换以及用于跨尺度电镜（EM）对齐的自动化模板匹配。形态丰富的离子通道（如 32S）用于估计变换，并将其传播到稀疏的治疗信号（如 79Br、15N），从而克服了低信噪比的挑战。我们在多种细胞和组织类型中验证了该框架，在体内外追踪了寡核苷酸和抗体药物，揭示了细胞类型和细胞器特异性的分布模式。这项工作为自动化多模态配准和细胞器分辨率的亚细胞药理学建立了一个可推广的平台。

## Abstract
Mapping subcellular drug distribution is essential for understanding trafficking and off-target effects. NanoSIMS enables chemical imaging of labeled therapeutics, but signal interpretation requires ultrastructural correlation with electron microscopy, a manual and laborious process. We present an automated AI-driven pipeline for correlating chemical and ultrastructural images, enabling multiscale, organelle-precise imaging of molecules in cells and tissues. The method integrates bidirectional optical flow, confidence-guided affine transformation, and automated template matching for cross-scale EM alignment. Morphology-rich ion channels (e.g., 32S) estimate transformations that propagate to sparse therapeutic signals (e.g., 79Br, 15N), overcoming low signal-to-noise challenges. We validate this framework across diverse cell and tissue types, tracking oligonucleotide and antibody therapeutics in vitro and in vivo to reveal cell-type- and organelle-specific distribution patterns. This work establishes a generalizable platform for automated multimodal registration and organelle-resolved subcellular pharmacology.