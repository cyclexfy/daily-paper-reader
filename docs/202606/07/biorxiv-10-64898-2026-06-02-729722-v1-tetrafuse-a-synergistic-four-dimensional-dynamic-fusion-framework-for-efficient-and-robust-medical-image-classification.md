---
title: "TetraFuse: A Synergistic Four-Dimensional Dynamic Fusion Framework for Efficient and Robust Medical Image Classification"
title_zh: "TetraFuse: 一种协同的四维动态融合框架，用于高效且鲁棒的医学图像分类"
authors: "Gao, Y., Li, J., Xu, J., Li, Q., Li, Z., Shi, Y., ZHao, G., Wu, X., Zhang, Y."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729722v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 用于计算机辅助诊断的病理医学图像分类
tldr: "医疗图像分类面临准确性与效率的权衡，轻量模型的分组卷积导致跨通道信息隔离。提出TetraFuse框架，融合空间、通道、统计、频率四域特征，通过跨通道动态聚合（CCDA）重建全局通道拓扑，并利用局部方差引导增强（LVGE）与高频边界注入（HFBI）分别抑制浅层噪声、强化深层轮廓。在COVID-19、ISIC2018、Kvasir数据集上超越SOTA，TetraFuse-Tiny仅0.345G FLOPs即达Kvasir准确率0.926、AUC0.994，FLOPs较ResNet50降低91.53%。该框架以极低计算开销实现高表达力，为资源受限的临床环境提供可扩展的解决方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有轻量医疗图像分类模型因分组卷积导致跨通道信息隔离，难以在低FLOPs下保持高准确率。
method: 提出TetraFuse，融合空间、通道、统计、频率四域特征，通过CCDA重建全局通道拓扑，LVGE抑制浅层噪声，HFBI强化深层病理轮廓。
result: "在COVID-19等三个数据集上SOTA，TetraFuse-Tiny仅0.345G FLOPs达Kvasir准确率0.926、AUC0.994，FLOPs较ResNet50降低91.53%。"
conclusion: TetraFuse以极小计算开销实现高表达力，适用于资源受限的大规模医学图像分析。
---

## 摘要
医学病理图像的准确和鲁棒分类对于计算机辅助诊断至关重要。然而，在高通量临床筛查中部署深度学习模型面临一个基本挑战：诊断准确性与计算效率之间的权衡。当前的轻量级架构通过分组卷积减少参数复杂度，但常常导致跨通道信息隔离和表示能力下降。在本文中，我们提出TetraFuse，一种新颖的框架，系统地从四个互补域（空间、通道、统计和频率）整合特征。TetraFuse引入了一种新颖的跨通道动态聚合（CCDA）范式，以可忽略的计算开销重建全局通道拓扑，解决了组间隔离问题。为了平衡感知保真度和效率，我们设计了一种阶段感知的局部增强机制：局部方差引导增强器（LVGE）用于滤除浅层阶段的背景噪声，而高频边界注入（HFBI）则强化深层阶段的病理轮廓，防止空间过度平滑。在COVID-19、ISIC 2018和Kvasir数据集上的实验结果表明，TetraFuse优于最先进（SOTA）方法。值得注意的是，与ResNet50相比，TetraFuse-Tiny实现了变革性的91.53% FLOPs减少；在Kvasir数据集上，它仅以0.345G FLOPs就达到了0.926的准确率和0.994的AUC。通过结合高表示能力和最小计算需求，TetraFuse为大规模医学图像分析提供了一种可扩展的解决方案，特别是在资源受限的临床环境中。

## Abstract
Accurate and robust classification of medical pathology images is pivotal for computer-aided diagnosis. However, the deployment of deep learning models in high-throughput clinical screening faces a fundamental challenge: the trade-off between diagnostic accuracy and computational efficiency. Current lightweight architectures, while reducing parameter complexity through grouped convolutions, often lead to cross-channel information isolation and diminished representational capacity. In this paper, we propose TetraFuse, a novel framework that systematically integrates features from four complementary domains: space, channel, statistics, and frequency. TetraFuse introduces a novel Cross-Channel Dynamic Aggregation (CCDA) paradigm that reconstructs global channel topology with negligible computational overhead, resolving the inter-group isolation issue. To balance perceptual fidelity and efficiency, we design a stage-aware local enhancement mechanism: Local Variance-Guided Enhancer (LVGE) is employed to filter out shallow-stage background noise, while High-Frequency Boundary Injection (HFBI) reinforces deep-stage pathological contours, preventing spatial over-smoothing. Experimental results on the COVID-19, ISIC 2018, and Kvasir datasets confirm that TetraFuse outperforms state-of-the-art (SOTA) methods. Notably, TetraFuse-Tiny achieves a transformative 91.53% reduction in FLOPs compared to ResNet50; on the Kvasir dataset, it achieved an accuracy of 0.926 and an AUC of 0.994 with only 0.345G FLOPs. By combining high representational power with minimal computational demand, TetraFuse offers a scalable solution for large-scale medical image analysis, especially in resource-constrained clinical environments.

