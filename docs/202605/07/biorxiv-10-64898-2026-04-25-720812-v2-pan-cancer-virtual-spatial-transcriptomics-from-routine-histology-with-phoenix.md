---
title: Pan-cancer virtual spatial transcriptomics from routine histology with Phoenix
title_zh: 利用 Phoenix 从常规组织学中实现泛癌虚拟空间转录组学
authors: "Tran, M., Gindra, R. H., Putze, P., Senbai, K., Palla, G., Kos, T., Falcomata, C., Wang, C., Guo, R., Boxberg, M., Berclaz, L. M., Lindner, L. H., Bergmayr, L., Knoesel, T., Jurmeister, P., Klauschen, F., Homicsko, K., Gottardo, R., Eckstein, M., Matek, C., Mock, A., Theis, F. J., Saur, D., Peng, T."
date: 2026-05-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.25.720812v2.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 从常规组织学图像预测基因表达
tldr: 空间转录组学受限于高昂成本和低通量，难以在大规模临床研究中应用。本文提出Phoenix，一种基于潜在流匹配的生成模型，能从常规组织学切片中高精度推断泛癌症单细胞空间基因表达。该模型在头颈癌、乳腺癌、卵巢癌及肉瘤等多种癌症中表现出极强的泛化能力，成功识别了新的空间生物标志物并捕捉到化疗诱导的免疫重塑，为研究组织结构和治疗反应提供了可扩展的虚拟空间转录组学框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的空间转录组技术成本高、速度慢且计算预测方法在跨队列和跨疾病应用时泛化性差。
method: 开发了名为Phoenix的潜在流匹配生成模型，通过常规组织学图像推断具有空间分辨率的单细胞基因表达。
result: Phoenix在多种癌症和物种中实现了高精度预测，识别出新的空间生物标志物，并能准确捕捉免疫重塑和特定突变等位基因。
conclusion: Phoenix建立了一个从常规病理切片进行虚拟空间转录组分析的可靠框架，显著提升了研究组织机理和药物反应的效率。
---

## 摘要
空间转录组学将基因表达与组织架构联系起来，为细胞组织提供了机制性的视角。然而，现有数据集涵盖的供体较少，且忽略了人类疾病的复杂性。实验成本依然高昂，且大规模分析对于群体水平的研究而言速度过慢。迫切需要准确的计算方法。然而，从标准组织学预测基因表达仍是一个悬而未决的问题，因为现有方法在未见过的队列和疾病中迁移效果较差。在此，我们提出了 Phoenix，这是一种潜流匹配（latent flow matching）生成模型，能够高精度地推断泛癌空间分辨率单细胞基因表达。Phoenix 能够进行计算机模拟（in silico）治疗反应分析：应用于 763 名头颈癌患者时，它识别出三种新的空间生物标志物，我们已在两种癌症（乳腺癌，n = 84；卵巢癌，n = 157）和治疗方案（铂类、曲妥珠单抗）中对其进行了验证。Phoenix 的泛化能力超出了癌（carcinomas）：在一个大型肉瘤队列（802 个组织微阵列核心）中，它准确预测了留出样本中的细胞类型特异性特征，并捕捉到了化疗诱导的免疫重塑。Phoenix 还可以跨物种扩展：在小鼠模型中，它在计算机模拟中准确预测了胰腺癌谱系标志物和突变型 mKrasG12D 等位基因的表达。总之，Phoenix 将基于常规组织学的虚拟空间转录组学确立为一个可扩展的框架，用于研究组织结构、治疗反应和疾病机制。

## Abstract
Spatial transcriptomics links gene expression to tissue architecture, providing a mechanistic view of cellular organization. Yet existing datasets cover few donors and miss the complexity of human disease. Experimental costs remain prohibitive, and large-scale profiling is impractically slow for population-level studies. Accurate computational methods are urgently needed. Predicting gene expression from standard histology, however, remains an open problem, as current approaches transfer poorly to unseen cohorts and diseases. Here, we present Phoenix, a latent flow matching generative model that infers pan-cancer spatially resolved single-cell gene expression with high accuracy. Phoenix analyzes treatment response in silico: Applied to 763 head and neck cancer patients, it identified three new spatial biomarkers that we validated across two cancers (breast cancer, n = 84; ovarian cancer, n = 157) and treatment regimens (platinum, trastuzumab). Phoenix generalizes beyond carcinomas: In a large sarcoma cohort (802 tissue microarray cores), it accurately predicted cell-type-specific signatures in held-out samples and captured chemotherapy-induced immune remodeling. Phoenix also extends across species: In a mouse model, it accurately predicted the expression of pancreatic cancer lineage markers and the mutant mKrasG12D allele in silico. Together, Phoenix establishes virtual spatial transcriptomics from routine histology as a scalable framework for studying tissue organization, therapeutic response, and disease mechanisms.

---

## 论文详细总结（自动生成）

这是一份关于论文《Pan-cancer virtual spatial transcriptomics from routine histology with Phoenix》的结构化深入总结：

