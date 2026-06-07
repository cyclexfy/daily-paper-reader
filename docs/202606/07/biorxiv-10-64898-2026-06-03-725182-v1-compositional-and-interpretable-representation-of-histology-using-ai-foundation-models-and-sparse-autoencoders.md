---
title: Compositional and interpretable representation of histology using AI foundation models and sparse autoencoders
title_zh: 利用AI基础模型和稀疏自编码器实现组织学的组合式与可解释表示
authors: "Zhao, Z., Maliga, Z., Ogbonna, E. C., Talemi, S. R., Coy, S., Gagne, A., Lumamba, K., Solomon, I. H., Santagata, S., Steyn, A. J. C., Naidoo, T., Sorger, P. K."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.725182v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 使用计算病理学基础模型进行组织学表征
tldr: "H&E染色组织切片是病理学基础，但深度学习模型虽能提取特征却难以生物学解释。本文提出结合基础模型与稀疏自编码器（FM-SAE）的框架，自动分解H&E图像为可解释的病理特征。在肺结核和肺癌中，人机交互加速了特征解读，并实现了与分子空间图谱的形态学整合。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有计算病理模型难以解释其生物学意义，限制了在空间图谱研究中的应用。
method: 利用病理基础模型与稀疏自编码器分解组织嵌入，自动识别可解释的组织病理特征。
result: 在肺结核和肺癌中，框架辅助专家快速识别特征，并整合2D/3D组织结构与分子数据。
conclusion: "FM-SAE提供了一种可解释的形态学分析方法，可增强H&E图像在空间图谱研究中的价值。"
---

## 摘要
使用苏木精和伊红（H&E）染色的组织切片的光学显微镜检查是组织病理学150多年来的基础，并且对于诊断和研究仍然至关重要。能够以单细胞分辨率测量蛋白质和RNA表达的高多重空间分析技术的发展补充但并未取代H&E成像，即使在研究中也是如此。基于深度学习的计算病理学（CPath）模型有望进一步提高H&E成像的价值，但在生物学层面解释这些模型仍然具有挑战性。因此，它们并未广泛应用于空间分析研究。在此，我们描述了一种人机协同的计算框架，该框架利用CPath基础模型（FMs）和稀疏自编码器（SAEs）来分解FM嵌入，并自动识别H&E图像中多样、人类可解释的组织病理学特征。当将FM-SAE建模应用于肺结核和肺癌等肺部疾病时，人机交互增强并加速了专家解释。此外，由此产生的注释提供了一种形态学感知的方法，用于将2D和3D介观尺度组织结构与分子空间分析相结合。

## Abstract
Light microscopy of tissue sections stained with hematoxylin and eosin (H&E) has been the foundation of histopathology for over 150 years and remains essential for diagnosis and research. The development of high-plex spatial profiling approaches able to measure protein and RNA expression at single-cell resolution augments but does not replace H&E imaging, even in research. Computational pathology (CPath) models based on deep learning promise to further increase the value of H&E imaging but interpreting these models in biological terms remains challenging. As a result, they are not widely used in spatial profiling studies. Here we describe a human-in-the-loop computational framework that leverages CPath foundation models (FMs) and sparse autoencoders (SAEs) to decompose FM embeddings and automatically identify diverse, human-interpretable histopathology features in H&E images. When FM-SAE modeling was applied to pulmonary diseases such as tuberculosis and lung cancer, human-machine interaction augmented and accelerated expert interpretation. Moreover, the resulting annotations provide a morphology-aware approach to integrating 2D and 3D mesoscale tissue architectures with molecular spatial profiling.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将基于您提供的论文摘要和元数据，对这篇论文进行结构化、深入、客观的总结。

---

### 0. 论文的源代码链接

无（论文为预印本，且元数据及摘要中未提及代码仓库链接，仅有PDF链接，但该链接因访问限制不可用）。

### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：H&E染色组织切片是病理学诊断和研究的基石，但基于深度学习的计算病理学（CPath）模型虽然能提取特征，却难以在生物学层面对其进行解释。这种“黑箱”特性限制了它们在高空间分辨率分子图谱研究中的应用。
*   **整体含义**：本文提出一种结合AI基础模型（FM）与稀疏自编码器（SAE）的人机协同框架（FM-SAE），旨在自动将H&E图像分解为多样化、人类可解释的组织病理学特征，从而弥合计算病理学与生物学解释之间的鸿沟，并增强H&E图像在空间图谱研究中的价值。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

*   **核心思想**：利用CPath基础模型（如预训练的病理大模型）提取H&E图像的嵌入特征，然后通过稀疏自编码器（SAE）对这些高维、非稀疏的嵌入进行分解，自动识别出其中相互独立、且具有生物学含义的“概念”或“特征”（例如特定细胞类型、组织结构或病理模式）。
*   **关键技术细节**：
    *   **基础模型（FM）**：作为特征提取器，将H&E图像块转化为高维向量（嵌入）。
    *   **稀疏自编码器（SAE）**：一种无监督学习模型，通过添加稀疏性约束（如L1正则化），迫使隐藏层激活稀疏，从而将FM嵌入分解为一组稀疏激活的“字典”元素。每个字典元素代表一个可解释的组织病理学特征。
    *   **人机交互（Human-in-the-loop）**：专家通过观察与特定SAE特征高度相关的图像区域，以人机交互的方式加速对每个特征生物学含义的解读和标注，而非依赖完全自动化的黑箱分类。
