---
title: Interpretable morphology mapping of peripheral blood leukocytes using annotation-efficient artificial intelligence
title_zh: 利用注释高效的人工智能进行外周血白细胞的可解释形态学映射
authors: "Liu, Z., Castillo, S. P., Han, X., Sun, X., Hu, Z., Yuan, Y."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.725537v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 注解高效的白细胞形态AI用于血液恶性肿瘤分析
tldr: "外周血涂片检查是血液肿瘤诊断的重要环节，但人工阅片耗时长、主观性强。现有AI辅助方法扩展性差，且需要大量标注数据和缺乏可解释性。本研究提出一种标注高效的可解释AI框架，通过无标签表示学习构建细胞形态嵌入空间，再使用主动学习策略进行少量标注微调。在涵盖癌症患者和公开数据的2.3万张图像上，模型实现9类白细胞分类macro-F1达0.96，仅用13.3%标注即达最佳性能。模型还可分类11种形态属性，并利用显著性图和嵌入可视化提供可解释预测。最终开发了交互式网页应用HemoSight，支持临床集成，提升了阅片效率和可信度。"
source: biorxiv
selection_source: fresh_fetch
motivation: 解决外周血涂片AI辅助诊断中标注成本高和可解释性不足的问题。
method: 两阶段框架：无标签表示学习构建形态嵌入空间，再通过主动学习微调分类任务，并集成可解释性可视化。
result: "9类白细胞分类macro-F1达0.96，仅需13.3%标注即达峰值；11种形态属性平均F1达85.8%。"
conclusion: 实现标注高效、可解释的白细胞形态分析，为AI辅助血液病理学工作流提供可行方案。
---

## 摘要
背景：外周血涂片（PBS）审查是劳动密集型的、主观的，并且对于血液恶性肿瘤中罕见或形态异质性细胞类型具有挑战性。人工智能（AI）提供了一种可扩展的替代方案，但更广泛的临床转化受到注释负担和可解释性有限的制约。

方法：我们开发了一个可解释的、注释高效的人工智能框架，通过两阶段过程学习白细胞形态：无标签表示学习构建形态嵌入空间，随后进行监督微调以进行细胞类型和形态属性分类。该模型在MD安德森癌症中心癌症患者的5,952张PBS图像（包括原始细胞）以及来自公共来源的17,092张图像上进行训练和评估。评估了主动学习策略以提高标签效率，并通过显著性和嵌入可视化检查可解释性。开发了一个交互式网络应用程序HemoSight，以支持临床审查。

发现：该框架在内部测试集上的9类白细胞分类中实现了0·96的宏F1分数，在预留患者队列中实现了0·83。主动学习大幅减少了注释需求，仅使用13·3%的可用标签即达到峰值性能，并在9种细胞类型中的8种上显著提高了学习效率。该模型泛化到对11种白细胞形态属性进行分类，平均F1分数为85·8%，并揭示了结构化的形态景观。显著性图、嵌入可视化和HemoSight应用程序能够透明地检查模型预测的形态学，支持对模型行为的信心以及在临床整合中的可行性。

解释：我们的框架实现了可扩展、注释高效且可解释的白细胞形态学建模，支持将AI辅助的PBS审查整合到血液病理学工作流程中。

资助：德克萨斯大学MD安德森癌症中心种子基金。

研究背景：
本研究之前的证据：外周血涂片审查对于诊断和监测血液恶性肿瘤至关重要，但手动病例审查耗时且变异性大，特别是对于罕见或异常的白细胞类型。自动血液分析仪广泛用于标记异常细胞；然而，它们提供的形态学信息有限，并且经常需要频繁的手动校正，尤其是在癌症环境中，疾病和治疗会改变细胞外观。以前的白细胞分类人工智能方法显示了前景，但大多数依赖完全监督学习，需要大量的专家注释，关注有限的细胞类型，并且经常排除诊断重要的罕见细胞，如原始细胞。可解释性没有得到一致解决，很少有研究提供工具让临床医生在常规工作流程中检查和解释模型输出。

本研究的附加价值：本研究引入了一个注释高效的框架，该框架在大量外周血涂片图像上训练，包括经过血液病理学家验证的含有罕见细胞类型（如原始细胞）的癌症患者样本。该框架从未标记的图像中学习白细胞形态，并通过最少的专家标记适应多个分类任务。性能在内部测试集和预留患者队列上进行评估，以提供对泛化能力的现实估计。迭代的、不确定性引导的注释显著减少了标签需求，同时提高了大多数白细胞类别的学习效率。除了细胞类型分类，该框架还扩展到11个临床相关的形态学属性，并揭示了结构化的形态景观。这些能力被整合到一个网络应用程序HemoSight中，实现了血液病理学工作流程中的实时推理和预测的透明形态学检查。

