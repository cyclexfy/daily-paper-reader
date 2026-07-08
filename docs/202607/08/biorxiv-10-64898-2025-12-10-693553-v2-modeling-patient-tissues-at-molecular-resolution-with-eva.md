---
title: Modeling patient tissues at molecular resolution with Eva
title_zh: 通过Eva以分子分辨率建模患者组织
authors: "Liu, Y., Sharma, R., Bieniosek, M., Kang, A., Wu, E., Chou, P., Li, I., Rahim, M., Bauer, E., Ji, R., Duan, W., Qian, L., Luo, R., Sharma, P., Dhanasekaran, R., Schürch, C. M., Charville, G., Mayer, A., Zou, J., Trevino, A. E., Wu, Z."
date: 2026-07-08
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.10.693553v2.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 提出Eva，一个用于组织影像数据的基础模型，基于视觉Transformer并在空间蛋白质组学和病理图像上预训练
tldr: 组织分子结构与功能及疾病密切相关，但空间蛋白组学数据难以直接提取洞见。Eva作为基础模型，采用视觉Transformer架构，通过掩码重建预训练学习多尺度空间表示。它在跨模态推理、质量控制、零样本检索和生存建模等任务中表现优异，验证了嵌入的通用性。该模型有望桥接基础研究与临床实践，加速转化科学。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有空间多模态组织数据整合分析困难，缺乏统一模型提取结构与分子关系以支持疾病诊断和治疗。
method: 提出Eva模型，使用新型视觉Transformer架构，在匹配的空间蛋白组学和组织病理学图像上进行掩码重建预训练。
result: Eva在跨模态推理、质量控制、数据标注、零样本检索、生存建模和患者分层等多个任务中表现优异。
conclusion: Eva作为通用基础模型，能够桥接基础研究与临床实践，有望加速转化医学发展。
---

## 摘要
组织结构对所有器官的功能和稳态至关重要，结构破坏通常指示疾病。建模组织结构、分子和临床方面之间的关系可能推动新的诊断和治疗策略。尽管空间蛋白质组学等分析技术能够捕捉这些关系，但从数据中提取洞察仍具挑战。在此，我们提出Eva，一个组织成像数据的基础模型，可在分子、细胞和样本水平学习组织的多尺度空间表征。Eva采用新颖的视觉变换器架构，并在匹配的空间蛋白质组学和组织病理学图像的掩码重建上进行预训练。我们展示了Eva在多种任务上的优异表现，包括跨模态推理、质量控制、数据标注、零样本检索、生存建模和患者分层。在保留验证数据上的广泛评估证明了学习嵌入的通用性和泛化能力。我们预期Eva将通过连接基础研究和临床实践来加速转化科学。

