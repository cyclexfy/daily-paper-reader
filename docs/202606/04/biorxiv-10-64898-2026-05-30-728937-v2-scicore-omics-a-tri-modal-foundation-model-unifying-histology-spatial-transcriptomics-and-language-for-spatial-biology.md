---
title: "SciCore-Omics: a tri-modal foundation model unifying histology, spatial transcriptomics and language for spatial biology"
title_zh: "SciCore-Omics: 一个统一组织学、空间转录组学与语言的三模态基础模型，用于空间生物学"
authors: "Xiao, X., Li, Y., Zeng, Z., Yan, Y., Liu, Z., Xiang, Y., Ye, Z., Ying, J., Xie, L., He, F."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.30.728937v2.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 三模态基础模型，涵盖组织学、空间转录组学和语言
tldr: "现有基础模型仅能两两连接组织学、组学或语言，无法联合推断分子状态和空间组织。本文提出首个三模态基础模型SciCore-Omics，通过构建15万多个空间配对的图像-基因-文本数据集并进行三阶段训练，实现了组织学、空间转录组与生物语言的统一。在基因表达预测和空间域识别任务中，相对最佳基线提升23.6-80.9%；零样本病理分类准确率超越GPT-5两个百分点以上。该模型为计算病理和组学分析提供了更通用且可解释的基础。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基础模型仅两两连接组织学、组学或语言，无法实现三模态联合推理，制约了分子状态解码和组织空间组织理解。
method: 构建15万多个空间配对图像-基因-文本数据集，通过三阶段渐进训练，统一组织学、空间转录组和生物语言三模态。
result: "在基因表达预测和空间域识别任务中，相对最佳基线提升23.6-80.9%；零样本病理分类平均准确率超越GPT-5 6.16个百分点。"
conclusion: 三模态框架有效桥接组织形态与分子状态，为计算病理和组学分析提供了更通用、可解释的基础模型。
---

## 摘要
组织形态学与空间转录组学捕捉了组织生物学的互补方面，但它们之间的关系在大规模上仍难以提取、对齐和解释。现有的基础模型通常仅两两连接组织学、组学或语言，这限制了它们联合推断分子状态、解码空间组织结构和生成生物学基础解释的能力。在此，我们展示了SciCore-Omics，这是首个将组织学图像、空间转录组学和生物学语言相连接的三模态基础模型。我们构建了一个跨多种组织的空间配对的图像-基因-文本数据集，包含151,182个点，并在该数据集上对SciCore-Omics进行了三阶段渐进训练。在基因表达预测和空间域识别方面，SciCore-Omics在任务特定指标上相比最强外部基线获得了23.6%–80.9%的相对提升。它还在组织病理学分类中展现了强大的零样本泛化能力，在四个基准测试上的平均准确率比GPT-5高出6.16个百分点。在10例乳腺癌病例中的专家评估证实了其仅基于H&E染色的病例级分子推理能力。总之，我们的方法证明了三模态框架能够有效桥接组织形态学与分子状态，为计算病理学和组学分析提供了更通用和可解释的基础模型。

## Abstract
Histomorphology and spatial transcriptomics capture complementary aspects of tissue biology, but their relationships remain difficult to extract, align, and interpret at scale. Existing foundation models typically connect histology, omics, or language only pairwise, which limits their capacity to jointly infer molecular states, decode spatial tissue organization, and generate biologically grounded explanations. Here, we show SciCore-Omics, the first tri-modal foundation model linking histology images, spatial transcriptomics, and biological language. We constructed a spatially paired image-gene-text dataset comprising 151,182 spots across multiple tissues and performed a three-stage progressive training of SciCore-Omics on this dataset. Across gene expression prediction and spatial domain recognition, SciCore-Omics achieved 23.6-80.9% relative gains in task-specific metrics over the strongest external baselines. It further showed robust zero-shot generalization in histopathology classification, outperforming GPT-5 by 6.16 percentage points in mean accuracy across four benchmarks. Expert evaluation in 10 breast cancer cases confirmed its H&E-only case-level molecular reasoning capability. Together, our method demonstrates that a tri-modal framework can effectively bridge histomorphology and molecular state, providing a more general and interpretable foundation model for computational pathology and omics analysis.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文摘要与元数据生成的结构化中文总结。

---

0. **论文的源代码链接**：无（文中未提及）  
1. **论文的核心问题与整体含义**  
   - **研究动机**：组织形态学（组织学图像）和空间转录组学分别捕捉了组织生物学的互补方面，但现有方法难以在大规模上提取、对齐和解释两者之间的关系。已有的基础模型通常只两两连接组织学、组学或语言（如图像-文本、图像-基因、基因-文本），无法同时联合推断分子状态、解码空间组织并生成生物学可解释的推理。  
   - **整体含义**：该工作提出了首个三模态基础模型，旨在统一组织学图像、空间转录组学和生物语言，从而更通用、可解释地桥接组织形态与分子状态，为计算病理学和组学分析提供基础。  