所有可用证据的意义：推进血液学的人工智能需要减少专家标签需求、提供可解释输出并在临床多样的患者样本中可靠执行的方法。本研究表明，从大量无标签数据中学习结合迭代专家注释可以支持白细胞形态学的可扩展和灵活建模，用于分类任务。集成定量预测和交互式可视化支持将人工智能作为诊断性外周血涂片审查的辅助工具，具有提高效率、一致性和审查员信心的潜力。

## Abstract
BackgroundPeripheral blood smears (PBS) review is labor-intensive, subjective, and challenging for rare or morphologically heterogeneous cell types in hematologic malignancies. Artificial intelligence (AI) offers a scalable alternative, but broader clinical translation is constrained by annotation burden and limited interpretability.

MethodsWe developed an interpretable, annotation-efficient AI framework that learns leukocyte morphology through a two-stage process: label-free representation learning to construct a morphological embedding space, followed by supervised fine-tuning for cell type and morphological attribute classification. The model was trained and evaluated on 5,952 PBS images from cancer patients at MD Anderson Cancer Center, including blast cells, and 17,092 images from public sources. Active learning strategies were assessed to improve label efficiency, and interpretability was examined using saliency and embedding visualization. An interactive web application, HemoSight, was developed to support clinical review.

FindingsThe framework achieved a macro-F1 score of 0{middle dot}96 for 9-way leukocyte classification on the internal test split and 0{middle dot}83 on the held-out patient cohort. Active learning substantially reduced annotation requirements, reaching peak performance with only 13{middle dot}3% of available labels and significantly improving learning efficiency across 8 of 9 cell types. The model generalized to classifying 11 leukocyte morphological attributes with a mean F1 score of 85{middle dot}8% and revealed structured morphological landscapes. Saliency maps, embedding visualizations, and the HemoSight application enabled transparent morphological inspection of model predictions, supporting confidence in model behavior and feasibility for clinical integration.

InterpretationOur framework enables scalable, annotation-efficient, and interpretable modeling of leukocyte morphology, supporting the integration of AI-assisted PBS review for hematopathology workflows.

FundingSeed funding from The University of Texas MD Anderson Cancer Center.

Research in ContextO_ST_ABSEvidence before this studyC_ST_ABSPeripheral blood smear review is essential for diagnosing and monitoring hematologic malignancies, but manual case review is time-consuming and variable, particularly for rare or abnormal leukocyte types. Automated hematology analyzers are widely used to flag abnormal cells; however, they provide limited morphological insight and often require frequent manual correction, especially in cancer settings where disease and treatment alter cell appearance. Previous artificial intelligence approaches for leukocyte classification have shown promise, but most rely on fully supervised learning, require extensive expert annotation, focus on a limited set of cell types, and frequently exclude diagnostically important rare cells such as blasts. Interpretability is inconsistently addressed, and few studies provide tools that allow clinicians to inspect and interpret model outputs within routine workflows.

Added value of this studyThis study introduces an annotation-efficient framework trained on a large collection of peripheral blood smear images, including cancer patient samples with hematopathologist-verified rare cell types such as blasts. The framework learns leukocyte morphology from unlabeled images and adapts to multiple classification tasks with minimal expert labeling. Performance is evaluated on both internal test splits and a held-out patient cohort to provide a realistic estimate of generalization. Iterative, uncertainty-guided annotation substantially reduces labeling requirements while improving learning efficiency across most leukocyte classes. Beyond cell-type classification, the framework is extended to 11 clinically relevant morphological attributes and reveals a structured morphological landscape. These capabilities are integrated into a web application, HemoSight, enabling real-time inference and transparent morphological inspection of predictions within hematopathology workflows.

Implications of all the available evidenceAdvancing artificial intelligence for hematology requires methods that reduce expert labeling demands, provide interpretable outputs, and perform reliably across clinically diverse patient samples. This study shows that learning from largely unlabeled data combined with iterative expert annotation can support scalable and flexible modeling of leukocyte morphology for classification tasks. Integrating quantitative predictions and interactive visualization supports the use of artificial intelligence as an assistive tool for diagnostic peripheral blood smear review, with potential to improve efficiency, consistency, and reviewer confidence.