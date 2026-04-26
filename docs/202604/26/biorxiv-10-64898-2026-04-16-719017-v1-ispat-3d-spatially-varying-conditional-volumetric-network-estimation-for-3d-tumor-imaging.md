---
title: "ISPAT-3D: Spatially Varying Conditional Volumetric Network Estimation for 3D Tumor Imaging"
title_zh: ISPAT-3D：用于三维肿瘤成像的空间变化条件体积网络估计
authors: "Bhadury, S., Rao, A."
date: 2026-04-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.16.719017v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 从3D多重癌症成像数据中恢复相互作用网络
tldr: 本研究针对现有细胞交互网络分析局限于2D且忽略空间自相关的不足，提出了ISPat-3D分层贝叶斯框架。该方法利用3D多重成像数据，通过各向异性高斯过程和多研究因子分析，提取不同肿瘤强度区域的空间变化交互网络。在结直肠癌和乳腺癌数据集上的应用证明，该方法能识别出2D切片无法发现的体积空间条件交互，为理解肿瘤微环境的复杂空间组织提供了新工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的肿瘤细胞交互分析方法多局限于二维平面且忽略了空间自相关性，无法准确刻画三维空间中复杂的肿瘤微环境组织结构。
method: 提出一种名为ISPat-3D的分层贝叶斯框架，利用各向异性高斯过程建模空间相关性，并通过多研究因子分析提取特定区域的偏相关网络。
result: 在结直肠癌和乳腺癌的3D成像数据中，成功识别出随肿瘤密度变化的免疫抑制和血管重塑等关键细胞交互模块。
conclusion: ISPat-3D能够有效恢复3D组织中的体积空间条件交互，为研究肿瘤进展和免疫功能提供了比传统2D分析更深层的空间见解。
---

## 摘要
肿瘤微环境的空间组织塑造了免疫功能和疾病进展，然而现有的从多重组织图像中提取细胞类型相互作用网络的方法多在二维空间运行，且忽略了空间自相关。我们介绍了 ISPat-3D（三维信息空间感知模式），这是一个分层贝叶斯框架，可从三维多重癌症成像数据中恢复空间变化且具有区域特异性的相互作用网络。该方法将组织体积划分为肿瘤强度区域，为每种细胞类型和区域拟合各向异性高斯过程（在组织平面和轴向上具有独立的长度尺度），通过多研究因子分析分解残差，并从所得的精度矩阵中提取偏相关网络。仿真实验表明，该方法能够以高统计功效和受控的错误发现率（FDR）准确恢复共享结构和区域特异性结构。我们将 ISPat-3D 应用于两个三维数据集：结直肠癌图谱（CRC1）的三维 CyCIF 标本，以及来自三维 IMC 的 HER2 阳性导管乳腺癌（BC）标本。在 CRC1 中，区域特异性网络揭示了一个随肿瘤负荷增强的 T 细胞模块，其主导的调节关联从中等密度的 CD4+{leftrightarrow}Treg 转向最大密度的 CD8+{leftrightarrow}Treg，这与肿瘤核心的细胞毒性抑制一致。在 BC 中，共享网络显示出癌症相关成纤维细胞（CAF）与肌上皮层之间近乎完美的条件耦合，而区域特异性网络揭示了在中高负荷下的 CAF{leftrightarrow}内皮细胞共定位（与血管生成重塑一致），以及仅限于高密度区域的 B 细胞{leftrightarrow}CAF 关联（与三级淋巴结构形成一致）。在两种肿瘤中，ISPat-3D 均识别出了无法从二维切片中恢复的体积空间条件相互作用。

## Abstract
The spatial organization of the tumor microenvironment shapes immune function and disease progression, yet existing methods for cell-type interaction networks from multiplexed tissue images operate in two dimensions and ignore spatial auto-correlation. We introduce ISPat-3D (Informed Spatially Aware Patterns in 3D), a hierarchical Bayesian framework that recovers spatially varying, zone-specific interaction networks from 3D multiplexed cancer imaging data. The method partitions the tissue volume into tumor intensity zones, fits an anisotropic Gaussian process per cell type and zone with separate lengthscales for the tissue plane and axial direction, decomposes the residuals via multi-study factor analysis, and extracts partial correlation networks from the resulting precision matrices. Simulations demonstrate accurate recovery of shared and zone-specific structure with high power and controlled FDR. We apply ISPat-3D to two 3D datasets: the colorectal cancer atlas (CRC1) 3D CyCIF specimen and a HER2-positive ductal breast carcinoma (BC) specimen from a 3D IMC. In CRC1, zone-specific networks reveal a T cell module intensifying with tumor burden, with the dominant regulatory association shifting from CD4+{leftrightarrow}Treg at intermediate density to CD8+{leftrightarrow}Treg at maximal density, consistent with cytotoxic suppression at the tumor core. In BC, the shared network shows near-perfect conditional coupling between cancer-associated fibroblasts and the myoepithelial layer, while zone-specific networks reveal CAF{leftrightarrow}endothelial co-localisation at intermediate and high burden, consistent with angiogenic remodeling, and a B cell{leftrightarrow}CAF association confined to high-density zones, consistent with tertiary lymphoid structure formation. Across both tumors, ISPat-3D identifies volumetric spatial conditional interactions not recoverable from 2D sections.