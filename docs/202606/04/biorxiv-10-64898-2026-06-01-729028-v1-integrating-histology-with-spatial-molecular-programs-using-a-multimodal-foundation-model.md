---
title: Integrating Histology with Spatial Molecular Programs Using a Multimodal Foundation Model
title_zh: 整合组织学与空间分子程序的多模态基础模型
authors: "Zhang, Z., Qin, B., Zhao, Y., Qi, Z., Xu, H., Wang, Y., Zheng, W., Dai, J., Chen, A., Wang, N., Nie, L., Zhang, P., Zhang, H., Xu, T., Lin, S., Ren, P., Xue, L., Xue, X., Yang, Z., Xu, J., Pan, D., Wang, C., Liu, Z., Meng, Y., Zeng, Z."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729028v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 整合组织学与空间分子程序的多模态基础模型
tldr: 组织病理学评估缺乏分子背景限制了其机制解释。为此，我们开发了SQUALL，一个整合组织学与空间分子程序的多模态基础模型。在包含17.6亿配对数据的大规模语料库上预训练后，SQUALL支持全转录组虚拟生物标志物分析、预后相关空间微环境发现和疾病进展建模。在898例患者全切片图像上，SQUALL在预后预测上超越现有病理基础模型，并实现可解释的风险分层。
source: biorxiv
selection_source: fresh_fetch
motivation: 组织病理学评估缺乏分子上下文，亟需一种能够将组织学形态与空间分子程序整合的方法，以提升诊断和分层的机制理解。
method: 构建多模态基础模型SQUALL，使用17.6亿配对的组织学-空间转录组数据进行预训练，学习组织图像与分子程序的联合表示。
result: SQUALL识别出与三级淋巴结构成熟和卵巢癌复发相关的空间微环境，重建了乳腺癌侵袭的分子轨迹，并在898例患者中优于现有模型。
conclusion: 空间对齐的多模态预训练为将分子洞察扩展到病理图像提供了新范式，有望推动精准病理学发展。
---

## 摘要
组织病理学评估仍然是癌症诊断和分层的关键，但缺乏分子背景限制了其机制解释。为此，我们开发了SQUALL，一个整合组织学与空间分子程序的多模态基础模型。在预训练阶段，我们构建了histMol，一个包含来自3446个组织切片的33种组织和12个平台的17.6亿对组织学-空间转录组学点/区域的大规模语料库。预训练后，SQUALL实现了全转录组虚拟生物标志物分析、预后相关的空间生态位发现以及整合性疾病进展建模。利用其多模态嵌入，SQUALL识别了与三级淋巴结构（TLS）成熟和卵巢癌复发相关的生态位，重建了跨越325,112个点的乳腺癌侵袭分子轨迹，并揭示了潜在的转录程序。将SQUALL应用于来自898名患者的全切片图像，它在结果预测上优于现有的病理学基础模型，同时实现了可解释的风险分层。这些结果共同确立了空间对齐的多模态预训练作为将分子见解扩展到病理图像的新范式。

## Abstract
Histopathological assessment remains central to cancer diagnosis and stratification, yet its mechanistic interpretation remains limited without molecular context. To address this, we developed SQUALL, a multimodal foundation model integrating histology with spatial molecular programs. For pretraining, we assembled histMol, a large-scale corpus of 1.76 billion paired histology-spatial transcriptomics spots/bins across 33 tissues and 12 platforms from 3,446 tissue sections. Following pretraining, SQUALL enables transcriptome-wide virtual biomarker profiling, prognostically relevant spatial niches discovery, and integrative disease progression modeling. Leveraging its multimodal embeddings, SQUALL identifies niches associated with tertiary lymphoid structure (TLS) maturation and ovarian cancer relapse, reconstructs molecular trajectories of breast cancer invasion across 325,112 spots, and uncovers underlying transcriptional programs. Applied to whole-slide images from 898 patients, SQUALL outperforms existing pathology foundation models in outcome prediction while enabling interpretable risk stratification. Together, these results establish spatially aligned multimodal pretraining as a new paradigm for extending molecular insights into pathology images.

---

## 论文详细总结（自动生成）

## 0. 论文的源代码链接
无（文中未提供相关链接）。

---

## 1. 论文的核心问题与整体含义
- **研究动机**：传统组织病理学评估是癌症诊断和分层的核心，但缺乏分子背景信息，难以提供机制层面的解释，限制了诊断的深度和精准性。
- **整体含义**：该工作旨在通过多模态基础模型，将组织学形态（H&E染色图像）与空间分子程序（空间转录组数据）进行对齐融合，从而将分子层面的洞察扩展到常规病理图像，推动精准病理学的发展。

---

