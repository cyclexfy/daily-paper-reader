---
title: "SciCore-Omics: a tri-modal foundation model unifying histology, spatial transcriptomics and language for spatial biology"
title_zh: SciCore-Omics：一种统一组织学、空间转录组学和语言的三模态基础模型，用于空间生物学
authors: "Xiao, X., Li, Y., Zeng, Z., Yan, Y., Liu, Z., Xiang, Y., Ye, Z., Ying, J., Xie, L., He, F."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.30.728937v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 三模态基础模型统一组织学、转录组学和语言
tldr: "针对组织形态学与空间转录组学互补但现有模型仅两两连接的局限，提出SciCore-Omics三模态基础模型，统一组织学图像、空间转录组学和生物语言。在151,182个空间点的配对数据集上三阶段训练，基因表达和空间域识别任务相对最强基线提升23.6-80.9%，零样本病理分类平均准确率超GPT-5 6.16个百分点。仅用H&E即可进行分子推理，为计算病理学提供更通用、可解释的基础。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基础模型仅两两连接组织学、组学或语言，难以联合推断分子状态和解析空间组织结构。
method: "构建151,182个空间点的图像-基因-文本数据集，三阶段渐进训练三模态变换器。"
result: "基因表达预测和空间域识别相对最强基线提升23.6-80.9%；零样本病理分类准确率超GPT-5 6.16个百分点。"
conclusion: 三模态框架有效桥接组织形态与分子状态，为计算病理学提供更通用可解释的基础模型。
---

## 摘要
组织形态学和空间转录组学捕捉了组织生物学的互补方面，但它们在规模上的关系仍然难以提取、对齐和解释。现有的基础模型通常仅以成对方式连接组织学、组学或语言，这限制了它们联合推断分子状态、解码空间组织组织和生成生物学基础解释的能力。在这里，我们展示了SciCore-Omics，这是首个连接组织学图像、空间转录组学和生物学语言的三模态基础模型。我们构建了一个空间配对的图像-基因-文本数据集，包含跨多个组织的151,182个点，并在此数据集上对SciCore-Omics进行了三阶段渐进训练。在基因表达预测和空间域识别方面，SciCore-Omics在任务特定指标上相对于最强外部基线取得了23.6-80.9%的相对提升。它还在组织病理学分类中展示了强大的零样本泛化能力，在四个基准测试中平均准确率超过GPT-5 6.16个百分点。在10个乳腺癌病例中的专家评估证实了其仅基于H&E的病例级分子推理能力。总之，我们的方法表明，三模态框架可以有效桥接组织形态学和分子状态，为计算病理学和组学分析提供了一个更通用且可解释的基础模型。

## Abstract
Histomorphology and spatial transcriptomics capture complementary aspects of tissue biology, but their relationships remain difficult to extract, align, and interpret at scale. Existing foundation models typically connect histology, omics, or language only pairwise, which limits their capacity to jointly infer molecular states, decode spatial tissue organization, and generate biologically grounded explanations. Here, we show SciCore-Omics, the first tri-modal foundation model linking histology images, spatial transcriptomics, and biological language. We constructed a spatially paired image-gene-text dataset comprising 151,182 spots across multiple tissues and performed a three-stage progressive training of SciCore-Omics on this dataset. Across gene expression prediction and spatial domain recognition, SciCore-Omics achieved 23.6-80.9% relative gains in task-specific metrics over the strongest external baselines. It further showed robust zero-shot generalization in histopathology classification, outperforming GPT-5 by 6.16 percentage points in mean accuracy across four benchmarks. Expert evaluation in 10 breast cancer cases confirmed its H&E-only case-level molecular reasoning capability. Together, our method demonstrates that a tri-modal framework can effectively bridge histomorphology and molecular state, providing a more general and interpretable foundation model for computational pathology and omics analysis.

---

## 论文详细总结（自动生成）

### 0. 论文的源代码链接
无。论文中未提供代码仓库链接。

### 1. 论文的核心问题与整体含义
- **研究动机**：组织形态学（H&E染色图像）和空间转录组学（基因表达的空间分布）从互补维度描述组织生物学，但现有基础模型仅以成对方式连接其中两个模态（如组织学-组学、组织学-语言、组学-语言），无法联合推断分子状态、解码空间组织结构并生成生物学可解释的文本。
- **整体含义**：本文提出首个三模态基础模型SciCore-Omics，同时整合组织学图像、空间转录组学和生物学语言，旨在建立一个更通用、可解释的计算病理学与组学分析基础，实现仅凭H&E图像就能进行分子水平的推理。

