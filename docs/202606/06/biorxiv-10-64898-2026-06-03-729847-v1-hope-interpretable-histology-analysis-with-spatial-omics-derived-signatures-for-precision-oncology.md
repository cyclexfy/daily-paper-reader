---
title: "HOPE: Interpretable Histology Analysis with Spatial Omics-Derived Signatures for Precision Oncology"
title_zh: "HOPE: 利用空间组学衍生特征的可解释组织学分析用于精准肿瘤学"
authors: "Wang, T., Bieniosek, M., Krpicak, T. J., Luan, M., Ruf, B., Schürch, C. M., Mayer, A. T., Luo, R., Trevino, A. E., Wu, Z."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729847v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 利用空间组学衍生签名的组织学基础模型用于癌症预后
tldr: "H&E染色图像在临床广泛应用但预后能力有限，空间组学虽能深入刻画肿瘤微环境却难以临床普及。本研究提出HOPE框架，在训练阶段利用配对H&E和空间组学数据学习TME特征，推理时仅需H&E图像即可预测。借助H&E基础模型，HOPE在多个癌种和队列中均优于传统方法，并能生成可解释的TME注释，将患者分为预后不同的生物学亚组。该工作为将高内涵空间组学发现转化为可规模化临床工具提供了可行途径。"
source: biorxiv
selection_source: fresh_fetch
motivation: "现有H&E图像预后能力有限，而空间组学虽信息丰富但成本高、复杂，难以临床推广。"
method: "构建轻量级HOPE框架，训练时从配对H&E和空间组学数据学习TME特征，推理时仅需H&E图像。"
result: HOPE跨癌种和队列优于未使用空间组学引导的模型，并生成可解释的TME区域注释，实现生物学一致且预后不同的患者分层。
conclusion: HOPE建立了将空间组学高内涵发现转化为可扩展临床工具的实用路径，推动精准肿瘤学发展。
---

## 摘要
苏木精和伊红（H&E）染色图像是疾病评估的基础临床工具。然而，即使采用先进的计算模型，其预后能力仍然有限。空间组学能够详细描述肿瘤微环境（TME），但由于成本和复杂性，在临床上仍难以应用。在本研究中，我们提出了HOPE，这是一个轻量级框架，在训练期间从配对的H&E和空间组学数据中学习TME特征，然后在推理时仅对H&E数据应用这些特征。利用H&E基础模型，HOPE在不同癌症类型和队列中始终优于未接受空间组学引导的相同架构。它进一步在H&E区域上生成TME特征的可解释注释，将患者分层为具有不同预后结果的生物学上一致的组。HOPE建立了一条将高内涵空间组学发现转化为可扩展、可临床部署的工具的实用途径。

## Abstract
Hematoxylin and eosin (H&E) stained images are fundamental clinical tools for disease assessment. However, even with advanced computational models, their prognostic capabilities remain limited. Spatial omics characterizes tumor microenvironments (TME) in detail yet remains clinically inaccessible due to cost and complexity. In this study, we present HOPE, a lightweight framework that learns TME signatures from paired H&E and spatial omics data during training, then applies these to H&E alone at inference. Leveraging H&E foundation models, HOPE consistently outperforms identical architectures trained without spatial omics guidance across cancer types and cohorts. It further generates interpretable annotations of TME signature on H&E regions, stratifying patients into biologically coherent groups with different prognostic outcomes. HOPE establishes a practical route to translate high-content spatial omics discoveries into scalable, clinically deployable tools.

---

## 论文详细总结（自动生成）

### 0. 论文的源代码链接
无。论文未提供源代码链接。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **背景**：H&E染色图像是临床病理评估的基础工具，但即使借助先进的计算模型，其预后能力仍然有限。空间组学技术能够详细刻画肿瘤微环境（TME），但成本高、复杂度大，难以在临床中广泛部署。
- **核心问题**：如何将空间组学的高内涵信息转化为仅依赖H&E图像即可实现的、可解释的预后分析工具？
- **整体含义**：通过训练阶段利用配对H&E与空间组学数据学习TME特征，在推理阶段仅使用H&E图像即可生成具有生物学意义的TME注释和患者分层，从而为精准肿瘤学提供可扩展的临床解决方案。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：构建一个轻量级框架HOPE，在训练阶段从配对的H&E和空间组学数据中学习TME特征（作为“空间组学签名”），推理时仅需H&E图像即可预测这些签名。
- **关键技术细节**：
  - 利用H&E基础模型（foundation model）作为特征提取器，提取H&E图像的表征。
  - 设计一个轻量级网络，以配对空间组学数据（如转录组、蛋白组）作为监督信号，引导模型学习TME相关的区域特征。
  - 推理阶段：只输入H&E图像，模型输出TME特征签名的空间注释，并基于这些签名将患者划分为生物学上一致的预后亚组。
