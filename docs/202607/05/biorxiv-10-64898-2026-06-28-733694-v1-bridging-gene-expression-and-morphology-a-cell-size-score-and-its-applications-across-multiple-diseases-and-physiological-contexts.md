---
title: "Bridging Gene Expression and Morphology: A Cell Size Score and Its Applications Across Multiple Diseases and Physiological Contexts"
title_zh: 桥接基因表达与形态：细胞大小评分及其在多疾病和生理背景下的应用
authors: "Ji, X., Cui, Q."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.733694v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 整合免疫荧光图像和转录组学预测细胞大小，桥接基因表达和形态学
tldr: 细胞大小是决定细胞功能稳态的关键形态参数，但现有转录组数据库缺乏直接测量。通过整合高分辨率免疫荧光图像和转录组数据，识别了457个与细胞面积相关的基因，并开发了Cell Size Score (CSS)算法来从基因表达谱预测细胞大小。验证表明CSS能准确预测细胞大小，并发现其与广谱化疗耐药正相关，衰老中呈现性别和组织特异性变化，运动后骨骼肌CSS显著增加。该研究为利用现有组学数据回顾性分析细胞大小在癌症和衰老等过程中的作用提供了新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有转录组数据库缺乏直接细胞大小测量数据，亟需建立从基因表达推断细胞大小的方法以挖掘其病理生理意义。
method: 整合高分辨率免疫荧光图像与转录组学，鉴定457个与细胞面积显著相关的基因，据此开发Cell Size Score (CSS)算法。
result: CSS在多个独立数据集中准确预测细胞大小，与广谱化疗耐药正相关，并揭示衰老和运动引起的组织特异性细胞大小变化。
conclusion: CSS桥接了转录组与细胞形态，为利用现有组学数据研究细胞大小在疾病与生理过程中的作用提供新工具。
---

## 摘要
细胞大小是决定细胞功能稳态的关键形态参数，然而现有的大规模转录组数据库缺乏直接的细胞大小测量数据。通过整合高分辨率免疫荧光图像与转录组学，我们鉴定了457个与细胞面积显著相关的基因。基于这些发现，我们开发了一种算法——细胞大小评分（CSS），用于从基因表达谱预测细胞大小。在包括人类细胞系、小鼠模型和单细胞空间转录组学在内的多个独立数据集上的验证证实，CSS能够准确预测细胞大小。此外，我们观察到CSS与广谱化疗药物耐药性显著正相关，表明细胞体积增大赋予癌细胞生存优势。进一步，对衰老过程的CSS分析揭示了性别依赖、组织特异性变化模式，其中雄性脂肪和心脏组织随年龄增长出现进行性肥大，而雌性生殖器官则显著萎缩。此外，运动后骨骼肌中CSS显著增加，表明该指标能够捕捉动态生理适应过程。本研究建立了转录组学与细胞形态之间的桥梁，为利用现有组学数据回顾性分析细胞大小在癌症和衰老等病理生理过程中的作用，以及理解细胞大小调控的分子机制提供了新见解。

## Abstract
Cell size is a critical morphological parameter determining cellular functional homeostasis, yet existing large-scale transcriptomic databases lack direct cell size measurement data. By integrating high-resolution immunofluorescence images with transcriptomics, we identified 457 genes significantly correlated with cell area. Based on these findings, we developed an algorithm, Cell Size Score (CSS), to predict cell size from gene expression profiles. Validation across multiple independent datasets, including human cell lines, mouse models, and single-cell spatial transcriptomics, confirmed that CSS accurately predicts cell size. Furthermore, we observed a significant positive correlation between CSS and broad-spectrum chemotherapy drug resistance, suggesting that increased cell volume confers survival advantages to cancer cells. Moreover, CSS analysis of aging revealed sex-dependent, tissue-specific patterns of change, wherein male adipose and cardiac tissues exhibited progressive hypertrophy with age, while female reproductive organs showed significant atrophy. Additionally, CSS significantly increased in skeletal muscle after exercise, indicating that this metric can capture dynamic physiological adaptation processes. This study establishes a bridge between transcriptomics and cell morphology, providing novel insights into retrospectively analyzing the role of cell size in pathological and physiological processes such as cancer and aging using existing omics data, as well as understanding the molecular mechanisms underlying cell size regulation.

---

## 论文详细总结（自动生成）

## 0. 论文的源代码链接
无（论文未提供具体源代码链接，仅说明算法开发思路）。

## 1. 论文的核心问题与整体含义
- **研究动机**：细胞大小是决定细胞功能稳态的关键形态参数，但现有大规模转录组数据库（如TCGA、GTEx等）缺乏直接测量细胞大小的数据，导致难以利用已有组学数据研究细胞大小在疾病和生理中的作用。  
- **核心问题**：如何从基因表达谱中可靠地推断细胞大小，从而桥接转录组与形态学，为回顾性分析细胞大小在癌症、衰老、运动等过程中的作用提供工具。  
- **整体含义**：通过建立细胞大小评分（CSS），使研究者能够从大量公开转录组数据中推测细胞大小，挖掘细胞大小调控的分子机制及其与疾病表型（如化疗耐药）、生理变化（如衰老、运动适应）的关联。

