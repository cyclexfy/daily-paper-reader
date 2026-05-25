---
title: "Multi-Scale Tri-Modal Histology Dataset Integrating Tumor Morphology, Immune Patterns, and Clinical Outcomes"
title_zh: 多尺度三模态组织学数据集整合肿瘤形态、免疫模式与临床结果
authors: "Jung, K. J., Qiu, J., Cho, S., McDonough, E., Chadwick, C., Ghose, S., West, R. B., Brooks, J. D., Ginty, F., Machiraju, R., Mallick, P."
date: 2026-05-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.15.725535v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: "多尺度虚拟H&E切片和空间组织图谱用于前列腺癌"
tldr: "针对前列腺癌预后评估需要整合组织形态与免疫环境的需求，本文构建了Prostate-TriMod三模态数据集，包含多尺度虚拟H&E图块、空间细胞图谱（TOPAZ/CAT模型）以及单细胞驱动的文本描述，并配以Grade Groups和生化复发等临床结局。该数据集实现了视觉、空间与文本特征的高保真对齐，为多模态AI模型开发、空间分析和基准研究提供了资源。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有前列腺癌数据缺乏同时集成高分辨率形态、空间免疫信息与临床结局的多模态资源，限制了全面预后评估。
method: "基于Cell DIVE多重成像平台，生成三模态数据：多尺度虚拟H&E图块、TOPAZ和CAT模型识别的空间细胞图谱，以及从单细胞数据导出的文本描述，并关联Grade Groups和BCR状态。"
result: 构建了Prostate-TriMod数据集，实现了视觉特征、空间组织图和文本描述之间的高保真对齐，并包含完整的临床注释。
conclusion: 该数据集为开发结合组织形态与免疫环境的多模态AI预后模型提供了基础，有望推动前列腺癌精准医学中的表示学习、空间分析和基准研究。
---

## 摘要
准确的前列腺癌（PCa）预后评估需要对组织形态（包括细胞结构、腺体结构和组织排列）以及免疫环境进行综合分析。我们提出了Prostate-TriMod，这是一个新颖的三模态组织学数据集，旨在将高分辨率视觉形态与空间组织图谱、免疫浸润模式及临床结果相结合。该数据集基于Cell DIVE多重成像平台生成，包含三个同步的模态：（1）多尺度虚拟H&E切片（224像素、256像素、512像素和2040像素），提供视觉形态背景；（2）空间组织图谱，识别癌/非癌上皮细胞、间质和免疫细胞群体（通过TOPAZ和CAT模型）；（3）基于单细胞数据和模式生成的文本描述。数据集包含全面的临床标注，包括分级组和生化复发（BCR）状态。通过提供视觉特征、空间组织图谱和文本描述之间的高保真对齐，Prostate-TriMod支持先进的多模态AI框架的开发。我们期望该资源能够支持多模态表示学习、空间分析以及将组织学形态和免疫背景与前列腺癌临床结果关联的基准研究中的重用。

