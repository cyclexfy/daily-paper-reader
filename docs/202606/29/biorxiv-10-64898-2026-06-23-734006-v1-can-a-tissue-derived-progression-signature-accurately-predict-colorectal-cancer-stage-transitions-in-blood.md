---
title: Can a Tissue-derived Progression Signature Accurately Predict Colorectal Cancer Stage Transitions in Blood?
title_zh: 组织源性进展特征能否准确预测血液中结直肠癌阶段的转变？
authors: "Sarkar, P."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.23.734006v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 利用基因表达机器学习预测结直肠癌分期转变
tldr: 结直肠癌(CRC)的分子变化复杂，难以追踪。本研究开发了整合单调进展和StepMiner的机器学习框架，从组织转录组数据中识别出74个基因的进展标志，通过随机森林分类器在组织数据中表现优异，但在血液数据中效果差。经交叉过滤得到62个血相容基因，泄漏校正后在GSE164191上平均AUC达0.868。研究揭示了组织与血液转录组的差异，提供了自动化Nextflow流程和部署应用。
source: biorxiv
selection_source: fresh_fetch
motivation: CRC分子变化复杂，现有组织标志难以在血液中应用，需验证组织标志预测血液的可行性。
method: 整合单调进展和StepMiner识别开关基因，结合随机森林构建组织标志，再交叉过滤得到血相容基因。
result: 组织标志在血液数据中AUC仅0.868（泄漏校正后），基因CBX3等稳定可靠。
conclusion: 组织标志无法直接预测血液，但交叉过滤策略可提升血液预测，为液体活检提供参考。
---

## 摘要
摘要。结直肠癌（CRC）的追踪具有挑战性，因为其分子变化随着疾病进展非常复杂，给稳健生物标志物的发现带来了重大挑战。在本研究中，我们通过整合单调进展和StepMiner方法开发了一个机器学习框架。我们进行了外部验证，以识别与CRC进展相关的可重复、一致的转录组生物标志物。分析了来自公开GEO的四个疾病状态（正常结肠、腺瘤、原发性结直肠癌和转移）的基因表达数据集。首先，我们识别了具有单调表达的基因，然后使用StepMiner方法识别在阶段之间充当“开关”的基因。使用一个平衡的74基因特征结合随机森林进行机器学习分类。外部验证在基于组织的数据集中显示出强大的性能。然而，组织衍生的特征与基于血浆和血液的数据集表现不佳，突显了转录组谱之间的生物学差异。对组织衍生基因与血液表达数据集进行了交叉过滤，结果选择了62个血液兼容的基因特征。在GSE164191上进行无泄漏重新训练，平均AUC达到0.868，精确度平衡。功能富集分析显示这些基因在癌症生长中高度活跃。具体而言，基因CBX3、S100A11、PDK4、NCOR1和SOX4在验证折叠中表现出稳定可靠的性能。总体而言，我们的研究提出了一个进展感知的转录组框架用于CRC生物标志物发现，并展示了外部验证的重要性。此外，我们评估了组织衍生的特征是否能够预测血液谱。这种提出的方法可能有助于未来基于组织的诊断和针对CRC的微创液体活检策略的发展。为确保可重复性，我们提出的工作流程已自动化成为Nextflow管道。组织衍生模型作为应用程序部署，使用了Angular、ASP.NET Core和Plumber（R）。

## Abstract
Abstract. Colorectal cancer (CRC) is challenging to track because its molecular changes are very complex as the disease progresses, creating significant challenges for robust biomarker discovery. In this study, we developed a machine learning framework by integrating monotonic progression and the StepMiner approach. We conducted external validation to identify reproducible, consistent transcriptomic biomarkers associated with CRC progression. Gene expression datasets were analyzed across four disease states from publicly available GEO: normal colon, adenoma, primary colorectal cancer, and metastasis. First, we identified genes with monotonic expression, then used the StepMiner approach to identify genes that act as 'switches' between stages. A balanced 74-gene signature was used for machine-learning classification with a Random Forest. External validation showed strong performance in tissue-based datasets. However, tissue-derived signatures and plasma and blood-based datasets showed poor performance, highlighting biological differences between transcriptomic profiles. Cross-filtering between tissue-derived genes and blood expression datasets was performed, which resulted in the selection of 62 blood-compatible gene signatures. Leakage-free retraining on GSE164191 achieved a mean AUC of 0.868 with balanced precision. Functional enrichment analysis showed that these genes are highly active in cancer growth. Specifically, genes CBX3, S100A11, PDK4, NCOR1, and SOX4 demonstrated stable and reliable performance across the validation fold. Overall, our study presents a progression-aware transcriptomic framework for CRC biomarker discovery and demonstrates the importance of external validation. Additionally, we evaluate whether tissue-derived signatures can predict blood profiles. This proposed approach may help the future development of tissue-based diagnostics and minimally liquid-biopsy strategies for CRC. To ensure reproducibility, our proposed workflow was automated as a Nextflow pipeline. The tissue-derived model was deployed as an application utilizing Angular, ASP.NET Core, and Plumber (R).