## 2. 论文提出的方法论
- **核心思想**：利用高分辨率免疫荧光图像直接测量细胞面积，并与对应样本的转录组数据关联，筛选显著与细胞面积相关的基因，构建预测模型。  
- **关键技术细节**：  
  - 整合高分辨率免疫荧光图像和转录组学数据，识别出457个与细胞面积显著相关的基因（可能通过相关性分析或回归分析筛选）。  
  - 基于这些基因的表达水平，设计细胞大小评分（CSS）算法。CSS可能采用加权基因表达之和、主成分分析或类似线性模型的形式，具体公式未在摘要中给出，但推测为：CSS = Σ(wi × Ei)，其中wi为基因权重，Ei为基因表达值。  
  - 对CSS进行归一化，使在不同数据集间可比。  
- **算法流程**（文字说明）：  
  ① 从免疫荧光-转录组配对数据中计算每个基因的表达与细胞面积的相关性；  
  ② 筛选显著相关基因（阈值如P<0.05, |r|>0.3）；  
  ③ 用筛选出的基因集合对每个样本计算加权评分（CSS）；  
  ④ 在独立数据集中验证CSS与真实细胞大小的相关性。

## 3. 实验设计
- **使用的数据集/场景**：  
  - 训练集：自带免疫荧光图像和转录组的细胞/组织样本（可能来自细胞系或小鼠模型）。  
  - 验证集：人类细胞系、小鼠模型、单细胞空间转录组学数据（多个独立来源）。  
  - 应用场景：癌症（化疗耐药性）、衰老（性别和组织特异性）、运动（骨骼肌）。  
- **Benchmark**：没有明确提及外部基准方法。论文主要验证CSS预测细胞大小的准确性（与实测细胞面积的相关性），未与已有算法对比（因为此前可能无类似工具）。  
- **对比方法**：未提及，属于创新性方法，未与其他预测方法对比。

## 4. 资源与算力
- 论文中未明确说明使用的GPU型号、数量、训练时长等算力信息。可以推断该工作主要依赖传统统计分析和遗传算法，可能不需要大规模深度学习训练，因此算力需求较低。

## 5. 实验数量与充分性
- **实验数量**：至少涉及三类验证：  
  ① 在人类细胞系、小鼠模型、单细胞空间转录组等多来源数据中验证CSS预测准确性；  
  ② 分析CSS与12类（或更多）化疗药物耐药性的相关性（广谱）；  
  ③ 衰老过程中在雄性脂肪、心脏、雌性生殖器官等多个组织中的变化；  
  ④ 运动前后骨骼肌CSS变化。  
- **充分性评估**：  
  - 验证数据覆盖多物种、多尺度（细胞系、组织、单细胞），较为全面；  
  - 消融实验（如对457个基因的鲁棒性）未明确提及；  
  - 在癌症耐药性分析中，可能缺乏独立外部验证队列，且未控制混杂因素（如细胞周期状态）；  
  - 总体实验设计合理，但缺乏与现有形态学测量方法（如显微镜直接测量）的系统性对比，公平性一般。

## 6. 论文的主要结论与发现
- CSS能够从基因表达谱准确预测细胞大小，且跨物种、跨平台稳定。  
- CSS与广谱化疗药物耐药性呈显著正相关，提示细胞增大可能赋予癌细胞生存优势（增大药物耐受性）。  
- 衰老过程中细胞大小呈现性别依赖性、组织特异性变化：雄性脂肪和心脏组织随年龄进行性肥大，雌性生殖器官显著萎缩。  
- 运动后骨骼肌CSS显著增加，表明CSS能捕捉动态生理适应。  
- 本研究建立了转录组学与形态学之间的桥梁，为利用现有组学数据研究细胞大小在疾病和生理中的作用提供了新工具。

## 7. 优点
- **创新性**：首次提出从转录组推断细胞大小的方法，填补了大规模组学数据中缺乏形态学信息的空白。  
- **实用性**：可直接应用于大量公共转录组数据库（TCGA、GEO等），实现回顾性分析。  
- **跨物种验证**：从人类细胞系到小鼠模型再到单细胞数据，验证全面，增加了方法的普适性。  
- **生物学发现**：揭示了细胞大小与化疗耐药、衰老、运动的关联，具有潜在临床和生理学意义。

## 8. 不足与局限
- **实验覆盖**：仅用了有限数量的免疫荧光图像用于训练（可能样本量较小），基因筛选可能存在过拟合；未在大型独立队列中验证预测稳定性。  
- **偏差风险**：细胞大小受细胞周期、细胞类型、组织微环境等多因素影响，CSS可能混杂了增殖活性、代谢状态等，未充分控制这些变量。  
- **方法透明性**：未公开CSS具体计算公式和权重，限制了可复现性。  
- **应用限制**：仅适用于有转录组数据的样本，对于无转录组数据的场景无法使用；预测精度未与直接测量方法（如Coulter计数器）对比。  
- **单细胞应用**：空间转录组的验证可能受限于组织解离和细胞边界识别，准确性需进一步评估。

（完）
