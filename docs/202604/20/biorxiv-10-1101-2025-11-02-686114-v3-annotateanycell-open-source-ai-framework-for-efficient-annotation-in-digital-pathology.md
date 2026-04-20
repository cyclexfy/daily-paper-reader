---
title: "AnnotateAnyCell: Open-Source AI Framework for Efficient Annotation in Digital Pathology"
title_zh: AnnotateAnyCell：用于数字病理学高效标注的开源人工智能框架
authors: "Verma, S., Malusare, A., Wang, M., Wang, L., Mahapatra, A., English, A. L., Cox, A. D., Broman, M., de Brot, S., Burcham, G., Knapp, D., Dhawan, D., Sola, M., Aggarwal, V., Grama, A., Lanman, N. A."
date: 2026-04-13
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.02.686114v3.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: 用于组织病理学全切片图像高效标注和分类的框架
tldr: "本研究针对病理全切片图像手动标注耗时过长的问题，提出了AnnotateAnyCell开源框架。该框架结合了主动对比学习与人机协作反馈，集成Cellpose分割、UMAP可视化及伪标签传播技术。在犬类尿路上皮癌图像上的实验表明，该方法能将标注时间缩短25%，并在有丝分裂象和核仁识别中达到96%以上的准确率，为高效、精准的病理AI标注提供了新路径。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-11-02-686114-v3/fig-001.webp\", \"caption\": \"Figure 3: Left panel: Displays annotation summary statistics including counts for different morphological features along with distribution histograms. Center panel: Whole slide image view with cyan markers indicating the spatial locations of all annotated cells across the tissue sample, enabling pathologists to assess spatial distribution patterns and tissue architecture context. Right panel: Individual cell inspection tool showing detailed annotations for the selected cell (Tile 2791) with its specific morphological classifications. The interface includes data export functionality (Download CSV), version information, and the ability to filter and visualize cells based on specific morphological criteria. This output interface enables analysis of annotation results and supports research workflows requiring quantitative cellular phenotype data.\", \"page\": 6, \"index\": 1, \"width\": 968, \"height\": 523}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-11-02-686114-v3/fig-002.webp\", \"caption\": \"Figure 4: A. Sequential snapshots of the learned embedding space progression of annotations (green) within the unlabeled cellular population (blue). B. Classification evaluation of mitotic figures, nucleoli, and nuclear shape across training sizes using 5-fold cross-validation. C. Scaling behaviors highlight fundamental differences in data efficiency.\", \"page\": 7, \"index\": 2, \"width\": 951, \"height\": 952}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-11-02-686114-v3/fig-003.webp\", \"caption\": \"Figure 1: Pre-processing stage: Raw H&E-stained tissue images undergo segmentation using Cellpose models to generate nuclear masks. Each detected nucleus is extracted as three complementary representations: raw image patches, isolated nuclear regions, and semantic masks; Active Learning Loop: Expert pathologists (represented by colored figures) provide initial annotations for nuclear morphology features of neoplastic cells, including mitotic figures, vesicular chromatin, and prominent nucleoli. These labeled samples train a contrastive classifier that generates embeddings and pseudolabels for unlabeled data. A convolutional autoencoder processes the multi-modal inputs (raw, isolated, mask) to learn compact latent representations; Output Interface: The system produces annotated whole slide images with nuclei visualization, quantitative feature distributions, and prediction probabilities for downstream analysis. The iterative process refines the model’s understanding of cellular morphologies through expert feedback. Image Preparation: Left: Representative whole-slide image (WSI). Center: Nuclear segmentation results using pretrained Cellpose models. Right: Binary segmentation mask showing all detected valid cells. (Bottom row) Nine examples of 128×128 pixel cellular tiles illustrating morphological diversity across expert-defined annotation categories. Examples include bizarre mitotic figures showing irregular mitotic configurations, canonical mitotic figures demonstrating typical mitotic chromatin condensation patterns, nucleolar variations (single vs. multiple nucleoli) combined with nuclear shape classifications (circular, oval, irregular), and chromatin texture patterns (vesicular chromatin).\", \"page\": 3, \"index\": 3, \"width\": 968, \"height\": 819}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-11-02-686114-v3/fig-004.webp\", \"caption\": \"Figure 5: A. Illustrates labelling time with and without clustering, along with spatial distributions of agreement (green) and disagreement (brown) reveal localized cell-level ambiguities, with disagreement intensity encoded by saturation. B. Presents the annotation workflow metrics like agreement rates, reliability scores, consistency and spatial coverage scores across 11 annotators. C. Illustrates feature correlation demonstrating nuclear features are largely independent dimensions of morphology, and pairwise disagreement analyses showing some users might disagree more than others.\", \"page\": 8, \"index\": 4, \"width\": 964, \"height\": 539}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-11-02-686114-v3/fig-005.webp\", \"caption\": \"Figure 2: Left panel: Displays workflow guide for pathologists, nuclear size distribution histogram, and nuclear-to-cell ratio distribution with red indicators showing the currently selected cell’s measurements. Center panel: Interactive UMAP embedding visualization, where each point represents a cellular tile extracted from the whole slide image. Cells are color-coded based on annotation status (blue: unlabeled, green: labeled, orange: selected) and naturally cluster based on morphological similarities. Right panel: Shows a high-resolution preview of the selected cell tile (Tile 710) with morphological annotation options including mitotic figures, chromatin patterns, nucleoli characteristics, and nuclear shape classifications. The interface includes progress tracking (300/300 labeled points), version control, and model retraining capabilities (\\\"Update Clusters\\\" button).\", \"page\": 5, \"index\": 5, \"width\": 968, \"height\": 523}]"
motivation: 解决组织病理学全切片图像手动标注成本极高且效率低下的瓶颈问题。
method: 提出一种集成细胞分割、潜在空间可视化、对比学习和迭代人工反馈的半监督标注流水线。
result: "标注效率提升了25%，且在仅需少量样本的情况下实现了对有丝分裂象和核仁的高精度分类。"
conclusion: 该框架在保证专家级准确度的同时大幅降低了标注负担，是推动病理AI临床部署的有效工具。
---