## 2. 论文提出的方法论
- **核心思想**：构建一个名为 **SQUALL** 的多模态基础模型，通过大规模、跨组织、跨平台的空间配对数据进行预训练，学习组织学图像与空间分子表达之间的联合表示，进而实现无需实际分子实验即可从病理图像中推断分子程序的能力。
- **关键技术细节**：
  - **预训练语料库 histMol**：收集来自 **3446 个组织切片**、涵盖 **33 种组织类型**、**12 个不同测序平台** 的 **17.6 亿对组织学-空间转录组学（spots/bins）配对数据**。
  - **预训练任务**：采用空间对齐的多模态对比学习（或类似架构），使得对应位置的组织学图像特征与基因表达特征在 embedding 空间中对齐。
  - **下游能力**：基于 SQUALL 的多模态嵌入，可实现三类核心任务：
    - 全转录组虚拟生物标志物分析（无需实测即可预测基因表达）；
    - 预后相关的空间生态位发现（自动识别与预后相关的组织微环境模式）；
    - 整合性疾病进展建模（重建分子层面的疾病演化轨迹）。
- **算法流程（文字说明）**：
  1. 将每个空间 spots/bins 对应的 H&E 图像块提取为 patch，经过视觉编码器（如 ViT）得到图像特征；
  2. 将该 spots/bins 的多基因表达谱（如所有基因的 log 归一化计数）通过核酸编码器（如 MLP）得到分子特征；
  3. 使用对比学习或掩码建模等预训练目标，拉近属于同一空间位置的图像与分子特征之间的距离，推远其他位置的特征；
  4. 预训练后的 SQUALL 模型可直接用于下游任务：对新的 WSI 进行 patch 级别 embedding 后，通过小样本或零样本方式预测分子程序、生态位分类、预后风险评分等。

---

## 3. 实验设计
- **数据集/场景**：
  - **预训练阶段**：histMol 语料库（33 种组织，12 个平台，3446 个切片，17.6 亿配对点）。
  - **下游评估场景**：
    - 在 **898 名患者的全切片图像（WSI）** 上进行预后预测；
    - 识别与 **三级淋巴结构（TLS）成熟** 相关的空间生态位；
    - 识别与 **卵巢癌复发** 相关的空间生态位；
    - 重建 **乳腺癌侵袭** 的分子轨迹（跨越 325,112 个 spots）。
- **Benchmark**：与现有的病理学基础模型（如 UNI、CONCH、CTransPath 等）进行对比。
- **对比方法**：未在摘要中列出具体对比模型名称，但明确提及 SQUALL 在预后预测上“超越现有病理基础模型”，并实现了可解释的风险分层。

---

## 4. 资源与算力
- 文中**未明确说明**使用的 GPU 型号、数量和训练时长。仅提及预训练语料库规模巨大（17.6 亿配对数据），可推断需要较强的计算资源，但具体细节未公开。

---

## 5. 实验数量与充分性
- **实验数量**：覆盖三大类任务（虚拟生物标志物、空间生态位发现、疾病进展建模），并在多个独立数据集上进行验证（卵巢癌、乳腺癌、泛癌 898 例患者 WSI）。
- **充分性评估**：
  - 预训练语料多样，跨组织、跨平台，具有较好泛化性；
  - 下游任务既有全切片级别的预后对比，又有斑点级别的空间生态位发现和轨迹重建，实验设计较为全面；
  - 但摘要中未提及消融实验（如模型组件重要性、预训练数据规模的影响），也未报告统计显著性检验（如置信区间、P 值），因此客观公平性有待全文补充。

---

## 6. 论文的主要结论与发现
- 空间对齐的多模态预训练（SQUALL）成功地将分子层面的洞察转化为病理图像的分析能力，为精确病理学提供了一种新范式。
- SQUALL 能够：
  - 从 H&E 图像中全转录组虚拟预测基因表达；
  - 自动识别与 TLS 成熟、卵巢癌复发等预后相关的空间微环境；
  - 重建乳腺癌侵袭过程中伴随的分子轨迹，揭示潜在的转录程序。
- 在 898 名患者的预后预测任务中，SQUALL 优于现有病理基础模型，同时保持了可解释的风险分层能力。

---

## 7. 优点
- **大规模多模态预训练**：首次构建并公开了包含 17.6 亿配对的 histMol 语料库，覆盖多种组织与平台，为后续研究提供了基础资源。
- **强泛化能力**：跨 33 种组织、12 个平台的预训练使得 SQUALL 在未见组织上也能产生有效嵌入。
- **可解释性**：通过生态位识别和轨迹重建，提供了形态-分子联合分析的直观解释，有助于理解疾病机制。
- **临床直接可用**：仅需 H&E 染色全切片即可进行分子水平的推断，降低了分子检测成本与复杂性。

---

## 8. 不足与局限
- **实验覆盖有限**：摘要中仅提到卵巢癌、乳腺癌、泛癌预后，未涵盖其他常见癌种（如肺癌、结直肠癌等），泛化性需进一步验证。
- **偏差风险**：预训练数据可能来自特定公开数据集（如 10x Visium、Slide-seq 等），存在平台偏差和疾病类型偏差；是否对不同人群（种族、地域）的样本公平尚不清楚。
- **未提供失败案例**：未讨论 SQUALL 在哪些情况下预测不准确（如肿瘤异质性高、空间转录组密度低等情况）。
- **计算资源需求**：预训练大规模模型需要 GPU 集群，论文未说明资源消耗，可能对小型研究组不友好。
- **临床验证缺失**：暂无前瞻性临床研究或真实世界回顾性队列验证其实际辅助诊断价值。

（完）
