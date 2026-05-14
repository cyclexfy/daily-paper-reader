---
title: "MurineCyto-Det: A High-Resolution Murine BALF Cytology Dataset for Leukocyte Segmentation and Detection"
title_zh: MurineCyto-Det：用于白细胞分割与检测的高分辨率小鼠支气管肺泡灌洗液（BALF）细胞学数据集
authors: "Le, T. X., Tran, L.-A. T., Farabi, D. A., Wang, S., Phan, A. T. Q., Cormier, S. A., Taada, A., McGrew, D., Du, Y., Vu, L. D."
date: 2026-05-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.08.723893v1.full.pdf"
tags: ["query:cpath"]
score: 6.5
evidence: 用于白细胞分割和检测的细胞学数据集
tldr: "本研究针对临床前呼吸道研究中缺乏公开标注的小鼠支气管肺泡灌洗液（BALF）细胞图像数据集的问题，推出了MurineCyto-Det数据集。该数据集包含333张高分辨率图像，涵盖5类细胞共14,551个标注实例，支持细胞分割与检测任务。通过对主流模型进行基准测试，揭示了类别不平衡和复杂形态带来的挑战，为自动化细胞分析提供了标准化资源。"
source: biorxiv
selection_source: fresh_fetch
motivation: 临床前呼吸道研究急需自动化分析小鼠BALF细胞，但目前缺乏公开且高质量的标注数据集。
method: "构建了一个包含14,551个标注实例的高分辨率数据集，并利用代表性分割和检测模型建立了基准。"
result: 实验结果验证了数据集的实用性，并指出了类别不平衡、小目标及不规则形态等实际分析挑战。
conclusion: MurineCyto-Det为小鼠BALF细胞分析提供了标准化的开发与评估资源，有助于推动该领域的自动化研究。
---

## 摘要
小鼠支气管肺泡灌洗液（BALF）细胞学的自动分析对于临床前呼吸系统研究具有重要意义，但由于缺乏公开可用且标注良好的小鼠 BALF 图像数据集，该领域的研究进展受到了限制。我们提出了 MurineCyto-Det，这是一个高分辨率的小鼠 BALF 细胞学数据集，包含 333 张尺寸为 1024x1024 像素的图像块，涵盖五个细胞学类别，并提供了像素级分割掩码和一一对应的边界框标注。该数据集包含 14,551 个标注的细胞实例，支持两项互补的分析任务：面向形态学的细胞分割和目标级细胞检测。为了建立可重复的基准基线，我们评估了具有代表性的分割和检测模型。结果证明了 MurineCyto-Det 的实际应用价值，同时也突显了由类别不平衡、目标尺寸微小、细胞形态不规则以及模糊的碎片状结构所带来的现实挑战。MurineCyto-Det 为开发、评估和比较小鼠 BALF 细胞学分析的自动化方法提供了一个标准化的资源。该数据集可在 https://doi.org/10.5281/zenodo.17608677 公开获取。

## Abstract
Automated analysis of murine bronchoalveolar lavage fluid (BALF) cytology is important for preclinical respiratory research, yet progress has been limited by the lack of publicly available, well-annotated mouse BALF image datasets. We present MurineCyto-Det, a high-resolution murine BALF cytology dataset comprising 333 image tiles of size 1024x1024 pixels, annotated across five cytological categories with both pixel-level segmentation masks and one-to-one matched bounding boxes. The dataset contains 14,551 annotated cell instances and supports two complementary analysis tasks: morphology-oriented cell segmentation and object-level cell detection. To establish reproducible benchmark baselines, we evaluated representative segmentation and detection models. The results demonstrate the practical utility of MurineCyto-Det while highlighting realistic challenges arising from class imbalance, small object size, irregular cell morphology, and ambiguous debris-like structures. MurineCyto-Det provides a standardized resource for developing, evaluating, and comparing automated methods for murine BALF cytology analysis. The dataset is publicly available at https://doi.org/10.5281/zenodo.17608677.