## 摘要
组织病理学全切片图像的手动标注仍然是计算病理学和临床人工智能部署的关键瓶颈，在大规模应用时需要耗费极高的专家时间。在此，我们提出一个开源的半监督框架，该框架结合了主动对比学习与迭代的人机回圈（human-in-the-loop）反馈，用于高效的细胞标注和分类。该流程集成了 Cellpose 分割、基于 UMAP 的潜空间可视化以及带有伪标签传播的对比学习，并在 40 倍放大倍率下，针对涵盖低、中、高组织学分级的五张犬类浸润性尿路上皮癌全切片图像进行了评估。潜空间聚类引导的标注耗时 47 分钟，而顺序标注耗时 63 分钟，减少了 25%（95% 置信区间为 18-32%）。使用 1,075 个标记样本，核分裂象的分类准确率达到 96.3% ± 1.2%，核仁的分类准确率达到 98.3% ± 1.4%；其中核仁分类仅使用 215 个样本即可达到 95.5% ± 1.5% 的准确率。标注者间的一致性在染色质（κ = 1.00）和核仁（κ = 0.95）方面较高，但在核分裂象（κ = 0.58）和细胞核形状（κ = 0.36）方面表现一般，反映了这些类别中固有的形态模糊性。该框架在显著减轻标注负担的同时，对定义明确的形态特征实现了专家级的准确度，为资源受限的病理环境下的 AI 辅助诊断提供了一条可扩展的路径。

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWManual annotation of histopathological whole slide images remains a critical bottleneck for computational pathology and clinical AI deployment, requiring prohibitive expert time at scale. Here we present an open-source semi-supervised framework combining active contrastive learning with iterative human-in-the-loop feedback for efficient cellular annotation and classification. The pipeline integrates Cellpose segmentation, UMAP-based latent space visualization, and contrastive learning with pseudolabel propagation, evaluated on five whole slide images of canine invasive urothelial carcinoma across low, intermediate, and high histological grades at 40x magnification. Latent space clustering-guided annotation required 47 minutes compared to 63 minutes for sequential annotation, a 25% reduction (95% CI 18-32%). Classification accuracy reached 96.3% {+/-} 1.2% for mitotic figures and 98.3% {+/-} 1.4% for nucleoli using 1,075 labeled samples, with nucleoli classification achieving 95.5% {+/-} 1.5% accuracy from only 215 samples. Inter-annotator agreement was high for chromatin ({kappa} = 1.00) and nucleoli ({kappa} = 0.95) but moderate for mitotic figures ({kappa} = 0.58) and nuclear shape ({kappa} = 0.36), reflecting intrinsic morphological ambiguity in these categories. This framework substantially reduces annotation burden while achieving expert-level accuracy for well-defined morphological features, providing a scalable path toward AI-assisted diagnostics in resource-constrained pathology settings.

---

## 论文详细总结（自动生成）

### 论文总结：AnnotateAnyCell 开源数字病理高效标注框架

