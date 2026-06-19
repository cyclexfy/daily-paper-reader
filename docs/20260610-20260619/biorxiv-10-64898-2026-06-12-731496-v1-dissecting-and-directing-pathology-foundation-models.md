---
title: Dissecting and directing pathology foundation models
title_zh: 剖析与引导病理学基础模型
authors: "Kim, C., Kaczmarzyk, J., Savant, D., Zhao, Z., Koo, P., Lee, S.-I."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731496v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 病理基础模型的可解释性与控制
tldr: 病理学基础模型（FM）的嵌入不透明，限制了临床可信度和科学发现。PICASSO框架通过稀疏自编码器将FM嵌入分解为可解释的视觉概念，在1.2亿组织块（32种癌症）上训练，构建首个泛癌组织形态学概念图谱。该图谱支持模型审计、新标志物发现（如肺腺癌EGFR突变的hobnailing形态）、技术伪影抑制及反事实生成。PICASSO将病理学FM转变为可解释、可控的平台，推动机制研究和临床转化。
source: biorxiv
selection_source: fresh_fetch
motivation: 病理学基础模型嵌入缺乏可解释性，导致临床信任不足，也限制了生物学新见解的发掘。
method: PICASSO使用稀疏自编码器将FM嵌入分解为可解释概念，在超1.2亿组织块（32癌种）上训练得到泛癌概念图谱。
result: 实现模型审计、发现hobnailing上皮为EGFR突变新标志、关联空间转录组、抑制伪影、生成反事实嵌入以探索治疗影响。
conclusion: PICASSO为将病理学FM转化为可解释、可控的平台提供通用框架，促进临床转化与生物发现。
---

## 摘要
基础模型在数字病理学中至关重要，它能够将组织学图像编码为密集嵌入，从而促进诊断分类、分子改变预测和临床结局建模。然而，这些嵌入的不透明性使得基于基础模型的系统成为“黑箱”，限制了其在临床转化中的可信度以及在科学发现中的实用性。本文介绍了PICASSO（通过稀疏字典学习构建的病理学图像概念图谱），这是一个让病理学基础模型变得可解释和可控制的框架。PICASSO使用稀疏自编码器将基础模型嵌入分解为人类可解释的视觉概念。该框架在超过1.2亿个组织切片（涵盖32种癌症类型）上进行训练，生成了首个泛癌组织形态学概念图谱。我们证明，PICASSO通过揭示学习表征中的可解释结构并支持概念级干预，实现了基础模型嵌入的多样化下游应用。它通过揭示驱动预测的形态学特征，使得对临床模型行为进行审计成为可能。除了透明度和验证之外，PICASSO还能发现新的生物学见解；例如，它识别出“钉突”上皮形态学作为肺腺癌EGFR突变的一个此前未知的生物标志物。通过将PICASSO推导出的概念与空间转录组学联系起来，我们揭示了形态学模式与基因表达程序之间的关联。此外，PICASSO允许抑制与技术伪影相关的概念，从而减少模型对虚假信号的依赖。最后，PICASSO能够对学习到的概念进行受控操作，生成反事实嵌入以用于探索性治疗分析，例如调节肿瘤浸润淋巴细胞密度以评估其对预测生存结局的影响。总之，PICASSO提供了一个原则性框架，将病理学基础模型转变为用于机制洞察和发现的平台。

## Abstract
Foundation models (FMs) are central to digital pathology, encoding histology images into dense embeddings for facilitating diagnostic classification, molecular alteration prediction, and clinical outcome modeling. However, the opacity of these embeddings renders FM-based systems "black boxes," limiting their trustworthiness for clinical translation and utility for scientific discovery. Here, we introduce PICASSO (Pathology Image Concept Atlas built via SparSe dictiOnary learning), a framework that makes pathology FMs interpretable and controllable. PICASSO decomposes FM embeddings into human-interpretable visual concepts using a sparse autoencoder. It is trained on more than 120 million tissue patches across 32 cancer types, producing the first pan-cancer atlas of histomorphological concepts. We demonstrate that PICASSO enables diverse downstream applications of FM embeddings by exposing interpretable structure within learned representations and supporting concept-level intervention. It enables auditing of clinical model behavior by revealing the morphological features driving predictions. Beyond transparency and validation, PICASSO enables the discovery of new biological insights; for example, it identified hobnailing epithelial morphology as a previously unrecognized biomarker of EGFR mutations in lung adenocarcinoma. By linking PICASSO-derived concepts with spatial transcriptomics, we uncover associations between morphological patterns and gene expression programs. Furthermore, PICASSO allows suppression of concepts associated with technical artifacts, thereby reducing model reliance on spurious signals. Finally, PICASSO enables controlled manipulation of learned concepts to generate counterfactual embeddings for exploratory therapeutic analysis, such as modulating tumour-infiltrating lymphocyte density to assess impacts on predict survival outcomes. Together, PICASSO provides a principled framework for transforming pathology FMs into platforms for mechanistic insight and discovery.

---

## 论文详细总结（自动生成）

好的，根据您提供的论文元数据及摘要内容，我将为您生成详细的中文总结。

