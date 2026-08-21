---
title: An AI-assisted platform for quantitative histopathological analysis in interstitial lung disease
title_zh: 一种用于间质性肺疾病定量组织病理学分析的AI辅助平台
authors: "Mizrahi, I., Guo, Y., He, J., Livneh, I., Stein, P., Shimron, R. B., Raz, A., Abu Saleh, M., Napso Shogan, T., Matalon, N., Hershfinkel, M., Cohen, H. A., Shemesh, A., Palty, R., Dotan, Y., Wolfenson, H., Hasson, P., Odeh, A."
date: 2026-08-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.16.745078v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 用于间质性肺病定量组织病理分析的人工智能辅助平台
tldr: 间质性肺病（ILD）的临床前病理评估依赖半定量、费力的常规评分，存在主观性和采样局限。本研究提出FibroSight平台，结合深度学习结构分割与颜色特征提取，对天狼星红染色切片进行全叶、多区室自动化定量。在博来霉素模型中，其指标与Ashcroft评分强相关，且优于ImageJ流程，并能区分炎症与纤维化，在人类ILD标本中验证。该平台为客观、可扩展的肺重塑定量提供了实用框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 常规ILD病理评分为半定量、主观且依赖有限视野，需更客观的全叶定量方法。
method: FibroSight融合深度学习分割与颜色特征，自动量化胶原、组织密度、核面积、气腔及气道血管重塑。
result: 博来霉素模型中与Ashcroft强相关，优于ImageJ；并能区分流感损伤的炎症与纤维化，在人类ILD活检中验证。
conclusion: 提供可扩展、可重复的多区室肺重塑定量，支持临床前和转化ILD研究。
---

## 摘要
间质性肺疾病（ILDs）是一组异质性肺部疾病，以慢性炎症和/或纤维化为特征。约30%–40%的ILD患者会发展为纤维化性疾病，与进行性呼吸功能下降和不良预后相关，尤其在特发性肺纤维化中。现有的抗纤维化疗法可延缓疾病进展，但无法逆转纤维化，这凸显了改进治疗策略的必要性。在临床前模型中进行稳健的组织病理学评估对于药物开发至关重要；然而，传统的评分系统是半定量的、劳动密集型的、受观察者间变异影响，并且依赖于有限的视野采样。在此，我们介绍FibroSight，一个用于天狼星红染色切片中肺重塑区室化定量的独立平台。通过将基于深度学习的结构分割与基于颜色的特征提取相结合，FibroSight能够实现高度自动化的全叶分析，且无需复杂的计算设置。该平台量化互补的重塑参数，包括实质胶原蛋白分数、实质组织密度、核面积分数、实质气腔分数，以及气道和血管相关的重塑。在博来霉素诱导的纤维化模型中验证，FibroSight衍生的指标与专家Ashcroft评分高度相关，并且与半自动ImageJ工作流程的对应输出相比，与组织学严重程度的关联更强。该平台还能区分流感诱导的肺损伤中的炎症性重塑与纤维化重塑，并在人类ILD活检标本中展示了转化的概念验证适用性。通过实现可扩展、可重复和多区室的组织学定量，FibroSight为肺重塑的客观评估提供了一个实用框架。该方法通过整合纤维化、炎症、气道和血管相关读数，扩展了传统的纤维化评估，支持在临床前和转化性ILD研究中更精确地分析疾病机制和治疗反应。