#### 1. 核心问题与研究动机
*   **核心瓶颈**：在数字病理学中，全切片图像（WSI）包含成千上万个细胞，手动标注和分类这些细胞需要耗费病理专家极高的时间成本，成为临床 AI 部署的主要障碍。
*   **现有局限**：目前的深度学习方法多依赖全监督学习，泛化性差且需要大量标注；现有的辅助标注平台往往缺乏直观的交互界面或有效的迭代反馈机制。
*   **研究目标**：开发一个名为 **AnnotateAnyCell** 的开源框架，通过半监督学习和主动学习（Active Learning）显著降低标注负担，同时保持专家级的分类准确度。

#### 2. 方法论
该框架采用了一个四阶段的半监督主动学习流水线：
*   **图像预处理与分割**：利用预训练的 **Cellpose** 模型对 H&E 染色图像进行细胞核分割，提取原始图像块、隔离的细胞核区域和语义掩码三种模态。
*   **潜在空间可视化**：使用 **UMAP** 算法将提取的细胞特征映射到二维嵌入空间，使形态相似的细胞自然聚类，方便病理医生进行批量或针对性标注。
*   **对比学习与伪标签传播**：
    *   采用 **InfoNCE 损失函数**进行对比学习，在特征空间中拉近相似形态、推开异类形态。
    *   通过**类平衡伪标签生成策略**，自动为未标注数据分配高置信度标签，扩大训练集。
*   **多模态自动编码器（VAE）**：集成原始图像、细胞核特征和掩码，通过变分瓶颈学习紧凑的潜在表示，不断迭代更新 UMAP 可视化效果，引导后续标注。

#### 3. 实验设计
*   **数据集**：使用 5 张犬类浸润性尿路上皮癌（IncUC）的全切片图像（40× 放大倍率），该模型是人类肌肉浸润性膀胱癌的重要转化研究模型。
*   **标注类别**：包括核分裂象（典型与非典型）、核仁特征（无、单个、多个、明显）、染色质纹理和细胞核形状。
*   **基准对比（Benchmark）**：
    *   **效率对比**：聚类引导标注 vs. 传统顺序标注。
    *   **性能评估**：通过 5 折交叉验证评估不同标注样本量下的分类准确率。
    *   **一致性分析**：邀请 11 位资深兽医病理学家进行标注，计算 Cohen’s κ 系数。

#### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量及训练总时长。
*   **软件架构**：提到使用了 MongoDB 进行数据管理，前端界面基于 BokehJS 构建，支持多用户并发和异步模型重训。

#### 5. 实验数量与充分性
*   **实验规模**：
    *   11 位病理学家参与，每人标注约 300 个细胞。
    *   针对不同特征（核分裂、核仁、形状）进行了从 200 到 1000+ 样本量的学习曲线分析。
*   **充分性评价**：实验设计较为充分，不仅验证了算法的准确性，还深入探讨了标注者间的一致性（Inter-annotator agreement）和标注效率的提升。然而，由于仅使用了 5 张 WSI 且局限于单一癌症类型，其跨器官、跨物种的泛化性仍有待进一步验证。

#### 6. 主要结论与发现
*   **效率提升**：聚类引导标注将 300 个细胞的标注时间从 63 分钟缩短至 47 分钟，**效率提升 25%**。
*   **高准确率**：使用 1,075 个样本时，核仁分类准确率达 **98.3%**，核分裂象达 **96.3%**。
*   **数据效率**：核仁分类在仅有 215 个标注样本时即可达到 95.5% 的准确率，显示出极强的少样本学习能力。
*   **主观性差异**：染色质和核仁的一致性极高（κ > 0.95），而细胞核形状的一致性较低（κ = 0.36），反映了形态学分类中的固有模糊性。

#### 7. 优点
*   **人机回圈（Human-in-the-loop）**：将病理专家的直觉与 AI 的聚类能力结合，通过 UMAP 空间交互降低了认知负荷。
*   **开源属性**：提供了完整的开源框架，有助于资源受限的实验室快速建立自有的 AI 辅助诊断流程。
*   **多模态融合**：同时利用原始图像和分割掩码，捕捉了更丰富的形态学细节。

#### 8. 不足与局限
*   **数据集局限性**：实验仅基于犬类尿路上皮癌，样本量（5 张 WSI）相对较小，可能无法完全代表复杂多变的临床病理场景。
*   **形状分类瓶颈**：对于细胞核形状等主观性较强的特征，模型准确率（59.5%）仍有较大提升空间。
*   **硬件细节缺失**：缺乏算力消耗和推理延迟的具体数据，不利于其他研究者评估部署成本。
*   **标签噪声风险**：半监督学习中的伪标签可能引入噪声，虽然采用了类平衡策略，但在极端类别不平衡下的鲁棒性需进一步考察。

（完）
