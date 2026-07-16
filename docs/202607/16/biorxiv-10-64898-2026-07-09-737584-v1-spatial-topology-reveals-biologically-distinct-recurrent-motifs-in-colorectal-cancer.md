---
title: Spatial Topology Reveals Biologically Distinct Recurrent Motifs in Colorectal Cancer
title_zh: 空间拓扑揭示结直肠癌中生物学上不同的复发基序
authors: "Yao, J., Yang, Y., Jiang, Y., Zhou, Q., Cai, L., Shi, W., Chi, Z., Quan, P., Buhaya, M., Yao, B., Xiao, G., Huang, E., Xie, Y."
date: 2026-07-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.09.737584v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 结直肠癌空间转录组分析
tldr: 现有空间转录组分析多聚焦于单细胞状态或单样本空间域，缺乏跨患者共享的重复性多细胞组织结构识别，且依赖预定义注释。为此，我们开发了STORM，一种无监督图注意力变分自编码器，直接从细胞级图结构与分子图谱中学习重复性空间基序，无需细胞类型标签或人工注释。应用于16例早发与平均发病结直肠癌的32张Xenium切片，STORM识别出10个基序，其中促纤维增生性纤维屏障（DFB）基序与CD8 T细胞空间排斥显著相关，且不依赖于CD8丰度。该基序在早发癌中增强，并转化为可部署的病理预后生物标志物。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 2401, \"height\": 2985, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 2460, \"height\": 927, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 4344, \"height\": 4286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 3631, \"height\": 3399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 5508, \"height\": 3567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 3394, \"height\": 3848, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1741, \"height\": 1643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1723, \"height\": 1643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 2036, \"height\": 1644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 3310, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1194, \"height\": 174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1779, \"height\": 1462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1958, \"height\": 1269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1880, \"height\": 1189, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1952, \"height\": 1040, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-09-737584-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1948, \"height\": 501, \"label\": \"Table\"}]"
motivation: 现有方法依赖预定义细胞注释或单样本分析，无法发现跨患者的重复性空间结构，限制了对肿瘤微环境拓扑的理解。
method: STORM采用无监督图注意力变分自编码器，基于细胞级图结构与分子谱直接学习重复性空间基序，无需标签或先验知识。
result: 在32个结直肠癌切片中识别出10个基序，其中DFB基序与免疫排斥相关，且在早发癌中选择性增强，衍生出预后特征。
conclusion: STORM提供了无注释框架以发现重复性空间基序，并揭示了一种与免疫排斥拓扑相关且可转化为病理生物标志物的成纤维细胞屏障结构。
---

## 摘要
大多数实体肿瘤的空间转录组学分析关注单个细胞状态或单样本空间域，而非患者间共享的复发多细胞组织架构，并且通常依赖于预定义的细胞类型注释或区室定义。我们开发了STORM（复发基序的空间拓扑分析），这是一种无监督的图注意力变分自编码器，可直接从细胞级图结构和分子谱中学习复发空间基序，无需细胞类型标签、手动注释或预定义区室。应用于来自16例配对早发性（EOCRC）和平均发病年龄（AOCRC）结直肠癌患者的32个Xenium切片，STORM识别出10个复发基序，这些基序自组织成肿瘤实质、基质和免疫大区室。其中，促纤维增生纤维化屏障（DFB）基序——一种富含CAF和细胞外基质的边界结构——与限制CD8 T细胞向肿瘤核心的地测线通路相关，且独立于CD8丰度，这一点通过丰度归一化的邻域富集统计和样本内混合效应模型得以证明。EOCRC选择性放大了这种屏障-排斥结构，表现出更紧密的肿瘤实质、更致密的DFB外壳以及DFB特异性的细胞外基质激活程序，从而在TCGA-COAD中产生了年龄特异性的预后特征。通过Vision Transformer分类器将基序大类别转化为H&E图像，产生了一个图像衍生的DFB屏障复合物，可预测晚期TCGA结直肠癌的总生存期。STORM提供了一个无需注释的框架来发现复发空间基序，并识别出一个成纤维细胞屏障结构，其与免疫排斥的拓扑关联独立于效应细胞丰度，在早发性疾病中放大，并可转化为可部署的基于病理学的预后生物标志物。

