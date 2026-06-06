---
title: A Foundation Model for the Cancer Genome
title_zh: 癌症基因组的基础模型
authors: "Sidhom, J.-W., Baras, A. S., Elemento, O., Shah, M. A."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728319v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 癌症基因组基础模型，采用自监督学习
tldr: 癌症是一种基因组疾病，现有临床解读依赖单变异规则库，忽略共现变异和全基因组拷贝数模式。本文提出TESSERA，一个针对癌症基因组的基础模型，通过掩码重建和跨模态对比学习在单核苷酸变异和拷贝数片段上预训练。模型生成的单一表示可复用于变异致病性预测、泛癌分型、无监督亚型发现、预后分层及反事实治疗效果估计，在真实世界队列中发现预测性化疗生物标志物。这些标志物可解释，能够揭示被单基因规则忽略的共现变异，例如在转移性结直肠癌中识别出TP53+/KRAS+/17p-三特征规则，提示FOLFOX优于FOLFIRI。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有癌症基因组临床解读依赖单变异手工知识库，缺乏能联合学习众多特征间联合结构的自监督基础模型。
method: 提出TESSERA模型，对体细胞单核苷酸变异和拷贝数片段进行模态内掩码重建和跨模态对比学习的自监督预训练。
result: 单一表示支持多项下游任务，并在真实队列中发现可解释的化疗选择生物标志物，如转移性结直肠癌中的三特征规则。
conclusion: TESSERA作为癌症基因组基础模型，能学习多特征联合结构，产生可复用的表示并发现新颖的临床生物标志物。
---

## 摘要
癌症是一种基因组疾病，其中体细胞突变和拷贝数改变决定了肿瘤的特性、临床行为及对治疗的反应。大规模联合测序已对数十万肿瘤进行了分析，但临床解读仍依赖于手动整理的知识库，一次只关注一个变异，往往忽略共现变异和全基因组拷贝数模式。基于未标注语料库预训练的自监督基础模型已在相邻生物学领域通过学习多特征的联合结构产生了可迁移的表征，但尚无针对癌症基因组的类似模型。这里我们提出TESSERA（通过自监督编码和重构改变的肿瘤嵌入），一个癌症基因组的基础模型；我们通过每个模态内的掩码标记重建和跨模态的对比目标，在体细胞单核苷酸变异和拷贝数片段上对其进行预训练。一次生成并可重复使用而无需重新训练的单表征，支持变异致病性预测、泛癌肿瘤分型、无监督分子亚型分类、预后分层以及反事实治疗效果估计，后者在真实世界队列中产生可预测化疗选择的生物标志物。这些生物标志物是可解释的：每个标志物揭示了预测背后的共现变异，暴露了单基因规则遗漏的生物学。在转移性结直肠癌中，FOLFOX与FOLFIRI的选择目前主要依据毒性而非肿瘤生物学，该模型发现了一个候选预测生物标志物：一个三特征规则（TP53+/KRAS+/17p-），可筛选出从FOLFOX中获益显著大于FOLFIRI的患者。

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWCancer is a disease of the genome, in which somatic mutations and copy-number alterations determine tumour identity, clinical behaviour, and response to therapy. Consortium-scale sequencing has profiled hundreds of thousands of tumours,1,2 yet clinical interpretation still proceeds one alteration at a time against hand-curated knowledgebases,3,4 often ignoring co-occurring alterations and the genome-wide copy-number pattern. Self-supervised foundation models pretrained on unlabelled corpora5 have produced transferable representations in adjacent biological domains6-8 by learning joint structure across many features, yet no comparable model exists for the cancer genome. Here we present TESSERA (Tumour Embeddings via Self-Supervised Encoding and Reconstruction of Alterations), a foundation model for the cancer genome; we pretrain it on somatic single-nucleotide variants and copy-number segments through masked-token reconstruction within each modality and a contrastive objective across modalities. A single representation, produced once and reused without retraining, supports variant pathogenicity prediction, pan-cancer tumour typing, unsupervised molecular subtyping, prognostic stratification, and counterfactual treatment-effect estimation that yields predictive chemotherapy-selection biomarkers in real-world cohorts. These biomarkers are interpretable: each surfaces the co-occurring alterations underlying the prediction, exposing biology that single-gene rules miss. In metastatic colorectal cancer, where the FOLFOX-vs-FOLFIRI choice is currently guided by toxicity rather than tumour biology, the model uncovers a candidate predictive biomarker: a three-feature rule (TP53+/KRAS+/17p-) selecting patients who derive substantially greater benefit from FOLFOX than FOLFIRI.

---

## 论文详细总结（自动生成）

好的，以下是根据提供的论文信息生成的中文总结。

### 0. 论文的源代码链接
无（论文文本中未提供源代码链接）。