## Abstract
Interstitial lung diseases (ILDs) are heterogeneous pulmonary disorders characterized by chronic inflammation and/or fibrosis. 30--40% of ILD patients develop fibrotic disease that is associated with progressive respiratory decline and poor prognosis, particularly in idiopathic pulmonary fibrosis. Current antifibrotic therapies slow disease progression but do not reverse fibrosis, highlighting the need for improved therapeutic strategies. Robust histopathological evaluation in preclinical models is essential for drug development; however, conventional scoring systems are semi-quantitative, labor-intensive, subject to inter-observer variability, and rely on limited field sampling. Here, we introduce FibroSight, a standalone platform for compartment-resolved quantification of lung remodeling in Sirius Red--stained sections. By integrating deep learning--based structural segmentation with color-based feature extraction, FibroSight enables highly automated whole-lobe analysis without requiring complex computational setup. The platform quantifies complementary remodeling parameters, including parenchymal collagen fraction, parenchymal tissue density, nuclear area fraction, parenchymal airspace fraction, and airway- and vascular-associated remodeling. Validated in the bleomycin-induced fibrosis model, FibroSight-derived metrics strongly correlated with expert Ashcroft scoring and showed stronger associations with histological severity than corresponding outputs from a semi-automated ImageJ-based workflow. The platform further distinguished inflammatory from fibrotic remodeling in influenza-induced lung injury and demonstrated translational proof-of-concept applicability in human ILD biopsy specimens. By enabling scalable, reproducible, and multi-compartment histological quantification, FibroSight provides a practical framework for objective assessment of lung remodeling. This approach expands conventional fibrosis evaluation by integrating fibrotic, inflammatory, airway, and vascular-associated readouts, supporting more precise analysis of disease mechanisms and therapeutic responses in preclinical and translational ILD research.

---

## 论文详细总结（自动生成）

好的，我将按照您的要求，对这篇论文进行结构化、深入的中文总结。

## 0. 源代码链接
**无**。论文内容中未提供任何公开的源代码仓库链接。

## 1. 论文的核心问题与整体含义
- **研究背景**：间质性肺疾病（ILD）是一组以慢性炎症和/或纤维化为特征的异质性肺部疾病，其中30%–40%的患者会进展为纤维化性疾病（尤其是特发性肺纤维化IPF），预后不良。现有抗纤维化药物仅能延缓进展，无法逆转纤维化，因此亟需更有效的治疗策略和临床前评估工具。
- **核心问题**：临床前ILD模型中的组织病理学评估高度依赖半定量、劳动密集型的传统评分系统（如Ashcroft评分），这些方法存在三大固有缺陷：
  1. **主观性强**：存在观察者间差异。
  2. **效率低**：耗时耗力。
  3. **采样局限**：通常仅依赖有限的显微镜视野，无法反映全叶（whole-lobe）的整体病理变化。
- **整体含义**：该研究旨在解决这一方法论瓶颈，提出一个客观、可扩展、自动化且多区室（multi-compartment）的定量分析框架，以提高临床前及转化研究中肺纤维化/重塑评估的准确性、重复性和信息丰富度。

## 2. 论文提出的方法论
- **核心思想**：构建一个名为 **FibroSight** 的独立平台，通过将 **深度学习（Deep Learning）结构分割** 与 **基于颜色的特征提取（Color-based Feature Extraction）** 相结合，实现对天狼星红（Sirius Red）染色切片的全叶自动化定量分析，而无需复杂的计算环境设置。
- **关键技术细节**：
  - **输入**：天狼星红染色的肺组织全切片图像。
  - **两大模块**：
    1. **深度学习结构分割**：用于识别并分割肺组织的不同解剖结构（如实质、气道、血管等），实现区室化（compartment-resolved）分析。
    2. **基于颜色的特征提取**：针对天狼星红的染色特性（特异结合胶原纤维），提取颜色特征以量化胶原沉积。
  - **算法流程**（文字描述）：
    1. 输入全叶切片图像 → 2. 深度学习模型自动分割实质、气道、血管等组织区室 → 3. 在各区室内基于颜色特征计算胶原面积、组织密度、核面积、气腔面积等参数 → 4. 汇总生成多维度定量表型数据。
- **量化参数**（互补性重塑指标）：
  - 实质胶原蛋白分数（Parenchymal collagen fraction）
  - 实质组织密度（Parenchymal tissue density）
  - 核面积分数（Nuclear area fraction）
  - 实质气腔分数（Parenchymal airspace fraction）
  - 气道相关重塑（Airway-associated remodeling）
  - 血管相关重塑（Vascular-associated remodeling）

## 3. 实验设计
- **数据集/场景**：
  1. **博来霉素（Bleomycin）诱导的肺纤维化模型**：这是ILD研究中最经典、最常用的临床前动物模型，用于验证平台在纤维化定量中的核心性能。
  2. **流感（Influenza）诱导的肺损伤模型**：用于验证平台能否区分**炎症性重塑**与**纤维化重塑**，即检验其多维度表型拆解能力。
  3. **人类ILD活检标本**：用于验证平台的转化应用可行性（translational proof-of-concept）。
