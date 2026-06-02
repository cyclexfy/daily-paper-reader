---
title: Label-free 3D virtual histology of human formalin-fixed paraffin-embedded (FFPE) prostate needle biopsies with propagation-based phase-contrast micro-CT (PBCT)
title_zh: 基于传播相位衬度显微CT的人福尔马林固定石蜡包埋前列腺穿刺活检组织的无标记三维虚拟组织学
authors: "Sugarman, A. L., Vanselow, D. J., Chen, G., Clark, E., Parkinson, D., La Riviere, P., Silverman, J., Warrick, J., Cheng, K. C. C."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728215v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 使用相位衬度显微CT对前列腺活检进行3D虚拟组织学成像
tldr: "传统组织学依赖2D切片，存在采样不足和切片伪影。本研究采用传播相位衬度微CT对福尔马林固定石蜡包埋的前列腺穿刺活检进行无标记3D成像，获得0.5微米各向同性体素。该方法能清晰区分良性前列腺组织和不同Gleason分级（3、4、5型）的腺癌，包括筛状结构和粉刺状坏死。此外，基于cycleGAN可生成虚拟H&E染色。PBCT实现了无破坏的3D虚拟组织学，避免了传统组织学的缺点，为肿瘤定量分析提供新途径。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统2D组织学切片仅评估肿瘤极小部分，存在采样和切片伪影，无法充分表征3D细胞体积和组织结构。
method: "使用传播相位衬度微CT对FFPE前列腺活检进行无标记成像，获取0.5微米分辨率的3D体积，并用cycleGAN生成虚拟H&E染色。"
result: PBCT重建能区分良性组织和Gleason 3、4、5型前列腺癌的不同结构特征，并允许在3D背景下探索组织架构。
conclusion: 该技术实现了无破坏的3D虚拟组织学，避免了传统切片的不足，有望通过定量分析辅助前列腺癌诊疗。
---

## 摘要
一个多世纪以来，通过肿瘤活检样本估计临床结局的目标一直基于2D组织切片（仅代表收集样本的一小部分）的组织形态学。其力量源于组织学的：1）对细胞类型的无偏表示，2）亚细胞分辨率，可跨细胞类型表征健康和疾病状态，3）多毫米视野，可评估肿瘤异质性。然而，组织学对物理切片的依赖限制了对三维细胞体积和组织结构的评估。在此，我们使用传播相位衬度显微CT（PBCT）创建了残留福尔马林固定石蜡包埋（FFPE）前列腺穿刺活检样本的三维组织学图像。由此产生的各向同性、灰度、0.5微米体素矩阵用于探索三维虚拟组织学区分诊断类别的潜力，包括良性前列腺组织和Gleason分级3、4、5型的前列腺腺癌。对总计5微米厚度的数字切片堆栈进行最大强度投影，可研究对应于显微CT成像后实际连续H&E染色切片的虚拟切片。与组织学类似，我们的PBCT重建让我们能够区分良性前列腺组织的非浸润性和波浪状腺体、Gleason 3型的浸润性圆形腺体、Gleason 4型的筛状结构以及Gleason 5型的粉刺样坏死。不同于组织学，显微CT使我们能够进一步在体积背景下探索三维组织结构。通过定制的Neuroglancer多平面和三维渲染界面实现了对样本体积的用户友好探索。稀疏训练的cycleGAN从未染色的显微CT重建中生成了合理的虚拟H&E染色。与基于组织切片的组织学不同，基于显微CT的虚拟组织学能够无损地表征癌细胞和组织结构（包括腺腔空间），无组织学的欠采样或切片伪影。这些发现证明了基于PBCT的前列腺癌三维虚拟组织学的可行性，并提示可据此探索肿瘤特性的定量分析以潜在贡献于患者护理。

## Abstract
For over a century, the goal of estimating clinical outcome from tumor biopsies has been based on histomorphology of 2D tissue slices that represent a small fraction of collected samples. Its power derives from histology's 1) unbiased representation of cell types, 2) subcellular resolution that allows the characterization of health and disease states across cell types, and 3) multi-millimeter fields of view that allow assessment of tumor heterogeneity. Histology's dependence upon physical slices, however, limits assessment of 3-dimensional cellular volumes and tissue architecture. Here, we used propagation-based phase-contrast microCT (PBCT) to create 3D histological images of residual formalin-fixed, paraffin-embedded (FFPE) prostate needle biopsies. The resulting isotropic, grey-scale, 0.5 micron voxel matrices were used to explore the potential of for the 3D virtual histology to distinguish diagnostic categories including benign prostatic tissue and prostatic adenocarcinoma of Gleason patterns 3, 4, and 5. Maximum intensity projections of stacks of digital slices totaling 5 microns "slices" allowed the study of virtual sections corresponding to actual serial H&E-stained sections of tissue cut after microCT imaging. Like histology, our PBCT reconstructions allowed us to distinguish between non-infiltrative and undulating glands of benign prostatic tissue, infiltrative round glands of Gleason pattern 3, cribriform structures of Gleason pattern 4, and comedonecrosis of Gleason pattern 5. Unlike histology, microCT allowed us to further probe 3D tissue architecture in volumetric context. User-friendly exploration of sample volumes was achieved using a customized Neuroglancer multiplanar and 3D rendering interface. Sparsely trained cycleGAN produced plausible virtual H&E staining from the unstained microCT reconstructions. Unlike tissue-section based histology, microCT-based virtual histology yields nondestructive 3D characterization of cancer cell and tissue architecture, including glandular spaces, without the undersampling or cutting artifacts of histology. These findings demonstrate the feasibility of PBCT-based 3D virtual histology of prostate cancer and suggest the exploration of derived quantitative analyses of tumor properties for potential contributions to patient care.