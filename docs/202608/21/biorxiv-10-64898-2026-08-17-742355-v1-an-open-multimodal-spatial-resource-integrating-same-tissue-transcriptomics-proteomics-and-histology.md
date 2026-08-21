---
title: "An open multimodal spatial resource integrating same-tissue transcriptomics, proteomics, and histology"
title_zh: 一个整合同一组织转录组学、蛋白质组学和组织学的开放多模态空间资源
authors: "Duchini, E., Tsao, C., Madore, J., Ashhurst, T. M., De Almeida Silva, J., Shin, J.-S., Gupta, R., McCaughan, G., Palendira, U., Liu, K., Ferguson, A., Marsh-Wakefield, F."
date: 2026-08-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.17.742355v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 同一组织切片上整合转录组、蛋白质组和组织学的公开多模态空间资源
tldr: "空间多组学整合面临同一切片多模态数据难以获取的挑战。本文提出在福尔马林固定石蜡包埋组织上依次进行Xenium空间转录组、COMET循环免疫荧光和H&E染色的工作流，实现转录本、蛋白和形态共定位。在扁桃体、肝细胞腺瘤和肝细胞癌等多种组织中验证，并公开对齐的多模态数据和单细胞整合结果，同时发布UnumLocalia可视化工具，为多模态空间生物学提供可复用资源。"
source: biorxiv
selection_source: fresh_fetch
motivation: 空间转录组与蛋白组整合困难，缺乏公开的多模态数据集，限制计算方法发展。
method: "同一FFPE切片依次进行Xenium、COMET和H&E染色，图像配准后利用Xenium分割生成单细胞多模态数据。"
result: 在多种人类组织上成功实现多模态整合，公开对齐数据和整合单细胞矩阵，并发布UnumLocalia工具。
conclusion: 该流程与资源支持多模态空间生物学研究，推动整合算法开发和验证。
---

## 摘要
空间转录组学和蛋白质组学技术为组织构成、细胞表型和功能提供了互补的见解，但在同一组织切片上整合这些模态仍具有技术挑战性。顺序工作流程必须保持RNA完整性、抗原性和组织形态，同时保持准确的空间配准。目前，适合计算方法开发的公开可用的多模态数据集仍然有限。在这里，我们展示了一种工作流程，可在同一福尔马林固定石蜡包埋组织切片上依次进行10x Genomics Xenium空间转录组学、COMET循环免疫荧光以及苏木精-伊红（H&E）组织学染色。我们在多种生物学上不同的人体组织中展示了该方法，包括扁桃体、肝细胞腺瘤以及配对肿瘤和非肿瘤肝细胞癌，说明了该工作流程在单一组织类型之外的广泛适用性。在图像配准之后，将Xenium衍生的细胞分割应用于蛋白质图像，以生成整合的单细胞转录组和蛋白质组测量结果，用于下游分析。为了促进社区复用，我们公开发布了四个具有代表性的对齐组织芯块，连同转录本坐标、多重蛋白质图像、H&E图像、细胞分割和整合的单细胞数据集。我们还介绍了UnumLocalia，这是一个开源的可视化和数据提取工具，能够交互式探索对齐的多模态图像，支持用户自定义细胞分割，并允许导出整合的单细胞数据用于下游分析。总之，这一技术方案、工作流程、软件和公开可用的数据集为多模态空间生物学提供了可复用的资源，支持生物发现、计算方法开发、多模态数据整合以及跨互补空间技术的新兴分析方法的验证。

## Abstract
Spatial transcriptomic and proteomic technologies provide complementary insights into tissue organisation, cellular phenotype and function, yet integrating these modalities on the same tissue section remains technically challenging. Sequential workflows must preserve RNA integrity, antigenicity and tissue morphology while maintaining accurate spatial registration. At present, publicly available multimodal datasets suitable for computational method development remain limited. Here, we present a workflow for sequential 10x Genomics Xenium spatial transcriptomics, COMET cyclic immunofluorescence, and haematoxylin and eosin (H&E) histological staining on the same formalin-fixed paraffin-embedded tissue section. We demonstrate this approach across multiple biologically distinct human tissues, including tonsil, hepatocellular adenoma, and matched tumour and non-tumour hepatocellular carcinoma, illustrating the widespread applicability of the workflow beyond a single tissue type. Following image registration, Xenium-derived cell segmentations were applied to protein images to generate integrated single-cell transcriptomic and proteomic measurements for downstream analyses. To facilitate community reuse, we publicly release four representative aligned tissue cores together with transcript coordinates, multiplex protein images, H&E images, cell segmentations, and integrated single-cell datasets. We additionally introduce UnumLocalia, an open-source visualisation and data extraction tool that enables interactive exploration of aligned multimodal images, supports user-defined cell segmentation, and allows export of integrated single-cell data for downstream analyses. Together, this technical protocol, workflow, software, and openly available dataset provide a reusable resource for multimodal spatial biology, supporting advances in biological discovery, computational method development, multimodal data integration, and validation of emerging analytical approaches across complementary spatial technologies.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 0. 源代码链接

**无。** 论文中介绍了开源可视化工具 UnumLocalia，但提取的文本中未提供具体的代码仓库链接（如 GitHub 或软件官网地址）。

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：空间转录组学和空间蛋白质组学技术分别提供组织构成、细胞表型和功能的互补视角，但**在同一组织切片上整合这些多模态数据**在技术上极具挑战性。
- **关键难点**：
  - 顺序工作流必须同时保存 RNA 完整性、蛋白质抗原性和组织形态结构；
  - 各模态图像之间需要保持**准确的空间配准**；
  - 目前公开可用的、适合计算方法开发的多模态空间数据集非常有限，制约了多模态整合算法的发展与验证。
