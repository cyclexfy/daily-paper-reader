---
title: Reconstructing True 3D Spatial Omics at Single-Cell Resolution
title_zh: 在单细胞分辨率下重建真实的 3D 空间组学
authors: "Yang, Y., Luo, Y., Zhang, K., Bu, Y., Xia, Z., Peng, H., Yan, R., Liu, Q., Chen, Y., Shen, L., Chen, E."
date: 2026-05-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721395v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 单细胞分辨率下3D空间组学的计算重建
tldr: 针对传统3D空间组学重建中物理切片破坏组织拓扑结构及2.5D堆叠方法无法还原连续分子梯度的难题，本文提出了DeepSpatial框架。该框架利用最优传输流匹配技术将组织演化建模为连续动态向量场，通过求解概率流常微分方程，实现了在任意空间深度提取高分辨率、无间断的组织状态。DeepSpatial在多种组学数据上表现出优异的重建保真度与扩展性，成功构建了包含3900万个细胞的小鼠全脑连续3D图谱，为理解复杂生物过程提供了高效的真3D空间重建方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的物理切片和2.5D堆叠方法会破坏组织的拓扑结构，且难以捕捉连续的深度依赖性分子梯度。
method: 提出DeepSpatial框架，采用最优传输流匹配技术将组织演化建模为连续动态向量场，并通过求解概率流常微分方程实现无间断重建。
result: 在蛋白质组学和转录组学等多种模态下实现了高保真重建，并高效完成了包含3900万个细胞的小鼠大脑大规模3D细胞图谱构建。
conclusion: DeepSpatial为跨尺度、跨模态的真3D空间组学重建提供了一个通用、高效且具有生物学可解释性的解决方案。
---

## 摘要
捕捉细胞的三维（3D）组织结构对于破译复杂的生物过程至关重要，然而，物理切片的破坏性以及完整组织成像的深度限制严重阻碍了全面的 3D 空间组学研究。目前的计算方法依赖于离散切片的 2.5D 堆叠，这本质上破坏了组织拓扑结构，且无法解析随深度变化的连续分子梯度。为了弥补这一差距，我们推出了 DeepSpatial，这是一个最优传输流匹配（Optimal Transport flow matching）框架，它将组织演变建模为连续的动态向量场。通过求解底层的概率流常微分方程（ODEs），DeepSpatial 能够直接提取任意空间深度下不间断且具有无限分辨率的组织状态。利用 Deep STAR/RIBOmap 3D 技术，我们证明了 DeepSpatial 相比 2.5D 方法实现了更高的 3D 重建保真度，在真实世界数据集中生成的结构能更紧密地重现原生组织微环境。在多种空间组学模态中，包括人类乳腺癌的成像质谱流式空间蛋白质组学，以及头颈部鳞状细胞癌转移淋巴结的 openST 空间转录组学，DeepSpatial 在不同数据集中均产生了具有生物学可解释性且高保真度的重建结果。我们在大规模小鼠大脑数据集上评估了 DeepSpatial 的可扩展性和鲁棒性，在 41.6 小时内重建了一个包含 3900 万个细胞的连续 3D 细胞图谱。系统的下游表征验证了其在不同脑区重现一致的空间架构、细胞类型分布、转录组模式和微环境结构的能力。总而言之，这些结果表明 DeepSpatial 是一种跨尺度、跨模态的真实 3D 空间重建的通用且高效的解决方案。

## Abstract
Capturing the three-dimensional (3D) organization of cells is essential for deciphering complex biological processes, yet comprehensive 3D spatial omics is severely hindered by the destructive nature of physical sectioning and the depth limitations of intact tissue imaging. Current computational methods rely on 2.5D stacking of discrete slices, which inherently disrupts tissue topology and fails to resolve continuous depth-dependent molecular gradients. To bridge this gap, we introduce DeepSpatial, an Optimal Transport flow matching framework that models tissue evolution as a continuous dynamic vector field. By solving the underlying probability flow ODEs, DeepSpatial enables the direct extraction of uninterrupted, infinitely resolvable tissue states at arbitrary spatial depths. Using Deep STAR/RIBOmap 3D technologies, we demonstrate that DeepSpatial achieves improved 3D reconstruction fidelity relative to 2.5D approaches, yielding structures that more closely recapitulate native tissue microenvironments in real-world datasets. Across diverse spatial omics modalities, including spatial proteomics using imaging mass cytometry in human breast cancer and spatial transcriptomics using openST in head and neck squamous cell carcinoma metastatic lymph nodes, DeepSpatial produces biologically interpretable and high-fidelity reconstructions across datasets. We evaluated the scalability and robustness of DeepSpatial on a large-scale mouse brain dataset, reconstructing a continuous 3D cellular atlas comprising 39 million cells within 41.6 hours. Systematic downstream characterization validated its ability to recapitulate consistent spatial architectures, cell-type distributions, transcriptomic patterns, and microenvironmental structures across brain regions. Collectively, these results demonstrate DeepSpatial as a generalizable and efficient solution for true 3D spatial reconstruction across scales and modalities.