### 0. 论文的源代码链接
无（文中未提及相关代码链接）。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：病理学基础模型（FM）能够将组织学图像编码为高维密集嵌入，但在临床诊断、分子预测等下游任务中，这些嵌入缺乏可解释性，导致模型被视为“黑箱”，限制了临床信任度，也阻碍了从模型中发现新的生物学见解（如新的形态学标志物）。
- **整体含义**：本文旨在将病理学FM从不可靠的预测工具转变为透明、可解释且可控制的平台，以促进临床转化和科学发现。通过一个名为PICASSO的框架，首次实现了对多个癌种病理学基础模型嵌入的语义分解与操控。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用稀疏自编码器（Sparse Autoencoder，SAE）将病理学基础模型的高维嵌入分解为**人类可解释的视觉概念**（concepts），从而构建一个“泛癌组织形态学概念图谱”（pan-cancer atlas of histomorphological concepts）。
- **关键技术细节**：
  - **稀疏字典学习**：训练稀疏自编码器，其中编码器将FM嵌入（如来自UNI、CONCH等基础模型的输出）映射到一个稀疏的概念空间（通常概念数远大于输入维度，但每个样本中只有少量概念被激活），解码器则从稀疏概念重构原始嵌入。
  - **概念可解释性**：每个稀疏概念对应一个视觉模式（如特定的细胞形态、组织结构、染色模式等），通过检查激活该概念的代表性组织块，可以赋予其语义标签。
  - **训练规模**：在超过**1.2亿个组织切片**上训练，覆盖**32种癌症类型**，确保概念图谱的泛癌通用性。
  - **概念级干预**：框架支持对特定概念进行抑制（如去除技术伪影）或增强（如增加肿瘤浸润淋巴细胞密度），从而生成反事实嵌入，用于探索性分析。

### 3. 实验设计：使用的数据集/场景、基准（benchmark）、对比方法
- **数据集与场景**：
  - 训练数据：超过1.2亿个组织切片，来自32种癌症类型（未指明具体公开数据集名称，可能包含TCGA等）。
  - 验证场景（包括但不限于）：
    - 模型审计：检查临床模型（如突变预测模型）依赖于哪些形态学概念。
    - 生物标志物发现：在肺腺癌中识别与EGFR突变相关的“钉突”（hobnailing）上皮形态。
    - 空间转录组关联：将PICASSO概念与空间转录组学数据（如来自Xenium等平台）对齐，揭示形态-基因表达关联。
    - 技术伪影抑制：识别并移除与石蜡、冰冻切片伪影相关的概念，改善模型鲁棒性。
    - 反事实生成：通过调节特定概念（如TIL密度）观察对预测生存结局的影响。
- **基准（benchmark）**：未提供明确的标准评测基准（如特定排行榜），主要基于定性/定量的案例分析和生物学验证。
- **对比方法**：未提及与其他可解释性方法（如注意力图、Grad-CAM、概念瓶颈模型等）的系统对比。主要强调框架本身的新颖性和通用性。

### 4. 资源与算力
文中未明确说明使用的GPU型号、数量或训练时长等算力细节。仅提及模型在超1.2亿组织块上训练，但未给出计算资源信息。

### 5. 实验数量与充分性
- **实验数量**：文中描述了多个场景下的验证实验：
  1. 模型审计（测试多个预测任务的依赖概念）。
  2. 生物标志物发现（1个具体案例：肺腺癌EGFR突变与hobnailing形态）。
  3. 空间转录组关联（至少1组实验）。
  4. 技术伪影抑制（至少1组实验）。
  5. 反事实生存分析（至少1组实验）。
- **充分性评价**：实验覆盖了可解释性、生物发现、鲁棒性、因果探索等多个维度，较为全面。但部分细节（如消融研究、不同基础模型的对比、量化评估指标）在摘要中未充分展示，因此无法全面判断公平性。总体上实验设计具有说服力，但需阅读全文以确认是否存在偏差。

### 6. 论文的主要结论与发现
- PICASSO成功将病理学基础模型的嵌入分解为人类可解释的视觉概念，构建了首个泛癌组织形态学概念图谱。
- 通过概念级审计，揭示了临床模型中驱动预测的具体形态学特征，增强了透明度和可信度。
- 发现了hobnailing上皮形态作为肺腺癌EGFR突变的一个**新的生物标志物**，验证了框架的科学发现能力。
- 将概念与空间转录组学对齐，建立了形态-基因表达关联。
- 能够通过抑制技术伪影相关概念来提升模型鲁棒性。
- 支持反事实嵌入生成，可用于探索性治疗分析（如调节TIL密度对生存结局的影响）。
- 结论：PICASSO是第一个将病理学FM转变为可解释、可控平台的原则性框架，有望推动机制研究和临床转化。

### 7. 优点
- **创新性**：首次将稀疏自编码器应用于病理学基础模型的可解释性，提出概念图谱这一通用框架。
- **规模与泛化性**：在1.2亿组织块、32种癌症上训练，概念图谱具有很好的泛癌覆盖度。
- **多维度应用**：不仅支持事后解释（审计），还支持生物发现、伪影抑制、反事实生成，功能丰富。
- **生物学验证**：发现新的形态学标志物（hobnailing）并得到初步验证，证明了框架的实用价值。
- **连接空间转录组**：将形态学概念与基因表达程序关联，提供了跨模态洞察。

### 8. 不足与局限
- **计算资源未公开**：未提供训练算力需求，可能限制可重复性。
- **评估缺乏量化基准**：未与现有可解释性方法（如注意力图、概念瓶颈模型）在标准任务上作量化对比。
- **概念可解释性的主观性**：虽然SAE分解出的概念可通过可视化赋予语义，但仍有部分概念的含义可能模糊或存在主观偏差。
- **应用限制**：框架依赖于特定基础模型的嵌入空间，更换基础模型可能需要重新训练。
- **偏差风险**：训练数据以TCGA等公共数据为主，可能低估罕见形态或多样性，概念图谱的分布代表性需进一步验证。
- **实验充分性不足**：伪影抑制和反事实生成的效果缺乏严格的量化评估（如AUC提升、校准度改善）。

（完）