- **整体含义**：作者试图建立一个从实验流程到数据发布的完整解决方案，为多模态空间生物学研究提供可复用的公共资源，从而推动生物发现、算法开发和跨技术验证。

## 2. 论文提出的方法论

- **核心思想**：在同一张福尔马林固定石蜡包埋（FFPE）组织切片上，按顺序完成三种模态的成像，并通过图像配准和统一细胞分割，生成整合的单细胞多模态数据。
- **关键技术流程**：
  1. **Xenium 空间转录组学**（10x Genomics）—— 首先在 FFPE 切片上进行原位转录本检测；
  2. **COMET 循环免疫荧光（Cyclic Immunofluorescence）** —— 在同一张切片上随后进行多重蛋白标记成像；
  3. **H&E 组织学染色** —— 最后进行常规组织病理染色，保留形态学信息；
  4. **图像配准** —— 将三种模态的图像对齐到同一空间坐标系；
  5. **统一细胞分割** —— 将 Xenium 衍生的细胞分割结果**直接应用于蛋白质图像**，从而为每个细胞同时提取转录组和蛋白质组测量值，形成整合的单细胞数据集。
- **算法/公式说明**：论文中未涉及具体数学公式，核心方法为实验流程编排 + 图像配准 + 已有分割算法的跨模态迁移应用。

## 3. 实验设计

- **数据集/场景**：
  - 人类**扁桃体**组织；
  - 人类**肝细胞腺瘤**（hepatocellular adenoma）；
  - 配对的人**肝细胞癌（HCC）肿瘤及癌旁非肿瘤组织**。
- **Benchmark**：论文并未建立与替代实验方案（如分别染色后整合、或在连续切片上整合）的直接比较基准，而是以多组织类型的可行性演示为主。
- **对比方法**：未与其他技术工作流进行系统性比较。

## 4. 资源与算力

- 文中**未明确说明**所使用的计算资源，包括 GPU 型号、数量、训练时长或图像配准的计算耗时。
- 分析过程涉及图像配准、细胞分割和数据处理，但具体算力需求未知。

## 5. 实验数量与充分性

- **实验组数**：在 4 种代表性组织芯块（四种不同组织类型，含配对 HCC 肿瘤/非肿瘤）上进行了验证；
- **无消融实验**：未涉及参数消融、配准算法选择对比等消融分析；
- **充分性评价**：
  - **优点**：覆盖了多种生物学上截然不同的人体组织，展示了工作流超越单一组织类型的广泛适用性；
  - **不足**：样本量相对有限（4 个组织芯块），且缺少与替代技术路线的定量比较指标（如配准精度、数据质量评分等），因此在严格意义上验证的全面性和客观公平性仍有提升空间。

## 6. 论文的主要结论与发现

- 提出了一个**在单张 FFPE 切片上依次执行 Xenium → COMET → H&E** 的可复现工作流，能够同时保留 RNA、蛋白质和形态信息，并实现准确的空间对齐。
- 该工作流在多种人类组织（扁桃体、肝细胞腺瘤、HCC 肿瘤与非肿瘤组织）中均成功运行，证明了其广泛适用性。
- 通过将 Xenium 的细胞分割直接迁移到蛋白图像，成功生成了**整合的单细胞转录组 + 蛋白质组数据**。
- 公开发布了对齐的组织芯块数据（转录本坐标、多重蛋白图像、H&E 图像、细胞分割、整合单细胞数据），并提出 **UnumLocalia** 开源工具，支持交互式多模态图像探索、自定义细胞分割和整合数据导出。
- 总体而言，该研究为多模态空间生物学社区提供了实验方案 + 软件 + 数据的完整可复用资源。

## 7. 优点

- **真正的同一切片多模态整合**：不同于连续切片或跨样本整合方案，本工作流避免了组织异质性带来的批次干扰，数据对齐具有天然的空间一致性。
- **组织类型的多样性验证**：覆盖淋巴组织（扁桃体）和肝脏病变组织（腺瘤、肿瘤及癌旁），增强了工作流的可信度和通用性。
- **数据完全开放**：公开原始数据、中间数据和整合后的单细胞矩阵，为计算方法开发提供了宝贵的 benchmark 数据资资源。
- **工具开源与可交互**：UnumLocalia 支持用户自定义分割和导出，降低了社区使用门槛。
- **技术链条完整**：从湿实验、配准、分割到可视化和数据发布，形成了闭环解决方案。

## 8. 不足与局限

- **算力与资源信息缺失**：未报告实际计算成本，不利于他人评估方法可复制性。
- **缺乏定量评估指标**：没有报告配准误差、RNA/蛋白信号保留率、细胞分割准确率等关键定量指标。
- **对比实验不足**：未与其他多模态整合方案进行系统比较，难以衡量本方案的相对优劣。
- **样本规模有限**：仅 4 个代表性组织芯块，统计功效有限；对于不同组织类型、不同疾病状态的普适性仍需更大规模验证。
- **组织选择偏差风险**：所选组织均为可获取的常见临床样本，但未涉及复杂组织结构（如脑、肿瘤微环境多样化程度高的组织）的验证。
- **分割策略依赖性**：完全依赖 Xenium 分割迁移到蛋白图像，对于 Xenium 分割失败的区域，蛋白数据质量可能受到连带影响，论文未讨论这一潜在偏差。

（完）