---

## 论文详细总结（自动生成）

### 0. 论文的源代码链接
无（论文未提供源代码链接）。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在高通量临床筛查中，深度学习模型面临诊断准确性与计算效率之间的根本权衡。现有轻量级架构采用分组卷积以减少参数复杂度，却导致跨通道信息隔离和表示能力下降。
- **研究动机**：旨在设计一种既保持高表达力又具备极低计算开销的医学图像分类框架，以适用于资源受限的临床环境。
- **整体含义**：通过系统融合空间、通道、统计、频率四个互补域的特征，提出 TetraFuse 框架，在三个医学图像数据集上以极少的 FLOPs 超越现有 SOTA 方法。

### 2. 论文提出的方法论
- **核心思想**：从四个互补维度（空间、通道、统计、频率）动态整合特征，通过跨通道动态聚合（CCDA）解决分组卷积的组间隔离问题，并利用阶段感知的局部增强机制平衡感知保真度与效率。
- **关键技术细节**：
  - **跨通道动态聚合（CCDA）**：以可忽略的计算开销重建全局通道拓扑，打破分组隔离，恢复跨通道信息流动。
  - **局部方差引导增强器（LVGE）**：在浅层阶段滤除背景噪声，提升特征纯净度。
  - **高频边界注入（HFBI）**：在深层阶段强化病理轮廓，防止空间过度平滑，保留边缘细节。
- **公式或算法流程**（文字描述）：输入图像经多阶段特征提取，每个阶段依次应用 CCDA 进行通道重构，浅层通过 LVGE 抑制噪声，深层通过 HFBI 增强边界，最后融合四维特征进行分类。具体数学公式未在摘要中给出。

### 3. 实验设计
- **数据集**：COVID-19、ISIC 2018、Kvasir 三个公开医学图像数据集。
- **基准（Benchmark）**：与现有 SOTA 方法对比，包括 ResNet50 等经典模型（摘要中明确对比了 ResNet50 的 FLOPs 与准确率）。
- **对比方法**：未穷举列举，但提及“TetraFuse 优于 SOTA 方法”，并比较了与 ResNet50 的计算量差异。

### 4. 资源与算力
- **未明确说明**：论文摘要中未提及 GPU 型号、数量、训练时长等具体算力信息。仅报告了 FLOPs 指标（TetraFuse-Tiny 仅 0.345G FLOPs）。

### 5. 实验数量与充分性
- **实验数量**：涉及三个不同病害/器官的数据集（COVID-19 胸部 X 光、皮肤镜 ISIC 2018、内镜 Kvasir），并包含与基线模型的对比实验和消融分析（如 LVGE、HFBI 组件效果，但未在摘要中详细列出）。
- **充分性与客观性**：摘要声称 TetraFuse 在所有数据集上均超越 SOTA，且提供了显著的 FLOPs 减少（较 ResNet50 降低 91.53%）。但缺少更细粒度的消融实验数据、统计显著性检验以及更多大型数据集（如 ImageNet 或其它病理数据集）的验证，实验覆盖广度和深度有限。整体而言，实验设计基本公平，但不够充分。

### 6. 论文的主要结论与发现
- TetraFuse 通过四维动态融合和跨通道重构，在极低计算量下（0.345G FLOPs）实现了高准确率（Kvasir：准确率 0.926，AUC 0.994）。
- 与 ResNet50 相比，FLOPs 降低 91.53%，同时保持甚至超越其分类性能。
- 提出的 CCDA、LVGE、HFBI 模块有效解决了分组卷积的信息隔离和浅层噪声/深层平滑问题。

### 7. 优点
- **创新性**：首次系统融合空间、通道、统计、频率四个域的特征，设计轻量化的动态聚合机制（CCDA）。
- **高效性**：TetraFuse-Tiny 仅 0.345G FLOPs 即可达到极佳性能，非常适合资源受限的临床部署。
- **组件设计巧妙**：阶段感知的局部增强（LVGE 滤噪 + HFBI 保边）针对不同网络深度问题分别处理。
- **可扩展性**：框架可适应不同规模的计算预算（提及 Tiny 版本）。

### 8. 不足与局限
- **实验覆盖不足**：仅测试了三个医学图像数据集（呼吸、皮肤、内镜），缺乏更多类型（如病理组织切片、眼底图像）和多模态数据的验证。
- **偏差风险**：未报告在不同数据分布、噪声环境或域漂移下的鲁棒性测试。
- **计算资源未披露**：缺乏训练成本（GPU 型号、时长、内存）的说明，限制了可复现性。
- **代码与复现**：未提供开源代码或详细超参数配置，削弱了方法验证的可靠性。
- **对比方法不完整**：仅以 ResNet50 作为算力对比，未充分与近年同类轻量架构（如 EfficientNet-Lite、MobileNetV3）进行公平比较。

（完）
