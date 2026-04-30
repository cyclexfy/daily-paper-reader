---
title: Pan-cancer virtual spatial transcriptomics from routine histology with Phoenix
title_zh: Phoenix：基于常规组织学的泛癌虚拟空间转录组学
authors: "Tran, M., Gindra, R. H., Putze, P., Senbai, K., Palla, G., Kos, T., Falcomata, C., Wang, C., Guo, R., Boxberg, M., Berclaz, L. M., Lindner, L. H., Bergmayr, L., Knoesel, T., Jurmeister, P., Klauschen, F., Homicsko, K., Gottardo, R., Eckstein, M., Matek, C., Mock, A., Theis, F. J., Saur, D., Peng, T."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.25.720812v1.full.pdf"
tags: ["query:cpath"]
score: 8.5
evidence: 从组织学图像预测泛癌分析中的基因表达
tldr: 空间转录组学受限于高昂成本和低通量，难以在大规模临床研究中应用。本文提出Phoenix，一种基于潜在流匹配的生成模型，能从常规组织学切片中高精度推断泛癌症单细胞空间基因表达。该模型在头颈癌、乳腺癌、卵巢癌及肉瘤等多种癌症中表现出极强的泛化能力，成功识别了新的空间生物标志物，并能跨物种预测，为研究组织结构和治疗反应提供了可扩展的虚拟空间转录组学框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的空间转录组技术成本高、速度慢且计算预测方法在未知队列和疾病中泛化性差。
method: 开发了名为Phoenix的潜在流匹配生成模型，通过常规组织学图像推断泛癌症的空间单细胞基因表达。
result: Phoenix在多种癌症中准确预测了基因表达和免疫重塑，并识别出跨癌种有效的空间生物标志物。
conclusion: Phoenix建立了一个从常规病理切片获取虚拟空间转录组信息的可靠框架，显著提升了疾病机制研究的效率。
---

## 摘要
空间转录组学将基因表达与组织架构联系起来，为细胞组织提供了机制性的视角。然而，现有数据集涵盖的捐赠者较少，且忽略了人类疾病的复杂性。实验成本依然高昂，且大规模分析对于群体水平的研究而言速度过慢。迫切需要准确的计算方法。然而，从标准组织学预测基因表达仍是一个开放性问题，因为现有方法在未见过的队列和疾病中迁移效果较差。在这里，我们提出了 Phoenix，这是一种潜流匹配（latent flow matching）生成模型，能够高精度地推断泛癌空间分辨率单细胞基因表达。Phoenix 能够进行计算机模拟（in silico）治疗反应分析：应用于 763 名头颈癌患者时，它识别出三种新的空间生物标志物，我们已在两种癌症（乳腺癌，n = 84；卵巢癌，n = 157）和治疗方案（铂类、曲妥珠单抗）中对其进行了验证。Phoenix 的泛化能力超出了癌（carcinomas）：在一个大型肉瘤队列（802 个组织微阵列核心）中，它准确预测了留出样本中的细胞类型特异性特征，并捕捉到了化疗诱导的免疫重塑。Phoenix 还可以跨物种扩展：在小鼠模型中，它在计算机模拟中准确预测了胰腺癌谱系标志物和突变型 mKrasG12D 等位基因的表达。总之，Phoenix 将基于常规组织学的虚拟空间转录组学确立为一个可扩展的框架，用于研究组织结构、治疗反应和疾病机制。

## Abstract
Spatial transcriptomics links gene expression to tissue architecture, providing a mechanistic view of cellular organization. Yet existing datasets cover few donors and miss the complexity of human disease. Experimental costs remain prohibitive, and large-scale profiling is impractically slow for population-level studies. Accurate computational methods are urgently needed. Predicting gene expression from standard histology, however, remains an open problem, as current approaches transfer poorly to unseen cohorts and diseases. Here, we present Phoenix, a latent flow matching generative model that infers pan-cancer spatially resolved single-cell gene expression with high accuracy. Phoenix analyzes treatment response in silico: Applied to 763 head and neck cancer patients, it identified three new spatial biomarkers that we validated across two cancers (breast cancer, n = 84; ovarian cancer, n = 157) and treatment regimens (platinum, trastuzumab). Phoenix generalizes beyond carcinomas: In a large sarcoma cohort (802 tissue microarray cores), it accurately predicted cell-type-specific signatures in held-out samples and captured chemotherapy-induced immune remodeling. Phoenix also extends across species: In a mouse model, it accurately predicted the expression of pancreatic cancer lineage markers and the mutant mKrasG12D allele in silico. Together, Phoenix establishes virtual spatial transcriptomics from routine histology as a scalable framework for studying tissue organization, therapeutic response, and disease mechanisms.