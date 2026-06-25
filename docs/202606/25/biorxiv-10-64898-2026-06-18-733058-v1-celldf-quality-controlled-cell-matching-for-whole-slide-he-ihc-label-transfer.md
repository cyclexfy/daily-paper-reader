---
title: "CellDF: Quality-controlled cell matching for whole-slide HE-IHC label transfer"
title_zh: "CellDF: 全切片HE-IHC标签转移的质量控制细胞匹配"
authors: "Jang, E., Huh, Y.-M."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733058v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 全切片HE-IHC标签迁移与细胞匹配
tldr: 串联切片HE-IHC图像存在细胞不对应和配准误差，无法直接用于细胞级监督。CellDF通过核回归估计局部自适应残差位移场，实现全切片尺度细胞匹配，无需真值对应。基于位移场分布计算方向散射和角度偏差两个统计量，作为无真值匹配质量指标，有效过滤不可靠匹配。在HyReCo和Acrobat数据集上验证了质量评估能力，并使用转移标签训练细胞分类器取得良好性能，证明串联切片可作为细胞标注资源。
source: biorxiv
selection_source: fresh_fetch
motivation: 串联切片HE-IHC配对图像在细胞级监督中未充分利用，因相邻切片细胞不同且配准误差大，无法直接分配标签。
method: 通过迭代核回归对每个HE细胞在K近邻IHC候选点中估计局部残差位移场，并采用稀疏核变体保证全切片可计算，再基于位移分布统计量过滤不可靠匹配。
result: 方向散射与标志点误差中度相关，能检测全局误差遗漏的局部染色损伤；在Acrobat数据上自动识别物理接近的IHC标志物，转移标签训练的细胞分类器F1达0.85。
conclusion: CellDF无需真值对应即可评估匹配质量，使串联切片IHC成为可用的细胞级标注资源，推动了HE-IHC联合分析。
---

## 摘要
连续切片免疫组织化学（IHC）是可用的最大配对苏木精-伊红（HE）和IHC全切片图像来源，但仍未充分利用于细胞级监督：相邻切片采样的细胞不完全相同，残留的配准误差阻止了将IHC标签直接分配给单个HE细胞。我们提出CellDF（细胞位移场），通过在全切片尺度上解决细胞匹配并评估其可靠性（无需真实对应关系），将配准后的连续切片数据转化为HE细胞及其IHC标签对。CellDF通过迭代核回归估计每个HE细胞的K个最近IHC候选的局部自适应残余位移场；稀疏核变体使其在全切片的细胞数量下可处理，而逐对匹配器无法应对。拼接块内估计位移的分布产生两个无真实值的统计量——方向散度和块间角度偏差——它们比基于标志点的目标配准误差更精细地定位匹配质量，并驱动两阶段异常值过滤器，在匹配不可靠时保留标签。在54对同一切片HyReCo上，方向散度与标志点误差仅中等相关，并标记了全局误差遗漏的局部复染损伤；在30例四标记Acrobat连续切片案例中，相同的统计量标记了哪些IHC标记（如果有）在物理上足够接近HE以支持细胞级转移。作为概念验证，通过CellDF转移的IHC标签训练了基于HE嵌入的细胞分类器，该分类器能够泛化到样本中留出的细胞（F1 0.85，AUROC 0.88），从而将连续切片IHC确立为可用的细胞级标记资源。

## Abstract
Serial-section immunohistochemistry (IHC) is the largest available source of paired hematoxylin and eosin (HE) and IHC whole slide images, yet it remains underexploited for cell-level supervision: adjacent sections sample non-identical cells, and residual registration error prevents direct assignment of IHC labels to individual HE cells. We present CellDF (Cell Displacement Field), which turns registered serial-section data into pairs of HE cells and their IHC labels by solving cell matching at whole-slide scale and assessing its reliability without ground-truth correspondences. CellDF estimates a locally adaptive residual displacement field through iterated kernel regression over K nearest IHC candidates of each HE cell; a sparse-kernel variant keeps it tractable at the cell counts of a whole slide, where pairwise matchers are not. The within-tile distribution of the estimated displacements yields two ground-truth-free statistics, the directional scatter and the between-tile angular deviation, that localize matching quality more finely than landmark-based target registration error and drive a two-stage outlier filter that withholds labels where matching is unreliable. On 54 same-section HyReCo pairs, the directional scatter correlates only moderately with landmark error and flags localized restaining damage that global error misses; on 30 four-marker Acrobat serial-section cases, the same statistic flags which IHC marker, if any, lies physically close enough to HE to support cell-level transfer. As a proof of concept, IHC labels transferred through CellDF trained a cell classifier on HE embeddings that generalized to held-out cells within the sample (F1 0.85, AUROC 0.88), establishing serial-section IHC as a usable cell-level labeling resource.

---

## 论文详细总结（自动生成）

### 0. 论文的源代码链接
无（论文未提供公开代码仓库链接）。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题**：串联切片（serial-section）HE 与 IHC 全切片图像是规模最大的配对数据来源，但由于相邻切片采样的细胞不完全相同，且配准后仍存在残余误差，无法直接将 IHC 标签分配给单个 HE 细胞，导致这类数据在细胞级监督学习中未被充分利用。
- **整体含义**：如果能可靠地将 IHC 标签迁移到对应的 HE 细胞，就能利用大量现成的串联切片数据训练细胞分类器，从而降低人工标注成本，推动 HE-IHC 联合分析在病理学中的应用。CellDF 专门解决这一匹配与质量评估难题。

