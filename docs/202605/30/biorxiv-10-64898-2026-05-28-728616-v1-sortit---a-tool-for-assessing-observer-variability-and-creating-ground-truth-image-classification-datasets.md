---
title: SortIT - A Tool For Assessing Observer Variability And Creating Ground Truth Image Classification Datasets
title_zh: SortIT - 一种评估观察者变异性并创建真实图像分类数据集的工具
authors: "Uegami, W., Bisson, T., Okoshi, E. N., Costa da Silva, F. G., Jiragawasan, C., Zerbe, N., Bychkov, A., Fukuoka, J."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728616v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于从全切片图像创建真实标注集的工具
tldr: 病理评估中观察者变异性影响诊断可靠性，AI标准化需要高质量标注。SortIT是一个开源Web应用，支持多标注者独立标注图像块，并导出数据用于变异分析和共识数据集生成。通过有丝分裂分割、前列腺癌分级评估、肉芽肿分类三个用例验证了其有效性。其易部署性和开放性有助于社区采用，为开发准确、泛化的诊断AI工具提供关键支撑。
source: biorxiv
selection_source: fresh_fetch
motivation: 病理诊断中观察者变异显著，现有标注工具缺乏系统性共识标注与变异评估功能，亟需简易开源方案。
method: 开发SortIT，基于Web的多标注者独立标注平台，支持权限控制、数据导出及观察者变异统计与共识构建。
result: 在有丝分裂分割、前列腺癌分级、肉芽肿分类三个任务中成功生成共识数据集并量化变异，验证了工具实用性。
conclusion: SortIT以易部署、开源特性填补了病理标注工具空白，为构建高质量金标准数据集和评估观察者变异提供了标准化手段。
---

## 摘要
观察者间变异性是病理评估中公认的挑战，影响诊断可靠性和疾病理解。由于评估的主观性，这种变异性存在于许多亚专业领域。应用于全切片图像的人工智能（AI）有潜力标准化程序并减少病理学中的变异性，但转向这些技术并不能保证改进。建立具有共识注释的可靠真实数据集对于开发稳健的AI解决方案至关重要。我们介绍SortIT，一个开源web应用，促进系统创建和评估真实图像块注释。SortIT使多个注释者能够独立标记图像块，具有灵活的用户权限控制。注释数据可以导出用于观察者变异的统计分析，以及从共识图像块创建真实数据集。我们概述了使用SortIT的几个用例协议：（1）肿瘤区域的核分裂分割，（2）通过与专家共识比较评估前列腺癌分级的AI解决方案，（3）通过注释判别性图像块特征进行肉芽肿分类。SortIT的主要优势在于其易于部署，使其对广泛用户可访问和可用。总体而言，SortIT提供了一个有价值的工具来建立高质量的真实数据集并全面评估观察者变异性。使用系统注释方法对真实质量进行批判性评估对于开发准确且可推广的诊断AI工具至关重要。其开源性质促进了社区采用和进一步发展。

## Abstract
Interobserver variability in pathological assessments is a well-recognized challenge that impacts diagnostic reliability and disease understanding. This variability exists across many subspecialties due to the subjective nature of evaluations. Artificial intelligence (AI) applied to whole slide images has potential to standardize procedures and reduce variability in pathology, but transitioning to these technologies does not guarantee improvement. Establishing reliable ground truth datasets with consensus annotations is crucial for developing robust AI solutions. We introduce SortIT, an open-source web application that facilitates systematic creation and evaluation of ground truth image tile annotations. SortIT enables multiple annotators to independently label tiles, with flexible user permission controls. Annotated data can be exported for statistical analysis of observer variation and for creating ground truth datasets from consensus tiles. We outline protocols using SortIT for several use cases: (1) mitosis segmentation in tumor regions, (2) evaluating AI solutions for prostate cancer grading by comparing to expert consensus, and (3) granuloma classification by annotating discriminative tile-level features. Key strengths of SortIT lies in its ease of deployment, making it accessible and usable for a wide range of users. Overall, SortIT provides a valuable tool to establish high-quality ground truth datasets and comprehensively assess observer variability. Critical evaluation of ground truth quality using systematic annotation methodologies is crucial for developing accurate and generalizable diagnostic AI tools. Its open-source nature facilitates community adoption and further development.