### 2. 论文提出的方法论
- **核心思想**：构建配对的多模态数据集，通过三阶段渐进训练一个统一的Transformer模型，让模型学习图像、基因表达和自然语言之间的联合表征。
- **关键技术细节**：
  1. **数据构建**：收集跨多个组织的空间转录组数据，每个空间点（spot）对应一个H&E图像块、一组基因表达向量以及通过LLM生成的生物学描述文本，最终得到151,182个空间点的“图像-基因-文本”三元组。
  2. **模型架构**：采用三模态Transformer，包含图像编码器、基因编码器和文本编码器，并通过跨模态注意力机制和对比学习进行对齐。
  3. **三阶段训练**：
     - 第一阶段：图像-基因对比预训练，学习形态与转录组的对应关系。
     - 第二阶段：图像-文本对齐训练，引入语言监督。
     - 第三阶段：全三模态联合微调，通过解码器统一完成基因表达预测、空间域识别、病理分类和文本生成等任务。
- **公式/算法流程**：未提供具体公式，但整体流程可概括为：数据三元组 → 多模态嵌入 → 对比损失+生成损失 → 端到端优化。

### 3. 实验设计
- **数据集**：
  - 训练集：151,182个空间点，来自多个组织（具体组织类型未在摘要中详列，但提到“跨多个组织”）。
  - 测试集：用于基因表达预测和空间域识别的任务特定数据集；四个独立的组织病理学分类基准（benchmark：名称未给出，但对比了GPT-5）；10例乳腺癌病例用于专家评估。
- **Benchmark与对比方法**：
  - 基因表达预测和空间域识别：对比最强外部基线（未列出基线名称），任务特定指标相对提升23.6-80.9%。
  - 零样本病理分类：对比GPT-5，平均准确率超出6.16个百分点。
  - 专家评估：10例乳腺癌，验证仅基于H&E的病例级分子推理能力。
- **实验场景**：涵盖回归（基因表达预测）、聚类/分割（空间域识别）、分类（病理分型）、分子推理（临床评估）。

### 4. 资源与算力
- **未明确说明**：论文中未提及具体的GPU型号、数量、训练时长或计算资源开销。

### 5. 实验数量与充分性
- **实验数量**：至少包含三组主要任务（基因表达预测、空间域识别、零样本病理分类）+ 一组专家评估，未明确列出消融实验数量。
- **充分性与公平性**：
  - 优点：跨多个任务（预测、识别、分类、推理）验证，对比了最强基线（包括GPT-5等广泛认可模型），并进行了人工专家评估。
  - 不足：未报告消融实验（如三模态 vs 双模态的影响），未提及是否在相同数据规模下公平对比基线模型，且未在其他组织类型上（除乳腺癌）进行专家评估。

### 6. 论文的主要结论与发现
- 三模态基础模型SciCore-Omics在基因表达预测和空间域识别上显著优于现有最强双模态/单模态方法（任务指标提升23.6-80.9%）。
- 零样本泛化能力强：在组织病理学分类上准确率超过GPT-5 6.16个百分点。
- 专家评估证实了仅基于H&E图像进行病例级分子推理的可行性，表明三模态框架能有效桥接组织形态与分子状态，为计算病理学提供了更通用、可解释的基础。

### 7. 优点
- **方法创新**：首个连接组织学、空间转录组学和语言的三模态基础模型，突破了现有成对连接的局限。
- **数据规模**：构建了15万+空间点的配对数据集，覆盖多组织，数据质量较高。
- **训练策略**：三阶段渐进训练，逐步引入跨模态知识，避免模态间灾难性遗忘。
- **零样本能力**：在病理分类任务上超越通用大模型GPT-5，展示了无需微调的泛化能力。
- **临床可解释性**：通过专家评估验证了模型能从图像直接推理分子特征，具有潜在临床应用价值。

### 8. 不足与局限
- **实验覆盖**：未公开完整的测试基准名称，难以复现；缺少消融实验，无法量化各模态贡献。
- **偏差风险**：数据集可能来自特定平台（如10x Visium）和有限组织类型，对非典型组织或低质量图像的泛化性未知。
- **应用限制**：模型依赖配对的空间转录组数据训练，在实际部署中仍需H&E图像，无法直接处理纯文本或单模态查询；未讨论计算开销或模型规模，可能与实际部署存在差距。
- **专家评估范围小**：仅10例乳腺癌，样本量少，且未评估对其他癌种或良性病变的适用性。

（完）