2. **论文提出的方法论**  
   - **核心思想**：构建一个三模态的嵌入空间，使得组织学图像（H&E染色）、空间转录组基因表达谱以及生物文本（如基因功能描述、病理注释）可以在同一表示空间中对齐和交互。  
   - **关键技术细节**：  
     1. 数据集构建：收集并整理了一个跨多种组织的空间配对图像-基因-文本数据集，包含151,182个点（spots），每个点对应一对组织学图像块和其空间转录组基因表达谱，并关联了生物文本描述。  
     2. 三阶段渐进训练（three-stage progressive training）：  
        - 第一阶段：单独预训练每个模态的编码器（图像编码器、基因编码器、文本编码器）。  
        - 第二阶段：在配对的图像-基因数据上进行对比学习，拉近同一位置的图像和基因表示。  
        - 第三阶段：引入文本模态，通过对比学习和生成式损失（如掩码语言建模），将三个模态的表示空间统一。  
   - **算法流程说明**：输入为一个组织学图像块和对应的空间转录组点，以及该点的基因描述文本（可能来自知识库或自动生成）。三个编码器分别提取特征，然后通过跨模态对比损失（图像-基因、图像-文本、基因-文本）进行对齐；同时利用基因表达预测任务和空间域分类任务作为辅助监督。最终模型可以接受任意两个模态作为输入，输出第三个模态的表示或预测。  

3. **实验设计**  
   - **数据集与场景**：  
     - 空间转录组数据集：多种组织（具体类型未在摘要中列出）的H&E图像 + 空间基因表达，共151,182个点。  
     - 零样本病理分类基准：四个公开的组织病理学分类基准数据集（具体名称未给出），用于评估零样本泛化能力。  
     - 专家评估：10例乳腺癌病例，仅根据H&E染色进行病例级分子状态推理。  
   - **Benchmark任务**：  
     1. **基因表达预测**：从组织图像预测基因表达水平。  
     2. **空间域识别**：根据图像和基因特征对空间点进行聚类并识别组织结构域。  
     3. **零样本病理分类**：在四个基准上，不进行任务微调，直接使用模型进行病理图像分类。  
   - **对比方法**：外部基线方法（未列出具体名称，但提到“最强外部基线”），以及GPT-5（用于病理分类对比）。  

4. **资源与算力**  
   - 文中未明确说明所使用的GPU型号、数量和训练时长。需要指出：摘要中未提供具体的计算资源信息，因此无法总结。  

5. **实验数量与充分性**  
   - **实验数量**：  
     - 两个主要定量任务（基因表达预测、空间域识别） + 一个零样本分类任务（四个基准） + 一项专家评估（10例乳腺癌）。  
     - 消融实验：文中未提及是否进行了消融实验（如不同训练阶段的影响、不同模态组合的效果），但从三阶段训练的设计推断，作者可能进行了阶段消融，但摘要未汇报。  
   - **充分性评估**：  
     - 实验覆盖了多任务、跨组织、零样本和临床场景，较为全面。  
     - 但存在不足：未给出数据集的详细统计（如组织类型数量、疾病种类）、对比方法的完整列表、超参数设置、统计显著性检验等。专家评估仅10例，规模较小。  
     - 总体而言，实验设计较为合理，但受限于摘要篇幅，需查看原文以判断公平性与完备性。  

6. **论文的主要结论与发现**  
   - SciCore-Omics在基因表达预测和空间域识别任务中，相较于最强外部基线，任务特定指标提升23.6%–80.9%（相对提升）。  
   - 在零样本病理分类任务上，平均准确率超越GPT-5约6.16个百分点。  
   - 专家评估表明，模型仅基于H&E染色即可进行合理的病例级分子推理（如分子亚型）。  
   - 三模态框架有效桥接了组织形态与分子状态，提供了更通用、可解释的基础模型。  

7. **优点**  
   - **模态覆盖全面**：首个同时连接组织学、空间转录组和语言的三模态模型，突破了两两配对的限制。  
   - **训练策略创新**：三阶段渐进训练，从单模态到双模态再到三模态，逐步对齐，有助于稳定学习。  
   - **零样本能力强**：无需下游微调即可在病理分类任务上超越GPT-5，展示了强大的泛化性。  
   - **可解释性潜力**：通过语言模态可生成生物学描述，增强模型的可解释性。  
   - **数据集规模较大**：151K配对点跨多种组织，具有一定代表性。  

8. **不足与局限**  
   - **实验细节缺失**：数据集的具体组成（组织类型、疾病种类、数据来源）、对比方法的完整名称、超参数、训练配置等均未在摘要中给出，影响可复现性评估。  
   - **消融实验未见**：未报告各训练阶段、各模态组合的贡献，难以判断三模态对齐的必要性。  
   - **临床评估规模小**：仅10例乳腺癌病例，不足以证明在临床中的稳健性。  
   - **偏差风险**：数据集可能主要来自公共资源，存在组织/疾病分布偏差；零样本评估可能受数据泄漏影响（需原文验证）。  
   - **应用限制**：目前仅基于H&E和空间转录组，实际临床中可能仅能获取H&E，基因预测的准确度仍需进一步提升；模型推理速度与计算资源需求未说明。

（完）