### 2. 论文提出的方法论
- **核心思想**：通过估计局部自适应残差位移场（residual displacement field）来实现全切片尺度的无监督细胞匹配，并利用位移场分布统计量无真值地评估匹配质量，过滤不可靠匹配。
- **关键技术细节**：
  - **迭代核回归**：对每个 HE 细胞，在其 K 个最近 IHC 候选点中，通过迭代加权核回归估计局部位移。核函数为高斯核，带宽自适应，迭代更新权重直到收敛。
  - **稀疏核变体**：为解决全切片数十万细胞量级下的计算爆炸问题，采用稀疏核（仅保留高权重邻居），使方法在计算上可行，而传统逐对匹配算法无法处理。
  - **无真值质量统计量**：在切片划分的图块（tile）内，根据估计位移的分布计算两个指标：
    - **方向散射（directional scatter）**：位移向量方向的一致性（圆形方差）。
    - **块间角度偏差（between-tile angular deviation）**：相邻图块间平均位移方向的变化幅度。
  - **两阶段异常值过滤**：第一阶段基于方向散射过滤不可靠图块；第二阶段基于全局角度偏差过滤配准异常区域，最终保留可靠匹配对应的 IHC 标签。

### 3. 实验设计
- **数据集**：
  - **HyReCo**：54 对同一物理切片（same-section）的 HE-IHC 图像，共 54 对，提供标志点（landmark）作为真值。
  - **Acrobat**：30 例四标记（4-marker）串联切片数据集，每例包含 HE 和四种 IHC 染色，用于评估多标记匹配。
- **Benchmark**：无标准 benchmark，论文采用标志点目标配准误差（target registration error）作为间接验证，以及下游分类任务作为应用验证。
- **对比方法**：论文未提供与已有匹配方法的直接定量对比，而是将 CellDF 本身作为方法框架，重点验证其质量评估能力（与全局误差对比）和标签转移有效性（训练分类器）。

### 4. 资源与算力
**未明确说明**：文中未提及 GPU 型号、数量或训练时长。仅在方法论部分提到“稀疏核变体使全切片细胞数量下可处理”，但未提供计算性能的具体数据。

### 5. 实验数量与充分性
- **实验组数**：
  - 在 HyReCo 数据集上：54 对，分析方向散射与标志点误差的相关性，并展示局部染色损伤被标记的案例。
  - 在 Acrobat 数据集上：30 例，展示质量统计量如何为每种 IHC 标记判断是否足够接近 HE 以支持转移。
  - 下游分类实验：使用转移标签训练细胞分类器（基于 HE 嵌入），并报告在留出细胞上的性能（F1 0.85, AUROC 0.88）。
- **充分性评估**：实验覆盖了主要验证目标（质量评估的有效性和标签转移的可行性），但缺乏与其他匹配方法的直接对比（如 ICP、深度特征匹配等）。消融实验较少（仅展示两阶段过滤前后对比，但未系统比较不同统计量组合）。总体较充分但偏初步，未评估跨病例泛化性。

### 6. 论文的主要结论与发现
- **主要结论**：CellDF 无需真值对应即可评估全切片细胞匹配质量，使串联切片 IHC 成为可用的细胞级标注资源。
- **关键发现**：
  - 方向散射与标志点误差仅中等相关（表明它捕捉了不同于全局误差的局部质量信息）。
  - 方向散射能检测全局误差遗漏的局部复染损伤（restaining damage）。
  - 在 Acrobat 数据上，自动识别出哪些 IHC 标记在物理上靠近 HE（支持细胞级转移）。
  - 转移标签训练的细胞分类器达到 F1 0.85，证明串联切片数据可用于训练。

### 7. 优点
- **无监督质量评估**：不需要标注真值对应，仅利用位移分布的内在统计量即可判断匹配可靠性，适用于现实无标注场景。
- **全切片可扩展性**：稀疏核变体使得方法能在数十万细胞量级下运行，解决了传统配对方法的计算瓶颈。
- **局部敏感性**：方向散射和角度偏差能发现全局配准误差掩盖的局部病理区域（如复染损伤），优于全局误差指标。
- **多标记兼容**：可用于多标记串联切片（如 Acrobat 四标记），自动选择可用标记。

### 8. 不足与局限
- **实验覆盖局限**：仅在一个 HyReCo 数据集和一个 Acrobat 数据集上验证，未在更多器官、染色类型或大规模多中心数据上测试。
- **缺乏对比基线**：未与现有细胞匹配方法（如基于深度特征的距离匹配、最优传输、经典配准后最近邻）进行定量比较，削弱了说服力。
- **下游验证规模小**：分类器仅在一个样本内留出细胞上测试（未跨病例），泛化性未知。
- **参数敏感性**：K 值、核带宽、图块大小等超参数未进行系统消融分析，可能影响实际应用。
- **未讨论局限性**：对于没有附近 IHC 细胞的 HE 细胞（如切片厚度大导致细胞丢失），CellDF 如何表现？质量过滤是否过于保守或冒进？正文未充分讨论。
- **可重复性**：未公开代码或详细实现参数，难以复现。

（完）
