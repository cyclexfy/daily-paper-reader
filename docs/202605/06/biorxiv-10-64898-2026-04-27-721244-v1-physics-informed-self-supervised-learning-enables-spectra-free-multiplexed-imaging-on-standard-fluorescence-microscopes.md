---
title: Physics-informed self-supervised learning enables spectra-free multiplexed imaging on standard fluorescence microscopes
title_zh: 物理信息引导的自监督学习在标准荧光显微镜上实现无光谱多重成像
authors: "Xia, J., Yan, J., Tang, M., Zhao, B., Chen, K."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.27.721244v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 标准荧光显微镜多重成像的自监督框架
tldr: 针对标准荧光显微镜通道有限及光谱重叠导致的多重成像难题，本研究提出PhySMI框架。该框架利用物理信息自监督学习，在无需成对标签的情况下实现欠定光谱解混。它能从3个激发通道中解析出5种亚细胞结构，具有低串扰、高保真度和强泛化性，显著提升了活细胞多色成像的时空分辨率并降低了光毒性。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统荧光显微镜受限于激发/发射通道数量和光谱重叠，难以在不增加硬件复杂性的情况下实现高通量多重成像。
method: 提出PhySMI自监督框架，将光谱前向混合过程嵌入自一致架构中，通过物理约束从无标注数据中恢复源分解。
result: "成功从3个激发通道中解析出5种亚细胞结构，串扰低于0.5%，并实现了在标准显微镜上的零样本部署和高速活细胞成像。"
conclusion: 该研究为解决欠定成像逆问题提供了通用物理信息学习策略，为标准显微镜平台实现高通量多重成像奠定了基础。
---

## 摘要
多重荧光成像受限于光谱重叠以及标准显微镜上有限的激发或发射通道数量，这使得大多数实验室仅能进行低重成像。在此，我们介绍了物理信息引导的无光谱多重成像（PhySMI），这是一个用于欠定光谱解混的自监督框架，在训练后无需密集的光谱测量即可实现高重成像。通过将光谱正向混合过程嵌入到自洽架构中，PhySMI 能够从无标签数据中恢复物理上合理的源分解，而无需成对的地面真值标签，同时抑制随机采集噪声。PhySMI 仅通过三个激发通道即可解析五种亚细胞结构，克服了传统的通道数量限制，同时保持了光谱保真度并最小化了串扰（<0.5%）。该框架还具有跨成像系统的泛化能力，能够在标准荧光显微镜上实现零样本部署。在活细胞中，与传统光谱成像相比，PhySMI 能够对动态多细胞器相互作用进行快速五色成像，并具有更高的延时分辨率，同时减少了光漂白和光毒性。这些结果为欠定成像逆问题中的物理信息学习建立了一种通用策略，并代表了向标准显微镜平台上通用高重荧光成像框架迈出的一步。

## Abstract
Multiplexed fluorescence imaging is limited by spectral overlap and the small number of excitation or emission channels available on standard microscopes, restricting most laboratories to low-plex imaging. Here we introduce physics-informed spectra-free multiplexed imaging (PhySMI), a self-supervised framework for underdetermined spectral unmixing that enables highly multiplexed imaging without dense spectral measurements after training. By embedding the spectral forward-mixing process into a self-consistent architecture, PhySMI recovers physically plausible source decompositions from unlabeled data without paired ground-truth labels while suppressing stochastic acquisition noise. PhySMI resolves five subcellular structures from only three excitation channels, overcoming the conventional channel-number limit while preserving spectral fidelity and minimizing crosstalk (<0.5%). The framework also generalizes across imaging systems, enabling zero-shot deployment on standard fluorescence microscopes. In live cells, PhySMI enables fast five-color imaging of dynamic multi-organelle interactions with improved temporal resolution and reduced photobleaching and phototoxicity relative to conventional spectral imaging. These results establish a general strategy for physics-informed learning in underdetermined imaging inverse problems and represent a step toward a general-purpose framework for highly multiplexed fluorescence imaging on standard microscopy platforms.