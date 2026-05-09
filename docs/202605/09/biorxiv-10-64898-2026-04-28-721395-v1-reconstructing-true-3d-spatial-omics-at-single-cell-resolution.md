---
title: Reconstructing True 3D Spatial Omics at Single-Cell Resolution
title_zh: 重构单细胞分辨率下的真实三维空间组学
authors: "Yang, Y., Luo, Y., Zhang, K., Bu, Y., Xia, Z., Peng, H., Yan, R., Liu, Q., Chen, Y., Shen, L., Chen, E."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721395v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 3D空间组学重建的计算方法
tldr: 针对物理切片和成像深度限制导致的3D空间组学重建难题，本文提出了DeepSpatial框架。该方法利用最优传输流匹配技术将组织演化建模为连续动态向量场，通过求解概率流常微分方程，实现了在任意空间深度提取无限分辨率的组织状态。DeepSpatial在多种组学模态和大规模数据集（如3900万个细胞的小鼠大脑）上展现了卓越的重建保真度、可扩展性和生物学解释力，为构建真实3D单细胞空间图谱提供了高效通用的解决方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的2.5D切片堆叠方法会破坏组织拓扑结构并丢失连续的分子梯度，难以实现高保真度的真实3D空间组学重建。
method: 提出DeepSpatial框架，采用最优传输流匹配技术将组织建模为连续动态向量场，通过求解概率流ODE实现任意深度的组织状态提取。
result: 在乳腺癌、头颈癌及大规模小鼠大脑数据集上验证了该方法，成功在41.6小时内重建了包含3900万个细胞的连续3D图谱。
conclusion: DeepSpatial为跨尺度、跨模态的单细胞分辨率3D空间组学重建提供了一个高效、稳健且具有高度生物学保真度的通用解决方案。
---

## 摘要
捕捉细胞的三维（3D）组织结构对于破译复杂的生物过程至关重要，然而，物理切片的破坏性以及完整组织成像的深度限制严重阻碍了全面的3D空间组学研究。目前的计算方法依赖于离散切片的2.5D堆叠，这本质上破坏了组织拓扑结构，且无法解析连续的深度依赖性分子梯度。为了弥补这一差距，我们引入了 DeepSpatial，这是一个基于最优传输流匹配（Optimal Transport flow matching）的框架，将组织演变建模为连续的动态向量场。通过求解底层的概率流常微分方程（ODEs），DeepSpatial 能够直接提取任意空间深度下不间断且无限可分辨的组织状态。利用 Deep STAR/RIBOmap 3D 技术，我们证明了 DeepSpatial 相比于 2.5D 方法实现了更高的 3D 重构保真度，在真实世界数据集中生成的结构能更紧密地还原原生组织微环境。在多种空间组学模态中，包括使用成像质谱流式技术的人类乳腺癌空间蛋白质组学，以及使用 openST 的头颈部鳞状细胞癌转移淋巴结空间转录组学，DeepSpatial 在不同数据集上均产生了具有生物学可解释性且高保真度的重构结果。我们在大规模小鼠大脑数据集上评估了 DeepSpatial 的可扩展性和鲁棒性，在 41.6 小时内重构了一个包含 3900 万个细胞的连续 3D 细胞图谱。系统的下游表征验证了其在不同脑区还原一致的空间架构、细胞类型分布、转录组模式和微环境结构的能力。总而言之，这些结果表明 DeepSpatial 是一种适用于跨尺度和跨模态的真实 3D 空间重构的通用且高效的解决方案。

## Abstract
Capturing the three-dimensional (3D) organization of cells is essential for deciphering complex biological processes, yet comprehensive 3D spatial omics is severely hindered by the destructive nature of physical sectioning and the depth limitations of intact tissue imaging. Current computational methods rely on 2.5D stacking of discrete slices, which inherently disrupts tissue topology and fails to resolve continuous depth-dependent molecular gradients. To bridge this gap, we introduce DO_SCPLOWEEPC_SCPLOWSO_SCPLOWPATIALC_SCPLOW, an Optimal Transport flow matching framework that models tissue evolution as a continuous dynamic vector field. By solving the underlying probability flow ODEs, DO_SCPLOWEEPC_SCPLOWSO_SCPLOWPATIALC_SCPLOW enables the direct extraction of uninterrupted, infinitely resolvable tissue states at arbitrary spatial depths. Using Deep STAR/RIBOmap 3D technologies, we demonstrate that DO_SCPLOWEEPC_SCPLOWSO_SCPLOWPATIALC_SCPLOW achieves improved 3D reconstruction fidelity relative to 2.5D approaches, yielding structures that more closely recapitulate native tissue microenvironments in real-world datasets. Across diverse spatial omics modalities, including spatial proteomics using imaging mass cytometry in human breast cancer and spatial transcriptomics using openST in head and neck squamous cell carcinoma metastatic lymph nodes, DO_SCPLOWEEPC_SCPLOWSO_SCPLOWPATIALC_SCPLOW produces biologically interpretable and high-fidelity reconstructions across datasets. We evaluated the scalability and robustness of DO_SCPLOWEEPC_SCPLOWSO_SCPLOWPATIALC_SCPLOW on a large-scale mouse brain dataset, reconstructing a continuous 3D cellular atlas comprising 39 million cells within 41.6 hours. Systematic downstream characterization validated its ability to recapitulate consistent spatial architectures, cell-type distributions, transcriptomic patterns, and microenvironmental structures across brain regions. Collectively, these results demonstrate DO_SCPLOWEEPC_SCPLOWSO_SCPLOWPATIALC_SCPLOW as a generalizable and efficient solution for true 3D spatial reconstruction across scales and modalities.