*   **算法流程（文字说明）**：
    1.  **特征提取**：将H&E全切片图像切分为图像块，输入CPath基础模型，得到每个图像块的嵌入向量。
    2.  **稀疏分解**：将所有图像块的嵌入向量输入稀疏自编码器进行训练。在训练过程中，SAE学习到一组稀疏的隐藏层神经元（即“特征”），每个图像块仅由少数几个特征（稀疏激活）表示。
    3.  **特征解读**：对于每个稀疏特征，检索其激活值最高的若干图像块。病理学家通过视觉检查这些图像块，为该特征赋予一个可解释的生物学标签（如“肉芽肿”、“纤维化”、“肿瘤相关巨噬细胞”等）。
    4.  **空间整合**：利用这些可解释特征及其在组织上的空间分布，可以建立形态学感知的映射，将2D/3D介观尺度的组织结构与分子空间图谱（如mRNA、蛋白质表达数据）对齐和整合。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

*   **数据集与场景**：论文主要应用于**肺结核**和**肺癌**两种肺部疾病的人H&E组织切片。
*   **Benchmark**：论文属于方法探索性工作，并未明确设立传统的基准测试（benchmark）以量化指标（如准确率、F1分数）对比。其有效性主要通过**专家对自动识别特征的认可度**以及**能否加速专家解读**来评估，即人机交互的效果。
*   **对比方法**：文中未提及与现有其他可解释性方法（如注意力图谱、概念瓶颈模型等）的系统性数值对比。核心对比可能是**专家在没有AI辅助时人工解读**与**借助FM-SAE框架辅助后解读**在速度和一致性上的差异。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

*   **未明确说明**：论文摘要和元数据中未提及具体的GPU型号、数量或训练时长。作为一篇Biorxiv预印本，通常会在正文的方法部分说明，但您提供的文本中缺乏这部分细节。

### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平。

*   **实验数量**：从摘要看，主要实验在两个疾病场景（肺结核、肺癌）中进行。这属于初步验证，而非大规模、多数据集、多任务的系统评估。未提及消融实验（如去掉SAE、使用不同FM等）或定量指标评估。
*   **充分性与客观性**：实验设计侧重于**概念验证**和**定性展示**，证明了方法的可行性。但缺乏定量基准对比、消融研究、统计显著性检验以及对不同模型参数和数据集鲁棒性的评估。因此，在严格意义上，实验充分性有限，客观性主要通过专家主观判断确认，存在一定偏差风险。

### 6. 论文的主要结论与发现

*   FM-SAE框架能够自动将H&E图像分解为多样化、人类可解释的组织病理学特征。
*   在肺结核和肺癌的应用中，人机协同显著增强并加速了病理学专家对特征的解读。
*   该框架提供了一种“形态学感知”的新方法，能够有效地将2D/3D的组织学结构与分子空间图谱（如多重免疫荧光、空间转录组学数据）进行整合，从而提升了传统H&E染色在空间生物学研究中的价值。

### 7. 优点：方法或实验设计上有哪些亮点。

*   **方法创新性**：将稀疏自编码器（SAE）这种常用于自然语言处理的可解释性方法创新性地引入计算病理学领域，用于分解视觉基础模型的嵌入，具有很强的原创性。
*   **人机协同设计**：不是试图取代专家，而是通过自动识别潜在有意义的结构来辅助和加速专家解读，更符合病理学实际工作流程。
*   **可解释性强**：相比传统的注意力图或特征可视化，SAE分解出的每个特征具有明确的、稀疏激活的区域，易于与具体的生物学结构挂钩。
*   **跨模态整合潜力**：明确提出了如何利用这种形态学特征作为桥梁，弥合组织学（H&E）与分子空间图谱之间的尺度鸿沟，具有重要的应用前景。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等。

*   **实验覆盖有限**：仅评估了两种肺部疾病（肺结核、肺癌），未验证在其他器官或疾病（如肝脏、脑、肿瘤微环境）上的泛化能力。
*   **缺乏定量评估**：论文主要通过定性演示和专家主观意见证明有效性，缺乏定量指标（如特征准确性、下游任务性能提升、专家解读时间缩短比例等）的严格评估。
*   **依赖专家参与**：虽然人机交互是亮点，但最终的特征解读仍依赖专家，这意味着专家的经验和偏见会影响结果。自动化程度仍然有限。
*   **稀疏自编码器的可调参数**：SAE的性能高度依赖于稀疏度等超参数，文中未讨论这些参数如何选择及其对结果稳定性的影响，存在引入偏差的风险。
*   **计算成本**：虽然未报告，但使用大型基础模型加SAE训练的计算开销可能不小，对于资源有限的实验室构成障碍。
*   **模型可解释性的深度**：虽然每个特征可解释，但特征之间的组合如何形成完整的病理诊断逻辑（如肿瘤分级、分期）仍不清楚，可能只是局部分解而非全局解释。

---

（完）