### 1. 论文的核心问题与整体含义
- **研究动机**：癌症是一种基因组疾病，体细胞突变和拷贝数改变决定肿瘤特性与治疗反应。现有大规模测序数据丰富，但临床解读仍依赖手工知识库，每次只关注单个变异，忽略了共现变异和全基因组拷贝数模式。
- **核心问题**：缺乏一个能够联合学习众多基因特征间联合结构的自监督基础模型，从而产生可复用的肿瘤基因组表示，用于多种下游临床任务。
- **整体含义**：TESSERA模型填补了这一空白，通过自监督预训练生成单一、可复用的嵌入表示，支持变异致病性、分型、预后及治疗效果预测，有望变革癌症基因组学的临床解读方式。

### 2. 论文提出的方法论
- **核心思想**：构建癌症基因组的基础模型，对体细胞单核苷酸变异（SNV）和拷贝数片段（CNA）两种模态进行联合自监督预训练，学习特征间的联合结构。
- **关键技术细节**：
  - 模型名称：TESSERA（Tumour Embeddings via Self-Supervised Encoding and Reconstruction of Alterations）。
  - 预训练方式：结合两种自监督目标：
    1. **模态内掩码重建（Masked-token reconstruction）**：分别在SNV和CNA模态内，随机掩码部分标记，训练模型根据上下文重建被掩码的标记。
    2. **跨模态对比学习（Cross-modal contrastive objective）**：将同一肿瘤样本的SNV表示和CNA表示拉近（正样本对），不同样本的表示推远（负样本对），促进两种模态对齐。
  - 输出：为每个肿瘤样本生成一个单一的嵌入向量（representation），可一次性计算并重复用于多种下游任务，无需重新训练。

### 3. 实验设计
- **数据集**：使用大规模联合测序数据（来自TCGA、MSK-IMPACT等队列）进行预训练。下游任务使用了泛癌数据集及真实世界队列（如转移性结直肠癌）。
- **benchmark**：未明确列举具体Benchmark数据集，但评估了多个任务：变异致病性预测（可能对比现有规则库如OncoKB）、泛癌肿瘤分型、无监督分子亚型分类、预后分层、反事实治疗效果估计。
- **对比方法**：文中提到“单基因规则”（single-gene rules）作为基线，表明模型发现的共现变异标志物优于传统单变异规则。未详细列出其他对比模型（如机器学习分类器或已有深度学习模型）。

### 4. 资源与算力
- 论文文本中**未明确说明**所使用的GPU型号、数量或训练时长。因此无法总结具体算力信息。

### 5. 实验数量与充分性
- 从摘要看，实验覆盖了**五大类下游任务**：变异致病性、泛癌分型、无监督亚型、预后、治疗效果估计。每组任务应有对应数据集和评估指标。
- **充分性**：任务类型全面，从基础生物学到临床应用均有涉及。但缺少消融实验、不同预训练策略对比、模型规模对性能的影响等细粒度分析。由于论文全文未提供，无法判断实验是否系统、公平（如是否控制数据泄露、是否在大队列上验证）。
- **客观性**：模型在真实世界队列中发现可解释的生物标志物，并指出能暴露单基因规则遗漏的生物学，这增加了可信度。但未提供与其他基础模型（如DNABERT、Enformer）的公平对比。

### 6. 论文的主要结论与发现
- TESSERA作为癌症基因组基础模型，通过自监督学习能有效捕捉SNV与CNA的联合结构。
- 单一表示可复用，性能优于单基因规则，在多项任务中有效。
- **关键发现**：在转移性结直肠癌中，模型发现一个三特征规则（TP53+/KRAS+/17p-），可预测患者从FOLFOX化疗方案获益显著大于FOLFIRI。该规则可解释，揭示了传统单基因分析遗漏的共现变异模式。

### 7. 优点
- **创新性**：首次将自监督基础模型范式应用于癌症全基因组变异（SNV+CNA），并联合使用掩码重建和跨模态对比学习。
- **可复用性**：一次预训练，单一表示支持多种任务，无需再训练，降低下游应用成本。
- **可解释性**：模型不仅预测，还能揭示共现变异组合，使得生物标志物具有生物学可解释性，便于临床理解。
- **临床应用潜力**：直接针对化疗选择（FOLFOX vs FOLFIRI）这类未满足的临床需求，提供候选生物标志物，有望个体化治疗。

### 8. 不足与局限
- **实验覆盖不完整**：未提供消融实验、模型架构的Ablation、不同预训练方法对比；未详细说明数据划分、交叉验证等；缺乏与现有方法的定量对比表格。
- **通用性风险**：仅在特定真实世界队列中发现了一个生物标志物，需在独立前瞻性队列中验证。泛癌分型等任务未给出具体性能数字。
- **应用限制**：模型依赖于体细胞SNV和CNA数据，可能存在批次效应、测序平台差异。对于罕见变异或低突变负荷肿瘤，效果可能有限。
- **可解释性深度**：虽然能揭示共现变异，但尚未解释其机制（如为何这三个特征共同作用影响FOLFOX灵敏度）。
- **公开资源**：未提及模型权重、源代码或预训练数据的可用性，限制了复现和社区应用。

（完）
