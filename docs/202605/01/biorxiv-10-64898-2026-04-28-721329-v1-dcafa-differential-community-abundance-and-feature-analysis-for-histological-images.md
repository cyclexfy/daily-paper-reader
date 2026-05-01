---
title: "DCAFA: Differential Community Abundance and Feature Analysis for Histological Images"
title_zh: DCAFA：组织学图像的差异化群落丰度与特征分析
authors: "Wright, G., Keller, P., Muter, J., Brosens, J., Tejpar, S., Minhas, F."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721329v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 组织学图像和组织结构的计算分析
tldr: 本研究提出DCAFA框架，旨在解决组织学图像分析中孤立特征分析的局限性。该框架通过将局部结构（如细胞、组织块）聚类为潜在群落，利用广义线性模型和混合效应模型，同时进行群落丰度差异分析和特征归因分析。DCAFA能够识别与临床结果相关的组织成分变化及特定背景下的特征关联，为生物医学影像数据提供了一种可解释的统计分析工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的组织学图像分析往往关注孤立特征，忽略了局部结构组成变化中蕴含的重要临床信号。
method: 提出一个基于回归的框架，将实例分组为潜在群落，并结合广义线性模型进行群落丰度分析和特征归因分析。
result: 在子宫内膜病理、空间转录组学和结直肠癌等多种生物医学场景中，成功识别出传统方法无法捕捉的可解释成分偏移和上下文特征关联。
conclusion: DCAFA统一了差异丰度测试与特征归因，为将组织组成与临床或分子结果联系起来提供了一个实用且可解释的开源工具箱。
---

## 摘要
组织学图像由细胞、腺体或组织斑块等多种局部结构组成，其组织方式和相对丰度反映了潜在的生物学过程。虽然大多数计算方法侧重于分析单个特征，但许多临床相关的信号源于这些结构组成的改变，而非孤立的测量值。这促使我们需要显式地建模相似实例组在样本间的变化及其与结果的关系。我们提出了 DCAFA（差异化群落丰度与特征归因分析），这是一个基于回归的框架，用于从组成和特征两个层面分析分层生物医学数据。DCAFA 将实例分组为代表重复出现的形态或表型模式的潜在群落，然后进行两项互补分析：(i) 群落组成分析，识别在不同结果中富集或减少的群体；(ii) 特征归因分析，量化实例级特征如何直接或在特定群落内与结果相关联。两者均使用广义线性模型和混合效应模型，能够通过效应量、置信区间和错误发现率控制进行协变量调整和推断。我们在多种生物医学场景中展示了 DCAFA 的实用性，包括子宫内膜组织病理学、空间转录组学、多重免疫荧光成像以及结直肠癌中预定义细胞类型的分析。这些示例识别出了传统基于特征的方法无法捕捉到的、具有可解释性的组成转变和特定背景下的特征关联。通过将差异丰度测试和特征归因统一在单个统计框架内，DCAFA 作为一个开源工具箱，为将组织组成与生物医学成像数据中的临床或分子结果联系起来提供了一种实用且具有可解释性的手段。代码见：https://github.com/wgrgwrght/DCAFA

## Abstract
Histological images are composed of diverse local structures such as cells, glands, or tissue patches, whose organisation and relative abundance reflect underlying biological processes. While most computational approaches focus on analysing individual features, many clinically relevant signals arise from changes in the composition of these structures rather than isolated measurements. This motivates the need for explicitly modelling how groups of similar instances vary across samples and relate to outcomes. We present DCAFA (Differential Community Abundance and Feature Attribution Analysis), a regression-based framework for analysing hierarchical biomedical data through both compositional and feature-level perspectives. DCAFA groups instances into latent communities representing recurring morphological or phenotypic patterns, and then performs two complementary analyses: (i) community composition analysis, which identifies groups that are enriched or depleted across outcomes, and (ii) feature attribution analysis, which quantifies how instance-level features relate to outcomes directly or within specific communities. Both use generalised linear and mixed-effects models, enabling covariate adjustment and inference through effect sizes, confidence intervals, and false discovery rate control. We demonstrate the utility of DCAFA across multiple biomedical settings, including endometrial histopathology, spatial transcriptomics, multiplex immunofluorescence imaging, and predefined cell-type analyses in colorectal cancer. These examples identify interpretable compositional shifts and context-specific feature associations that are not captured by conventional feature-based approaches. By unifying differential abundance testing and feature attribution within a single statistical framework, DCAFA serves as an openly available toolbox that provides a practical and interpretable means of linking tissue composition with clinical or molecular outcomes in biomedical imaging data. Code available at: https://github.com/wgrgwrght/DCAFA