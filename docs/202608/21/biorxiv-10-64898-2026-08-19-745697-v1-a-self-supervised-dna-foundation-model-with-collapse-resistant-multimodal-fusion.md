---
title: A self-supervised DNA foundation model with collapse-resistant multimodal fusion
title_zh: 具有抗坍缩多模态融合的自监督DNA基础模型
authors: "Chen, Y."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745697v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 自监督DNA基础模型与多模态融合
tldr: 基因组基础模型仅依靠DNA序列难以全面刻画调控信息，而现有多模态模型多针对特定任务，缺乏可复用嵌入。直接融合稀疏峰状调控信号与密集序列表征易引发多模态对齐退化，导致近零解。本文提出自监督DNA多模态基础模型，将序列嵌入与局部及全局染色质可及性在共享编码器中融合，通过全局归一化缓解模态坍塌，生成窗口级嵌入。在调控活性预测、信号排序和峰检测等任务上显著超越DNA-only基线，峰检测AUPRC提升4.6倍，并在ClinVar等外部数据上验证有效，为多模态DNA基础模型提供可扩展方法框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 序列-only模型无法完整反映调控信息，而现有多模态融合面临稀疏与密集模态对齐易退化为近零解的问题，缺乏可复用嵌入。
method: 提出自监督DNA多模态基础模型，在共享编码器中融合序列嵌入与局部/全局染色质可及性，并用全局归一化抑制模态坍塌。
result: 峰检测AUPRC较DNA-only提升4.6倍，调控活性预测与信号排序更优，ClinVar等外部验证表现改善。
conclusion: 全局归一化有效缓解异质模态退化，多模态融合框架可扩展至更多调控模态，为DNA基础模型提供方法论基础。
---

## 摘要
基因组基础模型在DNA序列上预训练已在多种任务上取得强劲性能，但仅序列的表征无法完全捕捉由额外以DNA为中心的多模态所反映的调控信息。现有基因组多模态模型通常针对特定预测任务进行优化，而非学习可复用的、跨下游分析共享的嵌入。然而，直接融合异质性基因组模态具有挑战性，因为稀疏的峰状调控信号与稠密的序列表征具有显著不同的统计结构，使得朴素的多模态对齐易于退化为接近零的解。我们提出了一种自监督的、以DNA为中心的多模态基础模型来解决这一不足，该模型在共享多模态编码器中整合DNA序列嵌入与局部和全局染色质可及性，生成可复用的窗口级嵌入，同时支持预训练期间的掩码重建和下游预测任务。我们诊断了这种异质性模态对齐失败，并表明全局归一化可显著缓解坍缩，从而实现跨模态的有效联合学习。得到的嵌入改善了多项调控功能的下游评估，包括调控活性预测、调控信号排序和染色质可及性峰检测，在峰检测上相比仅DNA基线实现了4.6倍的AUPRC提升，并进一步改进了ClinVar、GTEx eQTL和PBMC caQTL数据集上的外部验证。该框架可扩展到更多调控模态，为多模态DNA基础模型提供了方法论基础。

## Abstract
Genomic foundation models pretrained on DNA sequence have achieved strong performance across a range of tasks, but sequence-only representations cannot fully capture regulatory information reflected by additional DNA-centric modalities. Existing multimodal genomic models are often optimized for specific prediction tasks rather than for learning reusable embeddings shared across downstream analyses. However, directly fusing heterogeneous genomic modalities is challenging because sparse, peak-shaped regulatory signals and dense sequence representations have markedly different statistical structures, making naive multimodal alignment prone to degenerate near-zero solutions. We present a self-supervised DNA-centric multimodal foundation model that addresses this gap, integrating DNA sequence embeddings with local and global chromatin accessibility in a shared multimodal encoder to produce reusable window-level embeddings that support both masked reconstruction during pre-training and downstream prediction tasks. We diagnose this heterogeneous-modality alignment failure and show that global normalization substantially alleviates collapse, enabling effective joint learning across modalities. The resulting embeddings improve multiple downstream evaluations of regulatory function, including regulatory activity prediction, regulatory signal ranking and chromatin accessibility peak detection, achieving a 4.6-fold AUPRC improvement over the DNA-only baseline in peak detection, and further improving external validation on ClinVar, GTEx eQTL and PBMC caQTL datasets. The framework is extensible to additional regulatory modalities, providing a methodological basis for multimodal DNA foundation models.

---

## 论文详细总结（自动生成）

## 0. 源代码链接
无（论文摘要中未提供任何开源代码链接）。

## 1. 论文的核心问题与整体含义
- **研究动机**：现有的基因组基础模型主要在DNA序列上预训练，但仅靠序列无法完整捕捉调控信息。额外的以DNA为中心的多模态数据（如染色质可及性）能提供更丰富的调控线索，但现有基因组多模态模型多是为特定任务定制，缺乏可复用的通用嵌入。
- **核心问题**：如何在大规模自监督框架下，将稀疏、峰状的调控信号（如ATAC-seq峰）与稠密的DNA序列表征有效融合，避免多模态对齐退化（即模型坍缩到近零解），从而学习到可迁移的窗口级嵌入。
- **整体意义**：提出一个可扩展的多模态DNA基础模型框架，为后续将更多调控模态纳入基础模型提供方法论基础。

