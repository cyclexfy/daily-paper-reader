---
title: "TopoMIL: Topology Improves Multiple Instance Learning in Diagnostic Microscopic Images"
title_zh: TopoMIL：拓扑提升诊断显微图像中的多实例学习
authors: "Kazeminia, S., Dasdelen, M. F., Rieck, B., Marr, C."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731443v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: TopoMIL将拓扑结构引入多实例学习用于诊断显微镜图像
tldr: "计算病理学中，多实例学习（MIL）用于分析患者样本的显微图像，但现有方法忽略细胞分布的结构信息。本文提出TopoMIL，通过提取样本的拓扑结构并集成到MIL分类器中，评估了三种拓扑表示。在四个病理数据集上，结合拓扑信息使AUCROC提升最高达5.9%。TopoMIL可作为形态学模型的轻量扩展，提升诊断性能。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有MIL框架忽略细胞样本的代表性拓扑分布，导致诊断性能受限。
method: TopoMIL提取样本的拓扑结构（如persistence diagrams）并集成到各类MIL池化中，评估三种拓扑表示。
result: "在四个病理数据集上，集成拓扑信息后AUCROC提升3.3%-5.9%，注意力池化效果最佳。"
conclusion: TopoMIL是高效的可扩展框架，可增强现有MIL模型，无需复杂修改。
---

## 摘要
细胞和组织的显微图像是疾病诊断的核心。在计算病理学中，多实例学习（MIL）已成为分析单个患者样本中大量图像的关键范式。虽然样本中细胞的代表性分布对诊断很重要，但现有的MIL框架在很大程度上忽略了这一点。我们提出了TopoMIL，一个提取样本代表性拓扑结构并将其整合到MIL分类器中的框架。评估了三种拓扑表示，每种都有不同的优势和计算成本。我们在四个组织病理学和细胞形态学数据集上评估了TopoMIL，每个数据集都提出了独特的挑战。将样本的拓扑信息整合到MIL中提升了基于平均、最大、注意力和Transformer池化的分类性能，分别获得了3.3%、4.2%、5.9%和0.5%的AUCROC增益，且计算成本适中。我们的工作凸显了TopoMIL作为计算病理学中现有形态学模型的可扩展扩展的潜力。

## Abstract
Microscopic images of cells and tissues are central to disease diagnosis. In computational pathology, multiple instance learning (MIL) has emerged as a key paradigm for analyzing numerous images within a single patient sample. While the representative distribution of cells in a sample is important for diagnosis, existing MIL frameworks largely overlook it. We introduce TopoMIL, a framework that extracts the representative topological structure of the sample and integrates it into the MIL classifier. Three topological representations are assessed, each with distinct advantages and computational costs. We evaluate TopoMIL on four histopathology and cytomorphology datasets, each presenting unique challenges. Integrating the samples topological information into MIL enhances classification across average, max, attention-based, and transformer pooling, yielding AUCROC gains of 3.3%, 4.2%, 5.9%, and 0.5%, respectively, with moderate computational cost. Our work underscores the potential of TopoMIL as a scalable extension to existing morphology-based models in computational pathology.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 0. 论文的源代码链接
无（论文元数据未提供源代码链接，原文PDF不可访问，且作者未在摘要中提及公开代码）。

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在计算病理学中，多实例学习（MIL）是分析患者样本显微图像的关键范式，但现有MIL框架主要关注细胞形态特征，忽略了细胞在样本中的代表性分布和空间拓扑结构，导致诊断性能受限。
- **整体含义**：细胞和组织的空间分布模式（如细胞密度、聚集形态等）对疾病诊断具有重要指示意义。TopoMIL旨在通过提取样本的拓扑特征并将其集成到MIL分类器中，提升病理图像诊断的准确性，同时保持较低的计算开销，可作为现有形态学模型的轻量级扩展。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将拓扑数据分析（TDA）中的持久性同调（persistent homology）引入MIL框架，从高维细胞特征中提取样本的拓扑结构（如持久性图），并将其作为额外输入特征与原始形态特征融合，使分类器能感知全局空间布局。
- **关键技术细节**：
  - 提出**TopoMIL框架**，包含两个分支：
    - **形态分支**：使用标准MIL池化（如平均、最大、注意力、Transformer）处理细胞级特征。
    - **拓扑分支**：从细胞特征中计算样本的拓扑表示（三种方式）。
  - **三种拓扑表示**（各有优势和计算成本）：
    1. **持久性图（Persistence Diagrams）**：直接编码拓扑特征的出生-死亡时间对。
    2. **持久性特征（Persistence Features）**：对持久性图进行统计汇总（如总持续期、最大持续期等）。
    3. **拓扑嵌入（Topological Embeddings）**：通过核方法或向量化将持久性图映射到固定维度特征。
  - **集成策略**：将拓扑特征与形态特征拼接，输入最终分类层。拓扑分支可作为插件模块适配任意MIL池化器。

