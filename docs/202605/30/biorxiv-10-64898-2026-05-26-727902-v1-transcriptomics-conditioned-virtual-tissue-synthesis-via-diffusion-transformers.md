---
title: Transcriptomics-Conditioned Virtual Tissue Synthesis via Diffusion Transformers
title_zh: 通过扩散变换器实现转录组条件化的虚拟组织合成
authors: "Vlachas, P., Nonchev, K., Koelzer, V., Ratsch, G."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.727902v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: "使用扩散变压器根据转录组谱生成H&E病理图像"
tldr: "空间转录组学将H&E组织形态与基因表达关联，但生成组织图像的方法稀缺。STMDiT是一种扩散变换器，通过自适应层归一化和跨注意力模块，以形态嵌入和转录组谱为条件合成组织病理图像。在黑色素瘤数据上，基因表达条件化显著提升图像质量（FID从330.7降至252.9）和转录组保真度（AUC从0.229升至0.267）。利用预测转录组伪标签可零样本迁移到外分布数据集，实现虚拟组织合成，支持计算病理学中的假设检验。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有生成模型缺乏利用转录组谱合成组织图像的能力，限制了虚拟组织模拟和假设检验。
method: 基于扩散变换器，采用自适应层归一化和逐块交叉注意力融合基因表达，并引入独立模态丢弃的双分类器自由引导。
result: 在10x TuPro黑色素瘤上，基因条件化将FID从330.7降至252.9，AUC从0.229升至0.267；伪标签方法零样本迁移到TCGA SKCM，FID提升57点。
conclusion: 基因表达条件化可生成形态不同的组织图像，并支持超出原生空间转录组覆盖范围的虚拟组织合成。
---

## 摘要
空间转录组学将苏木精-伊红（H&E）组织形态与空间分辨的基因表达（GE）相结合。然而，利用这种耦合从转录组图谱合成组织图像的生成模型仍然稀缺。我们提出了STMDiT（空间转录组学与形态学扩散变换器），这是一种扩散变换器，能够在形态学嵌入和转录组图谱的共同条件下合成H&E组织病理学切片。基于PixCell（Yellapragada等，2025），我们通过自适应层归一化和逐块交叉注意力整合来自冻结的CancerFoundation编码器（Theus等，2024）的基因表达，并在双无分类器引导下使用独立模态丢弃进行训练。在10x TuPro Visium黑色素瘤队列上，GE条件化相比无GE的PixCell-B基线提高了图像质量（最佳FID为252.9 vs 330.7）和转录组保真度（最佳AUC为0.267 vs 0.229，达到真实切片上限的82%）。使用DeepSpot预测转录组伪标签（PTPL）进行训练，独特地实现了零样本迁移至TCGA SKCM，这是一个分布外（OOD）仅含H&E的黑色素瘤队列：PTPL-XAttn-PMA-B达到FID=690.0，比无GE基线（747.1）提高了57点，模型内GE消融效应为ΔOOD=+309.5，从而实现了超越原生空间转录组覆盖范围的虚拟组织合成。我们的结果表明，基因表达条件化能够产生形态上独特的组织图像，并支持用于计算病理学假设检验的虚拟组织模拟。代码可用性：https://github.com/ratschlab/stmdit

