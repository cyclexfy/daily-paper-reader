---
title: "Mapping Tumor-Microenvironment dependencies with TMEformer: A spatial foundation framework enabling in silico perturbation"
title_zh: 利用TMEformer映射肿瘤-微环境依赖关系：一个实现原位扰动的空间基础框架
authors: "Chen, S., Zhu, G., Yang, L., Wei, X., Li, S., Liu, P., Chen, Q., Zhang, Z., Liu, D., Tang, Y., Xu, G., Zhou, M., Luo, J., Huang, L., Chen, B., Ou, S., Jiang, J."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.17.725770v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 用于癌症的空间基础框架
tldr: 尽管空间上下文驱动肿瘤进展，但现有虚拟扰动模型普遍忽视其作用。TMEformer是一个肿瘤微环境感知的深度学习框架，利用高分辨率空间转录组学显式编码空间架构，联合建模肿瘤细胞内在程序与局部微环境信号。在多种肿瘤空间转录组队列中，TMEformer准确捕获谱系可塑性和治疗耐药性等关键转变，其性能优于基于大规模语料库预训练的模型。系统性扰动分析优先识别了已知及新型驱动疾病进展的调控因子，同时TMEformer生成的嵌入显著改善了肿瘤细胞空间分层，更贴合病理结构。该框架为将肿瘤视为空间耦合、可扰动生态系统建立了通用范式。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-17-725770-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1528, \"height\": 1535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-17-725770-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1538, \"height\": 2212, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-17-725770-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1532, \"height\": 1813, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-17-725770-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1498, \"height\": 2059, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-17-725770-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1518, \"height\": 1991, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-17-725770-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1529, \"height\": 2126, \"label\": \"Figure\"}]"
motivation: 现有虚拟扰动模型忽视空间上下文，TMEformer通过显式建模空间架构捕捉肿瘤-微环境依赖关系。
method: TMEformer基于高分辨率空间转录组数据，联合建模肿瘤内在程序与局部微环境信号，实现可解释的虚拟扰动。
result: 在多种肿瘤数据中优于大规模预训练模型，恢复已知调控因子并发现新候选因子，嵌入改善细胞空间分层。
conclusion: 建立将肿瘤视为空间耦合、可扰动生态系统的通用框架，助力理解肿瘤进展和耐药性。
---

## 摘要
尽管空间背景在驱动肿瘤进展中起基础性作用，但当前大多数用于虚拟扰动的计算模型在很大程度上忽视了其重要性。在此，我们提出TMEformer，一个肿瘤微环境感知的深度学习框架，它利用高分辨率空间转录组学，通过显式整合空间结构来联合建模肿瘤细胞内在程序与局部微环境信号。经过多种肿瘤空间转录组学数据集的验证，TMEformer能够实现捕获局部细胞生态系统内功能依赖性的虚拟扰动。尽管仅在癌症特异性空间数据集上训练，TMEformer在捕捉关键肿瘤转变方面优于在大规模语料库上预训练的基线模型，这些转变包括谱系可塑性和治疗抵抗性的出现。系统性扰动分析优先考虑了驱动疾病进展的肿瘤内在转录因子和TME来源的配体，恢复了已知的调控因子并揭示了新的候选因子。此外，TME衍生的嵌入改善了肿瘤细胞的空间分层，并与病理结构更加一致。总之，TMEformer建立了一个将肿瘤建模为空间耦合、可扰动生态系统的通用框架。

## Abstract
Despite the fundamental role of spatial context in driving tumor progression, most current computational models for virtual perturbation have largely overlooked its importance. Here, we introduce TMEformer, a tumor microenvironment-aware deep learning framework that leverages high-resolution spatial transcriptomics to jointly model intrinsic tumor cell programs and local microenvironmental signals by explicitly incorporating spatial architecture. Validated across diverse tumor spatial transcriptomic cohorts, TMEformer enables virtual perturbations that capture functional dependencies within local cellular ecosystems. Despite being trained on cancer-specific spatial datasets, TMEformer outperforms baseline models pretrained on large-scale corpora in capturing key tumor transitions, including lineage plasticity and the emergence of therapy resistance. Systematic perturbation analyses prioritize tumor-intrinsic transcription factors and TME-derived ligands that drive disease progression, recovering established regulators and revealing novel candidates. Furthermore, TME-derived embeddings improve the spatial stratification of tumor cells and align more closely with pathological architecture. Together, TMEformer establishes a general framework for modeling tumors as spatially coupled, perturbable ecosystems.