## Abstract
Tissue structure is essential to function and homeostasis in all organs, and disruptions to structure usually indicate disease. Modeling relationships between structural, molecular, and clinical aspects of tissues could advance new diagnostics and treatment strategies. Although profiling techniques like spatial proteomics can capture these relationships, the data remain challenging to extract insight from. Here, we present Eva, a foundation model for tissue imaging data that learns multi-scale spatial representations of tissues at the molecular, cellular, and sample level. Eva uses a novel vision transformer architecture and is pre-trained on masked reconstruction of matched spatial proteomics and histopathology images. We show that Eva excels at a variety of tasks, including cross-modal inference, quality control, data annotation, zero-shot retrieval, survival modeling, and patient stratification. Extensive evaluations on held-out validation data demonstrate the versatility and generalizability of the learned embeddings. We anticipate that Eva will accelerate translational science by bridging basic research and clinical practice.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 0. 论文的源代码链接
- **无**（文中注明了代码和模型权重将开源，但未提供具体链接，仅给出了预发布平台：https://github.com/YAndrewL/Eva 和 https://huggingface.co/yandrewl/Eva，但这些链接在论文截稿时可能尚未生效或为占位符）

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：组织结构与功能及疾病密切相关，但空间蛋白质组学等组织成像数据维度高、异质性强，难以直接提取可解释的生物学和临床信息。现有分析缺乏能够统一表征分子、细胞和组织层面信息的基础模型。
- **研究动机**：构建一个通用视觉基础模型，能够学习多尺度空间表示，将分子成像、形态学特征与患者临床结局关联起来，从而加速转化科学，桥接基础研究与临床实践。
- **整体含义**：提出 Eva（Encoder of visual atlas），一种针对多重组织成像数据的新型基础模型，通过大规模自监督预训练，在多种下游任务（跨模态推理、质量控制、细胞标注、微环境分类、生存分析等）上均取得领先性能，展示了通用表征的潜力。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：采用分层两级变换器架构（Two-stage transformer），结合轻量级通道编码器和令牌级掩码自编码器（Masked Autoencoder, MAE），从大规模配准的空间蛋白质组学（MIF）和H&E组织病理图像中学习跨通道和空间关系。
- **关键技术细节**：
  - **输入处理**：将MIF图像裁剪为224×224像素的非重叠图像块，每个块包含C+3个通道（C个MIF蛋白通道 + 3个H&E通道）。所有像素值归一化到0-1范围，H&E反相处理以匹配荧光图像风格。
  - **通道编码器（Channel-level Encoder）**：对每个图像块，先将其划分为8×8的非重叠令牌（token）。采用通道无关的方式，通过共享卷积核独立处理每个单通道令牌。同时引入基于GenePT的语言模型嵌入表示各生物标志物（蛋白/基因描述）的先验知识，替代传统的位置编码或ESM嵌入。每个多通道令牌内通过多头注意力融合通道间信息，输出聚合令牌（aggregation token）作为压缩表示。
  - **令牌级掩码自编码器（Token-level MAE）**：将通道编码器输出的聚合令牌嵌入与可学习的正弦位置编码相加，通过标准视觉变换器（ViT-base）编码器捕捉空间关系。解码器则从压缩表示重建原始像素，仅计算掩码位置的MSE损失。
  - **掩码策略**：训练时采用随机掩码（单通道令牌级随机遮盖），掩码比例0.75。推理时支持令牌掩码（整位置所有通道遮盖）、通道掩码（整通道遮盖）、H&E掩码或MIF掩码等，灵活适应不同任务。
  - **预训练过程**：在总共约110万张图像块（含4160万单通道块）上训练20个epoch，batch size为16，学习率从1e-4经余弦退火至1e-5。每批次固定最大通道数22，不足则零填充并使用通道掩码。
  - **下游任务嵌入使用**：对于图像块，取平均所有令牌嵌入作为块级表示；对于组织区域，采用门控多头注意力多实例学习（MIL）聚合块级嵌入成区域级嵌入，用于临床预测。

## 3. 实验设计：数据集、benchmark与对比方法
- **数据集**：
  - **训练集**：4159个组织区域，涵盖多种器官、表型（96%癌症）、平台（CODEX/Phenocycler 24%，Phenocycler Fusion 64%，MIBI 1%，IMC 11%），约64M细胞，66%区域有配准的H&E。
  - **验证集**：超过8000个区域（71%在预训练中未见），包含12个不同来源验证数据集（如Stanford-GC, UPMC-HNC, MDACC-HCC, EM-PCA等），覆盖不同癌症类型、平台和标注类型（细胞类型、微环境、临床标签等）。
- **Benchmark任务**：
  1. **图像重建**：随机掩码、令牌掩码、通道掩码下的像素级重建，对比VirTues。
  2. **跨模态翻译**：H&E→MIF预测，对比ROSIE和GigaTIME。
  3. **质量控制**：NIQE分数预测、伪影检测、生物标志物染色质量评估，线性探测。
  4. **细胞类型分类**：12个数据集，单细胞图像（32×32）线性探测，对比VirTues和KRONOS；零样本/少样本转移实验（Stanford-GC→UKT-GEJ）。
  5. **微环境分类与细胞组成预测**：UPMC-HNC和MDACC-HCC上的微环境分类；12个数据集上的细胞组成回归。
  6. **图像块检索**：零样本检索，按余弦相似度检索邻居，评估Top-1/3/5准确性。
  7. **癌症类型/亚型分类**：9种癌症（2500区域），肺癌亚型（ADC/SCC/SCLC），线性探测+5折交叉验证。
  8. **生存分析**：UPMC-HNC和EM-PCA-CRC，Cox比例风险模型，计算C-index和Kaplan-Meier曲线。
  9. **患者分层与病例检索**：多项二分类任务（HPV、炎症、预后、免疫治疗响应），线性探测+5折CV；零样本病例检索。
