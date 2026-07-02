---
title: In Vitro Detection of Breast Cancer Cell Types Using Machine Learning-Assisted Spectral Fingerprinting of SWCNTs
title_zh: 利用机器学习辅助的SWCNTs光谱指纹体外检测乳腺癌细胞类型
authors: "Rahmani, M., Van Gorden, K., Peyton, S. R., Roxbury, D."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.30.735651v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 利用机器学习与光谱指纹检测乳腺癌细胞
tldr: "乳腺癌早期检测依赖昂贵方法，缺乏活细胞实时监测手段。本研究利用DNA功能化单壁碳纳米管（SWCNT）近红外荧光光谱指纹结合机器学习，对五种细胞系共3000个细胞进行检测。通过提取光谱特征训练集成模型，实现了98%的癌症检测准确率和95%的亚型分类准确率。该平台为纳米材料生物传感实时监测癌症细胞状态奠定了基础。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有乳腺癌检测方法依赖病理切片，无法实时监测活细胞动态，亟需低成本、高灵敏的活细胞检测技术。
method: 将DNA-SWCNT与乳腺癌细胞系共培养，采集600个细胞/系的近红外荧光光谱，提取峰值强度、中心波长等特征，训练集成学习模型分类。
result: "模型对乳腺癌检测准确率98%，亚型分类准确率95%；MDA-MB-468细胞摄取SWCNT最高，MCF-10A细胞聚集更明显。"
conclusion: SWCNT荧光指纹可捕获细胞系特异性光学信号，为实时监测癌症细胞状态提供了无标记、非侵入式新方法。
---

## 摘要
目前乳腺癌的早期检测依赖于昂贵的乳腺X线摄影，随后是使用活检、固定和免疫组化染色组织的病理学。活细胞检测方法作为辅助诊断和研究工具可能非常有益，可以更好地理解和解决乳腺癌细胞的动态性质及其对治疗的实时反应。在这里，我们提出了一种单壁碳纳米管（SWCNT）近红外荧光光谱指纹方法，结合机器学习，精确检测活培养中乳腺癌细胞的异质性。我们将DNA功能化的SWCNT引入MCF-10A（非致瘤性健康对照）和涵盖已知外在疾病亚型的癌细胞系：MCF-7（管腔A）、HCC1954（HER2+）、MDA-MB-231和MDA-MB-468（两者均为三阴性）。每种类型600个单个细胞中DNA-SWCNT的近红外荧光光谱显示出发射峰强度、中心波长和峰强度比的显著差异，这归因于细胞摄取和生物分子相互作用的差异。这些光谱变化可能源于复杂的SWCNT细胞相互作用指纹，包括氧化还原介导的局部纳米管环境调节，而不是单一生物标志物响应。提取的光谱特征用于训练集成机器学习模型。该模型在乳腺癌检测中达到98%的分类准确率，在乳腺癌细胞亚型分类中达到95%的分类准确率。此外，拉曼显微镜进一步表明，MDA-MB-468细胞表现出最高的SWCNT摄取，而MCF-10A细胞表现出更大的SWCNT聚集，这与它们较低的宽带近红外荧光强度一致。这些结果表明，SWCNT近红外荧光指纹可以捕获细胞系特异性光学特征。该平台为旨在实时监测癌症相关细胞状态的纳米材料生物传感策略提供了基础。

## Abstract
The early detection of breast cancer currently relies on expensive mammography, followed by pathology that uses biopsied, fixed, and immunohistochemically stained tissues. A live-cell detection approach could be highly beneficial as a supportive diagnostic and research tool to better understand and resolve the dynamic nature of breast cancer cells and their response to treatment in real time. Here, we present a single-walled carbon nanotube (SWCNT) near-infrared fluorescence spectral fingerprinting approach combined with machine learning to precisely detect the heterogeneity of breast cancer cells in live culture. We introduced DNA-functionalized SWCNTs to MCF-10A (a non-tumorigenic healthy control) and cancer cell lines spanning known extrinsic disease subtypes: MCF-7 (luminal A), HCC1954 (HER2+), MDA-MB-231, and MDA-MB-468 (both triple-negative). The NIR fluorescence spectra of DNA-SWCNTs across 600 individual cells within each type showed significant differences in emission peak intensities, center wavelengths, and peak intensity ratios, attributable to variations in cellular uptake and biomolecular interactions. These spectral changes likely arise from complex SWCNT cellular interaction fingerprint that includes redox-mediated modulation of the local nanotube environment, rather than from a single biomarker response. The extracted spectral features were used to train an ensemble machine learning model. The model achieved 98% classification accuracy for breast cancer detection and 95% classification accuracy for breast cancer cell subtyping. Moreover, Raman microscopy further showed that MDA-MB-468 cells exhibited the highest SWCNT uptake, whereas MCF-10A cells showed greater SWCNT aggregation, consistent with their lower broadband NIR fluorescence intensity. These results demonstrate that SWCNT NIR fluorescence fingerprints can capture cell line-specific optical signatures. This platform provides a foundation for nanomaterial-enabled biosensing strategies aimed at real-time monitoring of cancer-associated cellular states.