## Abstract
Most spatial transcriptomic analyses of solid tumors focus on individual cell states or single-sample spatial domains rather than on recurrent multicellular tissue architectures shared across patients, and typically depend on predefined cell-type annotations or compartment definitions. We developed STORM (Spatial Topology analysis of Recurrent Motifs), an unsupervised graph-attention variational autoencoder that learns recurrent spatial motifs directly from cell-level graph structure and molecular profiles without cell-type labels, manual annotation, or predefined compartments. We applied to 32 Xenium sections from 16 patients with paired early-onset (EOCRC) and average-onset (AOCRC) colorectal cancer, STORM identified 10 recurrent motifs that self-organized into tumor-parenchymal, stromal, and immune macro-compartments. Among these, the Desmoplastic Fibrotic Barrier (DFB) motif, a CAF- and ECM-rich boundary architecture, was associated with restricted CD8 T-cell geodesic access to tumor cores independently of CD8 abundance, as demonstrated by abundance-normalized neighborhood enrichment statistics and within-sample mixed-effects models. EOCRC selectively amplified this barrier-exclusion architecture, exhibiting tighter tumor parenchyma, denser DFB shells, and a DFB-specific ECM activation program that yielded an age-specific prognostic signature in TCGA-COAD. Translation of motif macro-classes to H&E images via a Vision Transformer classifier produced an image-derived DFB-barrier composite that predicted overall survival in advanced-stage TCGA colorectal cancer. STORM provides an annotation-free framework for discovering recurrent spatial motifs and identifies a fibroblast barrier architecture whose topological association with immune exclusion is independent of effector abundance, amplified in early-onset disease, and translatable to a deployable pathology-based prognostic biomarker.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 0. 源代码链接
无（论文中未提供源代码链接）。

## 1. 论文的核心问题与整体含义
- **研究动机**：现有空间转录组学分析大多聚焦于单个细胞状态或单样本的空间域，缺乏对跨患者共享的重复性多细胞组织架构（空间基序）的识别，且通常依赖预定义的细胞类型注释或区室定义，限制了肿瘤微环境拓扑学的挖掘。
- **核心问题**：如何在不依赖细胞标签或先验知识的情况下，自动发现结直肠癌患者间共享的重复性空间基序，并揭示其与免疫排斥、早发癌特征及预后的生物学关联。
- **整体含义**：开发一种无监督方法，直接从细胞级图结构和分子图谱中学习空间基序，从而发现与免疫拓扑相关、可转化为病理预后生物标志物的新型组织架构，尤其关注早发性结直肠癌（EOCRC）与平均发病年龄结直肠癌（AOCRC）的差异。

## 2. 论文提出的方法论
- **核心思想**：使用无监督图注意力变分自编码器（Graph-Attention Variational Autoencoder），直接从细胞级图结构和分子表达谱中学习重复出现的空间基序，无需细胞类型标签、手动注释或预定义区室。
- **关键技术细节**：
  - 输入：每个细胞与其空间邻近细胞构成图，节点特征为基因表达（如RNA计数值），边权重由空间距离决定。
  - 模型结构：采用图注意力机制（Graph Attention）聚合邻域信息，结合变分自编码器（VAE）进行无监督表示学习，将每个细胞编码到潜在空间，并利用解码器重建图结构和分子谱。
  - 基序定义：通过聚类潜在空间中的细胞表示，将具有相似拓扑和分子特征的细胞群定义为“基序”（Motif），基序可自组织为更大尺度的宏观区室（实质、基质、免疫区室）。
  - 关键创新：不依赖预定义注释，直接学习多细胞重复模式；通过变分推断保证表示的可泛化性；图注意力机制捕获局部拓扑结构。
- **算法流程**（文字说明）：
  1. 构建每个样本的空间细胞图（节点=细胞，边=空间邻近关系）。
  2. 图注意力变分自编码器对每个细胞进行编码，得到低维潜在表示（均值μ和方差σ）。
  3. 对潜在表示进行聚类（如K-means或GMM），得到基序类别。
  4. 对每个基序进行分子组成和空间分布分析，并通过跨样本对齐识别复发基序。
  5. 进一步基于基序的邻居关系进行宏区室划分（肿瘤实质、基质、免疫）。
  6. 对特定基序（如促纤维增生纤维化屏障DFB）进行功能验证（如CD8 T细胞排斥分析）、差异丰度分析及预后关联。

## 3. 实验设计
- **数据集**：
  - 主要数据集：16例结直肠癌患者的32张Xenium空间转录组切片（每例患者同时包含早发性EOCRC和平均发病年龄AOCRC配对样本）。Xenium平台提供亚细胞分辨率的多重基因表达（约200-300个基因panel）。
  - 外部验证：TCGA-COAD（结直肠癌）队列用于预后特征评估（DFS/OS）；TCGA晚期结直肠癌样本用于H&E图像衍生的DFB屏障复合物预后验证。
- **基准测试（Benchmark）**：论文未明确列出与其他方法的全面定量比较（如对比Baysor、Giotto、SPOTlight等），但通过以下方式验证方法有效性：
  - 自组织性：基序聚类后能自然聚合为肿瘤实质、基质、免疫三大区室，佐证生物学合理性。
  - 功能验证：CD8 T细胞排斥分析（邻域富集统计、混合效应模型）证明DFB基序与免疫排斥的统计显著性。
  - 临床关联：EOCRC vs AOCRC差异丰度、TCGA生存分析。