- **Benchmark/基准**：
  - 以**专家Ashcroft评分**（传统半定量金标准）作为组织学严重程度的主要参照基准。
- **对比方法**：
  - **半自动ImageJ工作流程**（semi-automated ImageJ-based workflow）：这是传统的组织形态计量学分析标准方法，用于比较FibroSight的定量效果和关联强度。

## 4. 资源与算力
- **文中未明确说明**。论文摘要及元数据信息中均未提及所使用的GPU型号、数量、深度学习模型训练时长或推理算力消耗等具体信息。

## 5. 实验数量与充分性
- **实验组数**：主要设计了三类独立场景实验（博来霉素模型、流感模型、人类标本验证），并包括与传统评分（Ashcroft）的相关性分析和与ImageJ方法的性能对比。
- **充分性评估**：
  - **优点**：实验覆盖了从标准纤维化模型（博来霉素）到异质性损伤模型（流感），再到人类临床样本的梯度验证，逻辑链条完整。与Ashcroft评分和ImageJ流程的双重对比，使验证维度较为全面。
  - **不足**：
    - 未提及**消融实验**（如单独验证深度学习分割模块与颜色特征模块各自的贡献度）。
    - 未报告统计检验细节（如样本量n、重复次数、相关性系数r值及P值等），削弱了实验结果的客观量化程度。
    - 流感模型仅说明“能够区分”，但未详细说明区分度指标。

## 6. 论文的主要结论与发现
- **核心结论**：FibroSight平台在博来霉素模型中衍生的定量指标与专家Ashcroft评分**高度相关**，且其与组织学严重程度的关联强度**优于**半自动ImageJ工作流程。
- **功能区分**：该平台能够成功区分流感诱导肺损伤中的炎症性重塑与纤维化重塑，证明其不仅限于纤维化定量，还能提供更细颗粒度的病理生理信息。
- **转化潜力**：在人类ILD活检标本中成功应用，展示了跨物种的转化概念验证能力。
- **总体评价**：FibroSight为ILD临床前和转化研究提供了一个**可扩展、可重复、多区室**的组织学定量实用框架，是对传统纤维化评估方法的重要扩展和升级。

## 7. 优点
- **高度自动化与全叶分析**：摆脱了人工选视野的采样偏差，实现全叶覆盖，提升了结果的全局代表性。
- **多维度区室化定量**：同时整合纤维化、炎症（核面积、组织密度）、气腔变化及气道/血管重塑等多个互补读数，信息量远超传统单一纤维化评分。
- **分析客观性与可重复性**：基于深度学习和颜色特征的确定性算法，消除了观察者间主观差异。
- **易用性强**：平台被描述为“独立（standalone）”，无需复杂的计算基础设施，有望被普通病理实验室直接采用。
- **转化验证扎实**：从经典动物模型到损伤模型再到人类标本的验证路径，增强了其转化医学价值。

## 8. 不足与局限
- **计算资源信息缺失**：未披露训练深度学习模型所需的算力（GPU型号/时长），难以评估平台复现的技术门槛。
- **算法透明度有限**：受论文内容限制，未提供深度学习分割网络的具体架构（如U-Net变体）、训练策略、数据标注量及损失函数等关键细节。
- **实验细节缺失**：缺少关键统计数字（样本量、相关系数、置信区间），且未进行消融实验，无法剥离评估每个模块对最终结果的贡献度。
- **外部扩展性待验证**：仅在单一染色（天狼星红）上进行验证，未涵盖H&E或Masson三色等常见病理染色；也未讨论不同实验室间染色批次差异对颜色特征提取带来的潜在误差（Batch effect）。
- **验证范围局限**：虽然人标本展示了概念验证，但样本规模与疾病亚型覆盖范围未知，其在真实临床病理诊断中的可靠性仍需更大规模的独立队列验证。
- **机制解释受限**：定量指标虽然丰富，但文章内容未展示如何将这些组织学定量参数与功能学指标（如肺功能、生存率）进行关联。

（完）