### 0. 论文的源代码链接
*   **模型代码**：[https://github.com/peng-lab/phoenix](https://github.com/peng-lab/phoenix)
*   **模型权重**：[https://huggingface.co/peng-lab/phoenix](https://huggingface.co/peng-lab/phoenix)
*   **空间处理管线**：[https://github.com/peng-lab/spatialrefinery](https://github.com/peng-lab/spatialrefinery)
*   **组织学处理管线**：[https://github.com/peng-lab/HistoBistro](https://github.com/peng-lab/HistoBistro)

### 1. 论文的核心问题与整体含义
**研究动机**：空间转录组学（ST）虽然能揭示组织微环境，但面临成本极高（每样本数千美元）、耗时长（数天）、样本通量低等瓶颈。现有的通过常规 H&E 染色图像预测基因表达的 AI 方法存在严重缺陷：在未见过的队列、器官或疾病上泛化能力差，且通常只能预测少数高变基因。
**核心问题**：如何构建一个能够跨器官、跨队列、高精度且具备临床应用价值的“虚拟空间转录组”生成模型？

### 2. 论文提出的方法论
Phoenix 是一个端到端的生成式 AI 系统，其核心思想是利用**潜流匹配（Latent Flow Matching, CFM）**技术将组织形态学特征映射到转录组空间。
*   **核心架构**：
    *   **图像编码器**：利用病理基础模型（PFM，如 UNI2-h, Virchow2）将 H&E 图像块编码为紧凑的特征向量。
    *   **自动编码器（AE）**：基于自定义的 MLP-Mixer 设计，将高维基因表达投影到低维潜空间（Latent Space）。
    *   **流模型（Flow Model）**：基于改进的 Transformer 架构，在图像特征的调节下，学习从先验分布到基因潜空间的确定性映射轨迹。
*   **关键技术细节**：
    *   采用线性轨迹的条件流匹配，相比传统的扩散模型，训练更稳定且推理速度更快。
    *   支持单细胞、55μm 和 100μm 三种空间分辨率的预测。
    *   引入 k-NN 平滑处理技术以减少单细胞水平的噪声。

### 3. 实验设计
*   **数据集（The Nest）**：构建了目前最大的高分辨率空间转录组数据集，包含 2220 万个“图像-表达”对，涵盖 16 个器官系统、7 种基因面板。数据源自 Xenium 平台（FFPE 样本），确保了形态学保存完好。
*   **Benchmark 与对比方法**：
    *   在 5 个独立外部验证队列（跨三大洲、多种器官）上进行**零样本（Zero-shot）**评估。
    *   **对比方法**：BLEEP、DeepSpot、GHIST、Linear、SpatialEx。
*   **应用场景**：
    *   乳腺癌分子亚型分类（TCGA 队列）。
    *   结直肠癌进化分析（CNV 变异与侵袭模式）。
    *   头颈癌（HNSCC）放化疗反应预测。
    *   跨物种验证（小鼠胰腺癌模型）。

### 4. 资源与算力
*   **硬件**：在 JURECA 预外算级模块化超级计算机上运行。
*   **GPU**：使用了配备 NVIDIA H100 NVL Tensor Core GPU（96GB 显存）的节点。
*   **时长**：总计超过 **10,000 GPU 小时**。
*   **能耗与碳足迹**：消耗约 6,000 kWh 电力，估计碳排放量为 2.0 吨二氧化碳当量。

### 5. 实验数量与充分性
*   **实验规模**：评估了超过 **10,000 名患者**的数据，这在同类研究中属于史无前例的规模。
*   **充分性**：
    *   **跨队列验证**：严格分离训练集和测试集，确保测试集在机构、扫描仪和供体上完全独立。
    *   **跨谱系/物种**：不仅在癌（Carcinoma）中表现优异，还成功迁移到了肉瘤（Sarcoma）和小鼠模型。
    *   **消融与对比**：对比了多种 SOTA 方法，并在 Spearman 相关性等指标上实现了 35%-173% 的提升。实验设计客观、公平，涵盖了从基础准确性到高级临床终点的全方位验证。

### 6. 论文的主要结论与发现
*   **高精度泛化**：Phoenix 能够“开箱即用”地预测未见过器官的基因表达，并保留了复杂的空间梯度（如 Geary’s C 指标显著优于基准）。
*   **临床生物标志物发现**：在 HNSCC 中识别出 CD8+ T 细胞与成纤维细胞的空间共定位是化疗反应的关键预测因子，并在乳腺癌和卵巢癌中得到了跨癌种验证。
*   **群体规模图谱**：构建了涵盖 9,544 名 TCGA 患者的泛癌空间图谱，揭示了三种保守的肿瘤生态型（EC1-3），并证明其与患者生存显著相关。
*   **机制解析**：能够模拟药物（如贝伐珠单抗、KRAS 抑制剂）诱导的免疫重塑和生态系统变化。

### 7. 优点
*   **规模化**：通过联合缩放数据、模型和算力，解决了 ST 预测的鲁棒性难题。
*   **零样本能力**：无需针对新器官进行微调即可获得可靠结果，极大地降低了应用门槛。
*   **端到端生成**：相比分类或回归模型，流匹配模型能更好地捕捉基因表达的复杂分布。
*   **临床转化潜力**：直接利用存档的 H&E 切片进行虚拟分析，为回顾性临床研究提供了强大的工具。

### 8. 不足与局限
*   **基因面板限制**：受限于 Xenium 初始面板的基因数量（数百个），尚未实现全转录组预测。
*   **平台敏感性**：在 Xenium 5K Prime 数据上泛化效果较差，作者分析认为这主要是由于该平台灵敏度较低导致的，而非模型设计问题。
*   **跨平台验证不足**：尚未在 MERFISH 或 CosMx 等其他原位测序平台上进行广泛测试。
*   **细胞分割依赖**：单细胞水平的预测仍依赖于上游的细胞核分割算法质量。

（完）