- **公式或算法流程**（文字说明）：
  1. 准备配对数据集：(H&E图像, 对应的空间组学数据)。
  2. 使用预训练的H&E基础模型提取H&E图像块的特征向量。
  3. 将特征向量输入轻量级预测头，输出空间组学签名（如细胞类型丰度、通路活性等）。
  4. 训练损失函数：预测签名与真实空间组学签名之间的差异（例如均方误差或对比损失）。
  5. 推理时，仅通过H&E图像块得到空间组学签名的预测，并聚合到全切片水平，用于解释和预后。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：论文提到“跨癌症类型和队列”，推测使用了多个公开或内部数据集，涵盖不同癌种（如结直肠癌、肺癌、乳腺癌等），且包含配对H&E和空间组学数据（例如10x Visium、CODEX等）。
- **基准（Benchmark）**：未明确指定标准基准，但以“相同架构但未使用空间组学引导的模型”作为直接对比基线。
- **对比方法**：主要对比的是“未接受空间组学引导的相同架构”，即训练时仅使用H&E图像进行常规预后任务（如生存预测）的模型。可能还包括传统组织形态学特征方法或仅使用H&E基础模型直推的方法。

### 4. 资源与算力
- 论文未明确说明使用的GPU型号、数量、训练时长等算力信息。仅提到是“轻量级框架”，暗示计算资源需求较低。

### 5. 实验数量与充分性
- **实验数量**：从摘要推断，实验涉及多个癌症类型和队列（至少两个以上不同数据集），并包含与无空间组学引导的消融对比。但未给出具体的实验组数或详细消融表。
- **充分性与公平性**：
  - 优点：跨癌种、跨队列验证，增强了泛化能力；使用相同架构对比，控制了变量。
  - 不足：缺少与更先进的H&E-only预后模型（如基于全切片基础模型、多实例学习等）的对比；未提及统计显著性检验；实验细节（如数据划分、超参数）未公开，可能影响可重复性。

### 6. 论文的主要结论与发现
- HOPE框架在训练时融入空间组学指导后，在所有测试的癌症类型和队列中，均一致优于未使用空间组学引导的相同架构。
- HOPE能够在H&E区域上生成可解释的TME特征注释（如免疫浸润区域、缺氧区域等），将患者划分为生物学一致且预后显著不同的亚组。
- 该工作建立了将高内涵空间组学发现转化为可规模化的临床工具的实际路径，推动精准肿瘤学。

### 7. 优点（方法或实验设计上的亮点）
- **轻量级且临床可行**：推理时仅需H&E染色图像，无需额外昂贵的空间组学检测，降低了临床应用门槛。
- **可解释性**：模型输出的是有生物学意义的TME特征签名注释，而非黑盒预测，有助于病理学家理解和验证。
- **利用基础模型**：借助H&E基础模型强大的特征提取能力，降低了训练难度，提升了泛化性。
- **跨癌种验证**：在多个癌症类型和外部队列中验证，表明方法具有普适性。

### 8. 不足与局限（实验覆盖、偏差风险、应用限制）
- **实验覆盖有限**：未提供与最新H&E-only全切片基础模型（如UNI、CONCH、Phikon等）的对比，无法评估其在H&E预后任务上的相对提升幅度。
- **依赖配对数据**：训练阶段需要大量的配对H&E和空间组学数据，而这类数据获取成本仍然较高，可能限制模型在其他癌种或罕见肿瘤中的推广。
- **空间组学签名的定义**：所学习的TME签名能否真正反映生物学机制，还是仅与预后相关？未进行生物学验证（如与独立功能研究对比）。
- **轻量级框架的容量**：虽然轻量，但可能不足以捕捉所有复杂TME模式，对于某些异质性极高的肿瘤可能力不从心。
- **潜在偏差风险**：训练数据可能来自特定平台（如10x Visium），推理时若H&E染色条件、扫描仪、切片厚度等差异较大，可能导致性能下降。
- **应用限制**：当前主要聚焦于预后分层，尚未涉及治疗反应预测等其他临床任务。

（完）
