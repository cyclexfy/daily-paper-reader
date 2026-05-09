---
title: "BaSiCPy: Scalable and Robust Shading Correction for Optical Microscopy Images"
title_zh: BaSiCPy：用于光学显微图像的可扩展且鲁棒的阴影校正
authors: "Liu, Y., Fukai, Y. T., Cano-Muniz, S., Perez, V., Todorov, M., Ortega, G., Morello, T., Loeffler, D., Paetzold, J., Xu, X., Lamm, L., Ma, N., Erturk, A., Schroeder, T., Boeck, L., Schapiro, D., Schaub, N., Marr, C., Peng, T."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721386v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 生物研究中光学显微镜图像的遮光校正
tldr: 定量荧光显微成像常受光照不均和强度漂移干扰。虽然BaSiC是常用校正方法，但在处理具有强相关前景结构（如延时或平铺成像）时效果不佳，且需手动调参。本文推出BaSiCPy，这是一款感知前景的Python实现，通过自动超参数选择和GPU加速，显著提升了在复杂场景下的校正精度与处理效率，为生物图像分析提供了开源且可扩展的解决方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对现有BaSiC方法在处理强相关前景图像时鲁棒性不足且手动调参限制了可扩展性的问题。
method: 开发了感知前景的BaSiCPy算法，引入自动超参数选择并支持GPU加速计算。
result: 提高了在相关前景结构下的光照分布估计精度，并实现了大规模图像数据的快速处理。
conclusion: BaSiCPy作为一个开源工具，通过提高校正的鲁棒性和自动化程度，有效促进了现代生物图像分析工作流的集成。
---

## 摘要
定量荧光显微镜经常受到空间变化的照明和时间强度漂移的干扰。虽然 BaSiC 是一种被广泛采用的回溯性校正方法，但当图像间的前景内容具有强相关性时（这在延时、平铺和体积采集模式中很常见），该方法可能会失效，且其应用通常需要手动调节参数，限制了可重复性和可扩展性。我们推出了 BaSiCPy，这是 BaSiC 的一种前景感知实现，它改进了相关前景结构下的照明轮廓估计，提供了自动超参数选择，并通过 GPU 支持加速了大规模处理。BaSiCPy 以开源 Python 包的形式发布，具有图形和编程接口，便于集成到现代生物图像分析工作流中。

## Abstract
Quantitative fluorescence microscopy is frequently confounded by spatially varying illumination and temporal intensity drift. Although BaSiC is a widely adopted retrospective correction method, it can fail when foreground content is strongly correlated across images--a common regime in time-lapse, tiled and volumetric acquisitions--and its application often requires manual parameter tuning that limits reproducibility and scalability. We introduce BaSiCPy, a foreground-aware implementation of BaSiC that improves illumination profile estimation under correlated foreground structures, provides automatic hyperparameter selection and accelerates large-scale processing through GPU support. BaSiCPy is distributed as an open-source Python package with graphical and programmatic interfaces, facilitating integration into contemporary bioimage analysis workflows.