## Abstract
Accurate prognostic assessment of prostate cancer (PCa) requires an integrated understanding of tissue morphology-encompassing cell structure, glandular architecture, and tissue organization-and the immune environment. We present Prostate-TriMod, a novel tri-modal histology dataset designed to integrate high-resolution visual morphology with spatial tissue maps, immune infiltration patterns, and clinical outcomes. This dataset, generated from the Cell DIVE multiplexed imaging platform, consists of three synchronized modalities: (1) multiscale virtual H&E tiles (224px, 256px, 512px, and 2040px) providing visual morphological context, (2) spatial tissue maps identifying cancerous/non-cancerous epithelial cells, stroma and immune cell populations (via TOPAZ and CAT models), and (3) text captions generated from single-cell data and patterns. The dataset includes comprehensive clinical annotations, including Grade Groups and biochemical recurrence (BCR) status. By providing high-fidelity alignment between visual features, spatial tissue maps, and textual descriptions, Prostate-TriMod empowers the development of advanced multimodal AI frameworks. We expect this resource to support reuse in multimodal representation learning, spatial analysis, and benchmarking studies that link histology morphology and immune context to clinical outcomes in prostate cancer.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 0. 论文的源代码链接
无。论文未提供任何源代码或数据集下载链接，仅提到数据集可通过作者联系获取（未明确公开）。

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：准确的前列腺癌（PCa）预后评估需要综合理解组织形态（细胞结构、腺体结构、组织排列）和免疫微环境，但现有数据集缺乏同时集成高分辨率形态、空间免疫信息与临床结局的多模态资源。
- **整体含义**：构建一个多尺度、三模态的组织学数据集（Prostate-TriMod），将视觉形态、空间细胞图谱与临床结局（Grade Groups、生化复发BCR）紧密结合，为开发预后AI模型提供基础资源，推动前列腺癌精准医学中的多模态表示学习、空间分析和基准研究。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：基于Cell DIVE多重成像平台，生成三种同步模态的数据，实现高保真对齐。
- **关键技术细节**：
  - **模态1：多尺度虚拟H&E图块**：从原始Cell DIVE图像合成虚拟H&E图像，并裁剪为224px、256px、512px和2040px四种尺度，提供视觉形态上下文。
  - **模态2：空间组织图谱**：使用TOPAZ模型识别细胞边界和形态，CAT模型进行细胞类型分类（癌/非癌上皮、间质、免疫细胞），生成每个图块的空间细胞分布图。
  - **模态3：文本描述**：从单细胞数据和空间模式（如细胞密度、免疫浸润比例、腺体结构）自动生成自然语言描述，如“高密度肿瘤上皮区域，伴有大量CD8+ T细胞浸润”。
  - 所有模态以图块中心对齐，保证像素级对应；临床标注包括Grade Groups和BCR状态（0/1）。

## 3. 实验设计
- **使用的数据集**：仅基于Cell DIVE多重成像平台采集的前列腺癌组织切片，来源未公开具体病例数（文中未明确）。
- **Benchmark**：本文为数据集论文，未进行模型对比或基准测试，仅描述了数据集构建和一致性验证（如模态对齐质量）。
- **对比方法**：无。论文主要提供资源，未与任何现有方法或模型进行比较。

## 4. 资源与算力
- **未明确说明**：文中未提及GPU型号、数量、训练时长等算力信息。仅提到使用Cell DIVE成像平台和临床样本处理，未涉及深度学习训练计算资源。

## 5. 实验数量与充分性
- **实验数量**：论文未报告具体实验组数；仅进行了模态对齐的质量评估（如视觉检查、空间一致性验证），未进行系统性消融或对比实验。
- **充分性与客观性**：作为数据资源论文，其核心贡献在于数据集本身而非方法验证。缺乏量化的评估指标（如对齐误差、分类准确性）和跨数据集验证，实验充分性有限；但数据集构建过程（基于已发表模型TOPAZ/CAT）具有可重复性。

## 6. 论文的主要结论与发现
- 成功构建了Prostate-TriMod三模态数据集，包含多尺度虚拟H&E图块、空间细胞图谱和文本描述，所有模态与临床结局（Grade Groups、BCR）对齐。
- 数据集实现了视觉特征、空间组织图和文本描述之间的高保真对齐，可用于支持多模态AI框架（如视觉-语言模型、空间转录组学分析）。
- 该资源有望促进前列腺癌预后模型中组织形态与免疫环境的联合建模，并作为未来多模态组织学基准。

## 7. 优点
- **多模态对齐创新**：首次将虚拟H&E、空间细胞图谱和文本描述三模态在同一组织切片上实现像素级对齐。
- **多尺度覆盖**：提供224px到2040px不同分辨率图块，适应不同分析需求（局部细胞级到全局结构级）。
- **临床相关性**：包含Grade Groups和BCR状态，直接关联临床预后。
- **可扩展性**：方法可推广至其他多重成像平台和癌症类型。

## 8. 不足与局限
- **缺乏定量验证**：未提供模态对齐的量化指标（如Dice系数、空间一致性误差），仅定性描述。
- **无模型基准**：未利用数据集训练或评估任何现有预后模型，缺少性能参考。
- **样本规模与多样性未知**：未公开病例数、种族/地域分布，可能限制泛化性。
- **文本描述生成细节不足**：未说明基于何种规则或模型生成文本，可重复性存疑。
- **算力依赖未披露**：无法评估构建数据集的成本与可复现性。

（完）