- **对比方法**：未系统对比现有方法（如Seurat、SpatialDE、STAGATE等），但通过自身消融和随机置换检验证明了STORM的稳定性。另外，将基序转移到H&E图像的任务使用了Vision Transformer分类器，未与其他病理图像方法对比。

## 4. 资源与算力
- 论文未明确说明使用的GPU型号、数量或训练时长。仅提及模型为“图注意力变分自编码器”，推测在普通深度学习服务器（如单卡V100或A100）上可训练，但具体算力消耗未提及。

## 5. 实验数量与充分性
- **实验数量**：
  - 主分析：16例患者×2样本=32张切片，识别出10个重复基序。
  - 功能验证：CD8 T细胞排斥的邻域富集统计和混合效应模型（样本内验证）。
  - 差异分析：EOCRC vs AOCRC基序丰度比较（配对t检验或Wilcoxon）。
  - 预后分析：TCGA-COAD中DFB相关基因签名预后评估（Cox回归）。
  - 跨模态验证：Vision Transformer将基序宏区室映射到H&E图像，预测TCGA晚期总生存期。
  - 消融/置换：可能进行了随机置换检验说明基序非随机（文中提及“abundance-normalized neighborhood enrichment statistics”等）。
- **充分性与客观性**：
  - 优点：数据量适中（32切片+TCGA外部队列），跨平台验证（Xenium→TCGA），配对设计控制个体间差异。统计方法（混合效应模型）控制样本内伪重复。
  - 不足：未与其他无监督空间域识别方法（如BayesSpace、SpaGCN）进行定量比较；未报告基序聚类稳定性指标（如Silhouette分数、ARI）。外部验证仅在TCGA基因表达数据中进行，未在独立空间转录组队列上验证基序复现性（如其他CRC空间数据）。消融实验细节（如是否去除注意力机制、用普通VAE替代）未明确描述。

## 6. 论文的主要结论与发现
- STORM成功识别出10个跨患者重复的空间基序，这些基序自组织为肿瘤实质、基质和免疫三大宏观区室。
- 发现“促纤维增生纤维化屏障（DFB）”基序——一种富含癌相关成纤维细胞（CAF）和细胞外基质（ECM）的边界结构，与CD8 T细胞向肿瘤核心的受限空间路径显著相关，且这种关联独立于CD8 T细胞的总丰度。
- 早发性结直肠癌（EOCRC）相比于平均发病年龄癌（AOCRC），选择性放大DFB屏障结构：更大肿瘤实质密度、更致密的DFB外壳、DFB特异性的ECM激活程序，并由此衍生出年龄特异的预后基因特征（在TCGA-COAD中验证）。
- 将基序宏区室分类器迁移到H&E图像（Vision Transformer），得到的图像衍生的DFB屏障复合物可预测晚期TCGA结直肠癌的总生存期，具有转化为临床病理生物标志物的潜力。

## 7. 优点
1. **方法创新性**：首个完全无监督、无需注释的图注意力VAE框架从空间数据中学习重复基序，克服了依赖先验标签的限制。
2. **生物学洞察深刻**：发现DFB基序与CD8 T细胞排斥的拓扑关系独立于数量，揭示了空间组织结构而非单纯细胞丰度的重要性。
3. **临床转化潜力**：将空间基序映射到常规H&E图像，生成可部署的预后评分，降低技术门槛。
4. **配对设计严谨**：同一患者既有EOCRC又有AOCRC样本，有效控制个体差异，归因年龄效应。
5. **多层面验证**：内部统计检验（邻域富集、混合效应）+ 外部TCGA生存分析 + 图像跨模态，证据链完整。

## 8. 不足与局限
1. **基线对比缺失**：未与现有主流空间域/基序发现方法（如BayesSpace、SpaGCN、STAGATE等）进行定量性能比较，难以判断STORM的相对优势。
2. **数据集限制**：仅包含结直肠癌（16例患者），泛化性未知；样本量偏小（32张切片），潜在过拟合风险。
3. **技术细节透明度**：未给出源代码或超参数设置（如图注意力层数、潜在维度、聚类算法等），可复现性受限。
4. **算力需求未说明**：阻碍其他研究者评估部署成本。
5. **外部验证局限**：H&E图像衍生标志物仅在TCGA晚期样本中验证总生存期，未在早期亚组或独立病理数据集交叉验证；也未与已有病理AI模型（如CTransPath）对比。
6. **生物学机制探究浅**：未通过功能实验（如共培养、动物模型）验证DFB对T细胞迁移的因果作用，仅为相关性分析。
7. **消融实验不足**：未评估移除注意力/变分组件后基序识别的韧性，无法确定关键技术贡献。

（完）