## 2. 论文提出的方法论
- **核心思想**：构建一个自监督的、以DNA为中心的多模态基础模型，在共享编码器中同时处理DNA序列嵌入与局部/全局染色质可及性信号，生成窗口级嵌入，既能用于预训练时的掩码重建，又能直接用于下游预测任务。
- **关键技术细节**：
  - 输入包括：DNA序列、局部染色质可及性信号、全局染色质可及性信号。
  - 使用**共享多模态编码器**进行联合表征学习。
  - 针对异质模态（稀疏峰状 vs 稠密序列）对齐易坍缩的问题，引入**全局归一化**机制，显著缓解了模态坍缩。
- **算法流程**（文字描述）：
  1. 将DNA序列切分为窗口，编码为序列嵌入；
  2. 将局部和全局染色质可及性信号映射为对应的模态嵌入；
  3. 在共享编码器中对三种模态进行融合，期间施加全局归一化防止坍缩；
  4. 预训练目标为掩码重建（对部分输入掩码并重建）；
  5. 预训练得到的窗口级嵌入可零样本或微调地用于下游任务。

## 3. 实验设计
- **主要任务/benchmark**：
  - 调控活性预测（regulatory activity prediction）
  - 调控信号排序（regulatory signal ranking）
  - 染色质可及性峰检测（chromatin accessibility peak detection）
- **外部验证数据集**：
  - ClinVar
  - GTEx eQTL
  - PBMC caQTL
- **对比方法**：以“仅DNA（DNA-only）”模型为主要基线，同时隐含对比现有针对特定任务的多模态模型（但摘要未列出具体基线名称）。
- **消融性验证**：通过对比有无全局归一化来诊断模态对齐失败，验证全局归一化的有效性。

## 4. 资源与算力
- **未在摘要中提及**任何GPU型号、数量、训练时长或计算量信息。仅能判断该模型为大规模预训练模型，但具体算力需求未知。

## 5. 实验数量与充分性
- **实验组数**：摘要明确提到的实验任务有3项（活性预测、信号排序、峰检测），外加3个外部数据集验证（ClinVar、GTEx eQTL、PBMC caQTL）。此外还包含对全局归一化的消融诊断实验。
- **充分性评估**：
  - **优点**：覆盖了多种调控任务、外部独立数据集以及关键消融，能初步证明方法的有效性和泛化性。
  - **不足**：由于摘要篇幅限制，无法判断是否包含与多个现代基线（如其他多模态模型）的系统比较，也未给出统计显著性和方差信息；实验覆盖广度有限（未涉及更多任务类型如变异效应预测、细胞类型特异性分析等）。

## 6. 论文的主要结论与发现
- 直接融合稀疏调控信号与稠密序列特征容易导致多模态对齐坍缩到近零解。
- 全局归一化能显著缓解这种坍缩，实现跨模态有效联合学习。
- 所提出的多模态基础模型在调控活性预测、信号排序和峰检测上均优于仅DNA基线，其中峰检测AUPRC提升4.6倍。
- 在ClinVar、GTEx eQTL和PBMC caQTL上的外部验证进一步表明嵌入的可迁移性。
- 该框架可扩展到更多调控模态，为多模态DNA基础模型提供了方法论基础。

## 7. 优点
- **方法创新**：首次（或较先）提出自监督的DNA多模态基础模型，专注于生成可复用嵌入而非单一任务。
- **问题诊断明确**：明确指出异质模态融合的“近零坍缩”问题，并针对性地提出全局归一化方案。
- **性能提升显著**：峰检测AUPRC相对DNA-only提升4.6倍，效果明显。
- **验证扎实**：在多个下游任务和外部数据集上验证，体现嵌入的普适性。
- **可扩展性**：框架设计可容纳多种调控模态，有较强的后续发展潜力。

## 8. 不足与局限
- **信息缺失**：未在摘要中提供源代码、模型配置、训练数据规模、算力等细节，复现难度较大。
- **实验覆盖有限**：外部数据集虽覆盖ClinVar、GTEx、PBMC，但均为特定组织/细胞类型（如PBMC），对多样本、多组织泛化缺乏展示。
- **对比基线不够全面**：仅提及DNA-only基线，未明确列出与现有专门多模态模型的性能比较，无法判断相对最先进方法的具体优势。
- **偏差风险**：峰检测的性能提升可能受全局归一化与特定染色质信号统计结构的影响，在其他类型模态（如甲基化、Hi-C）上的适用性有待验证。
- **未讨论失败案例**：对哪些场景下融合仍然失效、全局归一化是否带来副作用等缺乏分析。

（完）