## Abstract
Spatial transcriptomics couples hematoxylin and eosin (H&E) tissue morphology with spatially resolved gene expression (GE). However, generative models that exploit this coupling to synthesize tissue images from transcriptomic profiles remain scarce. We present STMDiT (Spatial Transcriptomics and Morphology Diffusion Transformer), a diffusion transformer that synthesizes H&E histopathology patches conditioned jointly on morphological embeddings and transcriptomic profiles. Building on PixCell (Yellapragada et al., 2025), we integrate gene expression from a frozen CancerFoundation encoder (Theus et al., 2024) through adaptive layer normalization and per-block cross-attention, and we train under dual classifier-free guidance with independent modality dropout. On the 10x TuPro Visium melanoma cohort, GE conditioning improves both image quality over the no-GE PixCell-B baseline (best FID = 252.9 vs 330.7) and transcriptomic fidelity (best AUC = 0.267 vs 0.229, reaching 82% of the real-tile ceiling). Training with DeepSpot's predicted-transcriptomics pseudo-labels (PTPL) uniquely transfers zero-shot to TCGA SKCM, an out-of-distribution (OOD) H&E-only melanoma cohort: PTPL-XAttn-PMA-B reaches FID = 690.0, a 57-point improvement over the no-GE baseline (747.1), with a within-model GE-ablation effect of {Delta}OOD = +309.5, enabling virtual tissue synthesis beyond native spatial-transcriptomics coverage. Our results indicate that gene-expression conditioning produces morphologically distinct tissue images and supports virtual tissue simulation for hypothesis testing in computational pathology. Code availability: https://github.com/ratschlab/stmdit

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 0. 论文的源代码链接
- 论文中明确提供了代码仓库：[https://github.com/ratschlab/stmdit](https://github.com/ratschlab/stmdit)

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：空间转录组学技术能够同时测量组织切片的H&E形态学图像和空间分辨的基因表达（GE），但现有生成模型缺乏利用转录组谱（基因表达数据）来合成组织病理图像的能力，限制了虚拟组织模拟、假设检验以及跨平台数据整合的应用。
- **核心问题**：如何设计一个生成模型，能够以形态学嵌入和转录组图谱为条件，生成逼真的H&E组织病理图像，并使模型具备泛化到仅有H&E图像的外部分布（OOD）数据集的能力。
- **整体含义**：该工作尝试弥合分子图谱与组织形态之间的鸿沟，为计算病理学提供一种新的虚拟组织合成工具，支持基于基因表达假设的形态学验证。

## 2. 论文提出的方法论：核心思想、关键技术细节
### 核心思想
- 提出 **STMDiT（Spatial Transcriptomics and Morphology Diffusion Transformer）**，一个扩散变换器（Diffusion Transformer）模型，在形态学嵌入和转录组图谱共同条件下合成H&E病理切片小块。

### 关键技术细节
- **基础架构**：基于PixCell（Yellapragada et al., 2025）的扩散变换器框架，并引入两种条件融合机制：
  - **自适应层归一化（Adaptive Layer Normalization）**：将基因表达特征注入到网络各层的归一化参数中。
  - **逐块交叉注意力（Per-block Cross-Attention）**：在扩散变换器的每一块中，通过交叉注意力模块融合来自冻结的CancerFoundation编码器（Theus et al., 2024）的基因表达特征。
- **条件化训练**：使用**双无分类器引导（Dual Classifier-Free Guidance）**，训练时独立地对形态和转录组模态进行随机丢弃（Independent Modality Dropout），从而在推理时灵活控制不同模态的引导强度。
- **零样本迁移策略**：利用DeepSpot模型预测的转录组伪标签（Predicted Transcriptomics Pseudo-Labels, PTPL）进行训练，使得模型能够零样本迁移到仅含H&E的外部分布数据集（如TCGA SKCM），无需重新训练。

### 算法流程（文字说明）
1. 输入：目标转录组谱（来自空间转录组学或预测伪标签）和形态学嵌入（可选）。
2. 使用CancerFoundation编码器提取基因表达特征。
3. 扩散前向过程：逐步向干净图像添加噪声生成噪声图像。
4. 逆向过程：STMDiT以噪声图像、扩散时间步、形态嵌入和基因表达特征为输入，通过自适应层归一化和交叉注意力融合条件，预测噪声。
5. 训练时采用双无分类器引导：随机丢弃形态或转录组条件，学习无条件与条件预测的联合分布。
6. 推理时通过调节条件权重，生成与给定转录组条件匹配的组织图像。

## 3. 实验设计
- **使用的数据集**：
  - **10x TuPro Visium 黑色素瘤队列**：原始空间转录组数据集，包含H&E图像和真实转录组数据。
  - **TCGA SKCM**：仅含H&E图像的黑色素瘤队列，作为外部分布（OOD）测试集。
- **基准（Benchmark）**：
  - 对比方法：无基因表达条件化的PixCell-B基线（no-GE baseline）。
  - 评估指标：
    - 图像质量：FID（Fréchet Inception Distance）。
    - 转录组保真度：AUC（Area Under the Curve，可能基于预测的转录组与实际表达的相关性）。
- **对比方法**：主要对比自身无GE条件的基线以及不同的条件融合变体（如XAttn、PMA等）。未提及与其他SOTA生成模型的全面比较。

## 4. 资源与算力
- 论文摘要及元数据中**未明确提及**使用的GPU型号、数量、训练时长等算力信息。仅提供了模型名称和代码链接，但无具体硬件细节。

## 5. 实验数量与充分性
- 实验数量：主要报道了两组实验：
  1. **内部数据集实验**（10x TuPro）：对比有/无GE条件的FID和AUC，并报告了最佳FID 252.9 vs 330.7，AUC 0.267 vs 0.229（达到真实切片上限的82%）。
  2. **零样本迁移实验**（TCGA SKCM）：使用PTPL训练后迁移到OOD数据，FID达690.0（比无GE基线747.1提升57点），并给出了模型内GE消融效应ΔOOD=+309.5。
- **充分性评估**：
  - **优点**：展示了内部和外部数据集上的性能，验证了零样本迁移能力，消融实验（有无GE条件）清晰。
  - **不足**：实验仅局限于黑色素瘤单一癌种，缺少其他癌种或组织类型的验证；对比方法单一（仅基线），未与主流病理图像生成模型（如GAN、其他扩散模型）比较；未提供详细的统计分析或置信区间。

## 6. 论文的主要结论与发现
1. 基因表达条件化能够显著提升生成图像的质量（FID从330.7降至252.9）和转录组保真度（AUC从0.229升至0.267），证明转录组信息对形态合成有指导作用。
2. 使用预测转录组伪标签（PTPL）训练，模型可以零样本迁移到仅有H&E的外部分布数据集，实现超越原生空间转录组覆盖范围的虚拟组织合成。
3. 基因表达条件化能够产生形态上不同的组织图像，支持计算病理学中的假设检验（例如：改变特定基因表达谱，观察组织形态变化）。

## 7. 优点
- **创新性**：首次将扩散变换器应用于转录组条件化的组织图像合成，突破现有生成模型仅基于图像或病理标签的局限。
- **方法设计**：采用自适应层归一化和逐块交叉注意力融合多模态信息，并通过双无分类器引导实现模态可控生成，设计精巧。
- **零样本泛化能力**：利用伪标签策略实现到OOD数据集的迁移，极具实用价值，降低了空间转录组数据的稀缺性限制。
- **开源代码**：提供完整代码，可复现性强。
- **定量指标充分**：同时评估了图像质量（FID）和分子保真度（AUC），评估维度合理。

## 8. 不足与局限
- **实验覆盖有限**：仅探究了黑色素瘤一种癌种，缺乏泛化到其他组织类型（如乳腺癌、结直肠癌）的验证。
- **对比方法不足**：未与多种病理生成模型（如Stable Diffusion、GAN等）进行全面比较，无法判断相对性能地位。
- **OOD迁移细节缺失**：对TCGA SKCM的零样本迁移效果虽有所提升，但FID=690仍较高（远高于内部数据的252.9），表明OOD生成质量仍不理想，且未明确说明伪标签的生成质量或对迁移的影响。
- **资源算力未报告**：缺少训练和推理所需的硬件及时间信息，不利于其他研究者复现或评估可行性。
- **潜在偏差风险**：训练数据仅来源于Visium平台，可能引入平台特异性偏差；伪标签预测本身可能存在误差，进而影响条件生成效果。
- **应用限制**：当前模型生成的是组织小块（patch），而非完整全切片图像；对于假设检验需要精确基因变化对应形态变化的能力尚未通过生物验证（如扰动实验）。

（完）