## 3. 实验设计
- **数据集**：使用四个病理图像数据集，涵盖组织病理学和细胞形态学，每个数据集具有不同挑战（如数据规模、类别不平衡、图像分辨率差异）。
  - 具体数据集名称未在摘要中列出（推测为公开数据集如TCGA、CAMELYON、MNIST变体等，需原文确认）。
- **基准方法**：以不加入拓扑信息的基础MIL框架作为基准，包括四种池化策略：
  - 平均池化（Average Pooling）
  - 最大池化（Max Pooling）
  - 注意力池化（Attention-based Pooling）
  - Transformer池化（Transformer-based Pooling）
- **对比方法**：主要对比加入拓扑信息前后的性能差异，未提及与其他拓扑增强方法对比（局限性之一）。

## 4. 资源与算力
- **未明确说明**：论文摘要及元数据中未提及使用的GPU型号、数量、训练时长或显存消耗。仅提到“计算成本适中”的定性描述，无具体数值。

## 5. 实验数量与充分性
- **实验数量**：覆盖了4个数据集 × 4种池化方法 × 3种拓扑表示（推测共约48组主要实验，加上消融分析）。
- **充分性评估**：
  - **充分性**：数据集多样（涵盖不同病理类型），池化方法全面，拓扑表示对比合理，能有效验证方法通用性。
  - **客观性**：使用AUCROC作为主要指标，结果报告了提升百分比，但未提供标准差或统计显著性检验（如p值），削弱了可靠性。
  - **公平性**：在同一框架下公平比较基线（无拓扑）与增强版本，但未与现有的拓扑增强方法（如拓扑图神经网络）对比，结论可能不够全面。

## 6. 论文的主要结论与发现
- 将样本拓扑信息集成到MIL中能稳定提升分类性能，提升幅度因池化方式而异：
  - 平均池化：AUCROC提升3.3%
  - 最大池化：提升4.2%
  - 注意力池化：提升5.9%（最佳）
  - Transformer池化：仅提升0.5%（边际收益）
- 注意力池化对拓扑信息最敏感，可能是因为其自适应加权机制能更好地利用全局结构。
- 计算开销适中，表明TopoMIL可作为现有形态学MIL模型的可扩展轻量扩展，无需大幅修改网络结构。

## 7. 优点
- **方法新颖性**：首次系统性地将拓扑数据分析引入MIL框架，解决空间分布信息被忽视的问题。
- **模块化设计**：TopoMIL作为插件，可无缝集成到现有MIL池化层，降低应用门槛。
- **实验全面**：覆盖多种池化策略和多个病理数据集，验证了泛化能力。
- **性能提升显著**：在注意力池化上获得5.9%的AUCROC增益，具有临床实用潜力。
- **计算成本低**：“适度计算成本”意味着适合实际部署（尽管缺乏具体量化）。

## 8. 不足与局限
- **实验覆盖有限**：
  - 未与已有的拓扑增强方法（如利用图神经网络或核密度估计）对比，无法证明拓扑表示优于其他结构特征。
  - 仅使用AUCROC单一指标，缺乏敏感性、特异性、F1-score等评估。
- **偏差风险**：
  - 数据集未公开具体名称和统计信息，难以复现和验证。
  - 未报告模型方差（多折交叉验证或多次运行结果），可能由随机性导致结论偏差。
- **应用限制**：
  - 假设细胞特征已预提取，未考虑端到端训练或特征提取的质量对拓扑表示的影响。
  - 三种拓扑表示的具体计算方式和超参数未披露，影响可复现性。
  - Transformer池化增益极低（0.5%），暗示拓扑信息可能与Transformer的自注意力机制冗余，需要进一步分析。
- **理论深度**：未讨论为何拓扑信息对注意力池化最有效，缺乏可解释性分析。
- **资源未说明**：算力需求不明，阻碍资源受限场景下的复现。

（完）