- **对比方法**：VirTues（IMC数据上MAE训练）、KRONOS（DINOv2训练）、ROSIE（ConvNext）、GigaTIME（UNet++）、UNI（H&E基础模型）、Prov-GigaPath（H&E基础模型）。对比时使用各自官方发布权重和推荐嵌入提取方式。

## 4. 资源与算力
- **预训练**：8×141GB NVIDIA H200 GPUs，训练20个epoch（论文未写明具体耗时，但提及在8块H200上完成）。
- **下游实验**：在单块24GB NVIDIA RTX 4090 GPU上运行。
- **说明**：论文明确报告了GPU型号和数量，但并未给出训练总时长（小时/天）。对于参数规模，Eva的令牌级编码器为ViT-base，通道编码器为轻量级。

## 5. 实验数量与充分性
- **实验数量**：覆盖三大类（细胞/组织级、临床级）共9大类任务，每类任务在多个数据集上执行（例如细胞类型分类在12个数据集上；患者分层在6个数据集上；消融实验包括细胞掩码与框掩码比较、零样本/少样本迁移、多分辨率评估、多模态融合等）。
- **充分性与公平性**：
  - 对比方法均使用官方权重和标准协议，线性探测统一设置（学习率1e-4，20 epoch，AdamW），确保公平。
  - 评估指标多样（AUC, F1, PCC, Spearman, C-index, SSIM, MSE等），适合各任务特性。
  - 验证集高度分离（71%区域在预训练中未见），并包含不同平台、不同疾病、不同标注来源的数据，增强了泛化能力评估的可信度。
  - 但也有局限性：大部分数据来自CODEX/Phenocycler平台，IMC/MIBI数据较少，可能引入平台偏见。

## 6. 论文的主要结论与发现
- Eva在图像重建、跨模态预测、质量控制、细胞分类、微环境分类、细胞组成预测、癌症分类、生存分析和患者分层等几乎所有任务上，均一致优于现有空间蛋白质组学基础模型（VirTues, KRONOS）以及专用翻译模型（ROSIE, GigaTIME）。
- 在H&E→MIF翻译任务中，Eva显著超越ROSIE和GigaTIME，且能预测更多蛋白标记物。
- 在零样本和少样本标签转移场景中，Eva保持性能优势，展示了良好的跨数据集泛化能力。
- 将Eva嵌入与现有H&E基础模型（UNI, Prov-GigaPath）进行晚期融合，可在生存分析和患者分层上进一步提升性能，表明Eva与形态学模型具有互补性。
- Eva的自注意力权重能够反映生物学上合理的组织结构（如肿瘤区域和间质区域），说明其学到了具有生物学意义的特征。

## 7. 优点
- **创新架构**：两级编码器（通道级+空间级）灵活处理任意通道组合，并利用语言模型嵌入提供生物标记物先验知识，克服了固定通道数的限制。
- **大规模预训练**：基于4000+区域、64M细胞、约200种蛋白质标志物，覆盖多种癌症和组织，数据规模和多样性超越此前工作。
- **广泛且系统的评测**：涵盖从分子到患者的四个尺度（像素、细胞、邻域、区域），设计9类任务，使用独立验证集和多种对比方法，评估全面、可靠。
- **实用性强**：质量控制、自动细胞标注、跨数据集零样本迁移等任务直接服务于真实分析流程，具有临床转化潜力。
- **易于集成**：可与H&E基础模型联合使用，增强现有病理AI系统的分子感知能力。

## 8. 不足与局限
- **数据分布偏倚**：训练和验证数据以CODEX/Phenocycler平台为主（约88%），IMC和MIBI仅占12%，可能限制模型对新平台或实验条件的泛化，作者也承认这一局限。
- **标签偏差**：下游任务中的细胞类型、微环境、质量等标注均由人类专家完成，可能存在主观差异或错误，文中提到使用了多个来源的标注以缓解，但缺乏标准金标准数据。
- **预训练任务单一**：仅使用掩码重建目标，未原生包含跨模态生成（如H&E→MIF）任务，导致需要单独微调才能实现最佳翻译性能。
- **可解释性不足**：虽然注意力图显示与生物结构相符，但如何从嵌入中系统提取驱动患者结局的分子或细胞机制仍待解决。
- **资源与复现性**：代码和模型权重虽声明公开，但训练数据中部分为私有（如Enable Medicine平台内部数据），可能影响完全复现。另外训练资源需求较高（8×H200），小团队复现困难。

（完）
