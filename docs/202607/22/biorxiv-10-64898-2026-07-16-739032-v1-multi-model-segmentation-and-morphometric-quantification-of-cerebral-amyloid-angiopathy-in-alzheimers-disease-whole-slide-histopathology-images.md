---
title: "Multi-model Segmentation and Morphometric Quantification of Cerebral Amyloid Angiopathy in Alzheimer's Disease Whole Slide Histopathology Images"
title_zh: 阿尔茨海默病全切片组织病理学图像中脑淀粉样血管病的多模型分割与形态计量量化
authors: "Tahmasebidehkordi, H., Bahramy, A., Julian, D. R., Cohen, J. A., Neal, M., Bumgardner, C., Nelson, P. T., Pearce, T. M., Kofler, J."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.16.739032v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 阿尔茨海默病全切片组织病理图像分割与定量分析
tldr: "脑淀粉样血管病(CAA)的现有神经病理评估多依赖半定量分级，缺乏血管级分辨率和可扩展性。本文提出一种基于深度学习的全切片图像分析框架，通过比较U-Net、DA-ResUNet和Swin-UNet三种分割架构，选择DA-ResUNet实现血管壁、淀粉样沉积等结构的分割与形态定量。内部验证Dice>90%，外部验证泛化稳健，能够提取血管形态、淀粉样负荷及环周受累特征，为CAA的规模化定量研究提供了可解释的解决方案。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 11461, \"height\": 6753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 3885, \"height\": 3973, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 3701, \"height\": 3974, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 5495, \"height\": 5902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 6479, \"height\": 2267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 4316, \"height\": 4285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 5266, \"height\": 1790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 5406, \"height\": 1468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 2369, \"height\": 1741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 3963, \"height\": 6443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 5244, \"height\": 3550, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1795, \"height\": 900, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1798, \"height\": 529, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1797, \"height\": 694, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1801, \"height\": 721, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1794, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1788, \"height\": 969, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1790, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1789, \"height\": 678, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 7684, \"height\": 6043, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739032-v1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 7541, \"height\": 5954, \"label\": \"Table\"}]"
motivation: 现有CAA病理评估缺乏血管级定量分析，亟需可扩展的全切片图像自动分割方法。
method: 比较U-Net、DA-ResUNet、Swin-UNet三种架构，基于DA-ResUNet生成全切片分割掩码并提取血管形态与淀粉样特征。
result: "内部队列所有模型Dice>90%，DA-ResUNet平衡精度与效率；外部验证注意力模型优于标准U-Net，管道有效检测血管。"
conclusion: 该框架支持血管级CAA定量分析，可扩展至其他脑血管病理，促进临床与遗传研究整合。
---

## 摘要
引言：脑淀粉样血管病（CAA）以皮质和软脑膜血管中β-淀粉样蛋白沉积为特征，与认知障碍和出血相关。当前的神经病理学评估依赖于半定量分级，缺乏血管级别的分辨率和可扩展性。现有的计算病理学方法也无法捕捉全切片图像（WSI）中个体血管形态和淀粉样蛋白的空间分布。为填补这一空白，我们开发了一个用于CAA可重复定量分析的深度学习框架。方法：我们分析了来自匹兹堡大学阿尔茨海默病研究中心的10例阿尔茨海默病病理个体的20个死后脑组织切片（额叶皮层n=10，枕叶皮层n=10），作为内部开发队列。独立外部队列包括来自肯塔基大学阿尔茨海默病研究中心的5例个体的10个切片（5个额叶和5个枕叶样本）。我们训练并比较了三种语义分割架构：标准U-Net、双注意力残差U-Net（DA-ResUNet）和基于Swin Transformer的U-Net（Swin-UNet），使用内部开发队列进行切片水平五折交叉验证。所有模型在独立外部队列上评估，以测试域迁移下的泛化能力。基于分割性能和计算效率，我们选择一种架构生成全切片复合分割掩膜，用于血管壁、淀粉样蛋白沉积和组织分区。这些掩膜随后用于确定性血管检测、形态测量以及通过后处理分析量化血管和血管周围淀粉样蛋白特征。结果：所有三种架构在内部队列上均实现了高分割准确率，血管壁、淀粉样蛋白沉积、灰质和软脑膜的Dice得分均超过90%。Swin-UNet在血管分割上表现略优，而DA-ResUNet在准确率和计算效率上更均衡，被选用于下游分析。外部队列评估显示鲁棒的泛化能力，注意力增强模型在域迁移下优于标准U-Net。使用所选模型，该流程可靠地检测有效血管，排除非血管伪影，并能确定性提取血管形态测量、血管和血管周围淀粉样蛋白负荷，以及在血管水平识别环状CAA受累。讨论：该框架为血管级别CAA分析提供了可扩展、可解释的解决方案，支持脑血管病理的稳健几何和空间表征，并促进未来与临床和遗传学研究的整合。除CAA外，模块化设计允许扩展到全切片图像中的其他血管病理，包括小动脉硬化，从而促进脑血管疾病机制的更广泛研究。

## Abstract
Introduction: Cerebral amyloid angiopathy (CAA) is characterized by amyloid-beta deposition in cortical and leptomeningeal vessels and associated with cognitive impairment and hemorrhage. Current neuropathological assessments rely on semiquantitative grading and lack vessel-level resolution and scalability. Existing computational pathology approaches also fail to capture individual vessel morphology and spatial amyloid distribution across whole-slide images (WSIs). To address this gap, we developed a deep learning framework for reproducible, quantitative analysis of CAA in WSIs. Methods: We analyzed 20 postmortem brain tissue sections from the frontal (n = 10) and occipital cortices (n = 10) of 10 individuals with Alzheimer's disease pathology obtained from the University of Pittsburgh Alzheimer's Disease Research Center, which served as the internal development cohort. An independent external cohort consisted of 10 sections (5 frontal and 5 occipital samples) from 5 individuals obtained from the University of Kentucky Alzheimer's Disease Research Center. We trained and compared three semantic segmentation architectures, a standard U-Net, a dual-attention residual U-Net (DA-ResUNet), and a Swin Transformer-based U-Net (Swin-UNet), using the internal development cohort with slide-level five-fold cross-validation. All models were evaluated on the independent external cohort to assess generalization under domain shift. Based on segmentation performance and computational efficiency, we selected one architecture to generate whole-slide composite segmentation masks for vessel walls, amyloid deposits, and tissue compartments. These masks were subsequently used for deterministic vessel detection, morphometric measurements, and quantification of vascular and perivascular amyloid features through post-processing analysis. Results: All three architectures achieved high segmentation accuracy on the internal cohort, with Dice scores above 90% across vessel walls, amyloid deposits, gray matter, and leptomeninges. The Swin-UNet showed marginally higher performance for vessel segmentation, whereas the DA-ResUNet provided more balanced accuracy and computational efficiency and was selected for downstream analysis. External cohort evaluation demonstrated robust generalization, with attention-enhanced models outperforming the standard U-Net under domain shift. Using the selected model, the pipeline reliably detected valid vessels, excluded non-vascular artifacts, and enabled deterministic extraction of vessel morphometry, vascular and perivascular amyloid burden, and identification of circumferential CAA involvement at the vessel level. Discussion: This framework provides a scalable, interpretable solution for vessel-level CAA analysis, supporting robust geometric and spatial characterization of cerebrovascular pathology and enabling future integration with clinical and genetic studies. Beyond CAA, the modular design allows extension to other vascular pathologies, including arteriolosclerosis, in WSIs, facilitating broader investigation of cerebrovascular disease mechanisms

---

## 论文详细总结（自动生成）

### 0. 论文的源代码链接
无（文中未提供公开源代码链接）。

### 1. 论文的核心问题与整体含义
- **研究动机**：脑淀粉样血管病（CAA）是阿尔茨海默病（AD）常见的血管病理，但当前神经病理评估依赖半定量分级（如Vonsattel、Olichney评分），缺乏血管级别的分辨率和可扩展性，无法捕捉个体血管形态、淀粉样蛋白（Aβ）空间分布及血管间异质性。
- **核心问题**：开发一种自动化、可重复、可扩展的深度学习（DL）框架，对全切片图像（WSI）中CAA进行血管级别的定量分析，包括血管壁、Aβ沉积、组织分区（灰质、软脑膜）的分割，以及血管形态测量、血管/血管周围Aβ负荷量化、环状受累识别。
- **整体含义**：提供一种超越传统半定量分级的可量化工具，为CAA的规模化研究、临床相关性分析及与其他脑血管病理（如小动脉硬化）的通用分析奠定基础。

### 2. 论文提出的方法论
- **核心思想**：采用**多模型融合策略**（每个目标独立训练二值分割模型）避免多类分割的类别不平衡问题；在分割后通过**确定性几何后处理**（连通组件、轮廓分析、径向与切线-法线采样）提取血管级形态与Aβ特征。
- **关键技术细节**：
  - **分割架构比较**：标准U-Net、双注意力残差U-Net（DA-ResUNet）、Swin Transformer U-Net（Swin-UNet）。均为U-Net风格编码器-解码器结构。
    - DA-ResUNet：使用残差块、卷积块注意模块（CBAM，含通道注意力和空间注意力）、上采样采用双线性插值+1×1卷积。
    - Swin-UNet：基于Swin Transformer V2的层级编码器，集成卷积预激活残差块，使用窗口/移位窗口自注意力，解码器含残差卷积块和跳跃连接。
  - **训练策略**：每个目标独立训练二值模型；损失函数为**二元交叉熵（BCE）+ Tversky损失**（平衡假阳/假阴）；优化器AdamW，余弦退火调度；数据增强包括几何变换（翻转）和染色/扫描变异模拟；使用**混合精度训练**加速。
  - **多分辨率推理**：血管壁和Aβ在40×分辨率下分割（细节保留），灰质和软脑膜在10×分辨率下分割（大区域高效）。采用滑动窗口（2048×2048，步幅1024）和测试时增强（TTA）。
  - **复合掩膜构建**：各模型预测通过位运算融合为复合映射（灰质、软脑膜、血管壁、Aβ，重叠区域标记为Aβ阳性血管）。
  - **血管实例提取**：基于连通组件和轮廓层次，要求内腔轮廓完全被外壁轮廓包络，最小管腔面积20 μm²，排除碎片化血管。
  - **形态测量**：两种互补方法：
    - **径向采样**：从管腔质心向120个均匀角度发射射线，计算内外直径、径向壁厚、内-外径比、圆形度（基于径向距离变异）。
    - **切线-法线采样**：在管腔边界点沿法线方向测量壁厚，适用于非圆形或变形管腔。
  - **Aβ量化**：血管壁内Aβ像素占比（血管Aβ负荷）、血管周围环形区域（固定外扩75 μm）内Aβ密度、根据角度覆盖（>50%为环状受累）分类。
- **公式/算法流程**（文字描述）：
  - 损失函数：L_total = L_BCE + L_Tversky，其中L_BCE为像素级交叉熵，L_Tversky = 1 - (sum(yi·ŷi)) / (sum(yi·ŷi) + α·sum(yi·(1-ŷi)) + β·sum((1-yi)·ŷi))，α,β控制假阴/假阳惩罚。
  - 圆形度 = 1 / (1 + σ_r / r̄)，r̄为平均径向距离，σ_r为标准差。
  - 血管检测基于轮廓层次：内腔轮廓完全在外壁轮廓内部（使用OpenCV findContours）。

### 3. 实验设计
- **数据集**：
  - **内部开发队列**：匹兹堡大学ADRC，10例AD个体，每例额叶和枕叶各1张切片（共20张WSI）。组织厚度5 μm，Aβ免疫组化（NAB228抗体，Nova Red，苏木素复染），Aperio AT2 40×扫描。
  - **外部测试队列**：肯塔基大学ADRC，5例AD个体，每例额叶和枕叶各1张切片（共10张WSI）。组织厚度8 μm，同样NAB228抗体，不同染色流程（DAB色原），同一型号扫描仪。
- **划分**：内部队列用于训练和五折交叉验证（按WSI划分，防止数据泄漏）；外部队列完全独立，用于测试泛化能力。
- **标注**：单个标注者在神经病理学家监督下手工生成像素级二值掩膜（血管壁、Aβ、灰质、软脑膜）。
- **对比方法**：
  - **标准U-Net**（基线）
  - **DA-ResUNet**（提出的CNN+注意力）
  - **Swin-UNet**（提出的Transformer）
  - 均在同一内部分裂、相同数据增强、超参数下训练150轮，使用相同损失函数和优化器。
- **评价指标**：Dice系数、召回率、精确率。内部报告均值±SD（五折），外部报告单次结果。
- **下游验证**：定性展示血管检测、形态测量、Aβ负荷及环状受累，并比较额叶与枕叶的CAA差异（枕叶更严重，符合生物学知识）。

### 4. 资源与算力
- **GPU**：单张NVIDIA A100（40GB显存）。
- **训练时长**：未明确说明具体小时数，但提到DA-ResUNet处理一张典型WSI（约80,000×80,000像素）需4-5分钟，Swin-UNet需8-10分钟（约2倍）。
- **其他**：使用混合精度训练加速；计算环境基于PyTorch 2.9.0、CUDA 12.8。

### 5. 实验数量与充分性
- **实验组数**：
  - 三类架构 × 四个分割目标 = 12个模型，每个都经过五折交叉验证（共60个训练-验证实验）。
  - 外部测试：在10张WSI上各抽取约500 tile/目标进行评估。
  - 消融方面：未显式进行消融研究（如移除CBAM、残差、Tversky损失等）。但通过比较三种架构间接展示了不同组件的影响。
- **充分性判断**：
  - **优点**：内部交叉验证设计合理（WSI级划分），外部独立队列验证泛化，覆盖多种染色变异。使用多个评价指标（Dice、召回率、精确率）。下游分析了血管检测与定量特征，并验证了与已知生物学趋势一致（枕叶更严重）。
  - **不足**：样本量较小（内部10例/20 WSI，外部5例/10 WSI）；未进行消融实验以量化各模块贡献；超参数选择（如Tversky损失α,β）未报告具体值或敏感性分析；缺乏与其他CAA量化方法的直接比较（除DL架构外）；未报告统计显著性检验（如是否显著优于U-Net）。实验设计整体充分但可进一步强化。

### 6. 论文的主要结论与发现
- 所有三种分割架构在内部队列上均达到Dice>90%，其中Swin-UNet在血管分割上略优（Dice 91.6%），DA-ResUNet在效率与精度平衡上最佳，被选为下游管道。
- 在外部域迁移下，注意力增强模型（DA-ResUNet、Swin-UNet）优于标准U-Net，显示出更好的泛化能力，尤其是灰质分割（U-Net仅80.34%，DA-ResUNet达91.79%）。
- 基于DA-ResUNet的完整管道能够可靠检测血管（基于封闭管腔几何约束），排除非血管伪影，并确定性提取血管形态（内径、外径、壁厚、圆形度）、血管Aβ负荷、血管周围Aβ密度及环状受累分类。
- 初步验证显示枕叶皮层比额叶皮层具有更高的血管Aβ负荷、更多环状受累血管及更多Aβ阳性毛细血管，与已知CAA分布一致。
- 该框架为模块化设计，可扩展至其他血管病理（如小动脉硬化）。

### 7. 优点
- **方法论亮点**：
  - 采用独立二值模型融合策略，有效缓解多类分割中的类别不平衡问题，并允许对每个目标单独调整损失权重（如Aβ模型强惩罚假阳，血管模型强惩罚假阴）。
  - 结合径向采样和切线-法线采样两种互补几何测量方法，适应不同血管形状。
  - 复合掩膜直接用于下游测量，无需原始图像，提高可解释性和重现性。
  - 多分辨率推理平衡了效率与细节。
- **实验设计亮点**：
  - 严格的WSI级交叉验证防止数据泄漏。
  - 包含独立外部队列，评估域迁移下的泛化能力，并展示了注意力机制的优势。
  - 定量与定性结合，并验证了生物合理性（枕叶CAA更严重）。

### 8. 不足与局限
- **样本量有限**：内部仅10例AD个体，外部5例，可能无法覆盖CAA的全部表型变异（如不同严重程度、共存病理）。统计功效不足。
- **未进行消融实验**：无法定量评估各组件（CBAM、残差、Tversky损失、TTA等）的贡献。
- **超参数报告不完整**：Tversky损失的α,β值未给出，学习率调度参数未详述，可重复性受影响。
- **缺乏与其他CAA量化方法的直接比较**：未与Perosa等（2021）的基于区域的深度学习方法进行对比，也未与传统半定量评分进行关联分析。
- **血管检测偏向特异性**：严格几何规则（封闭管腔、最小面积20 μm²）导致部分有效血管被排除（如分叉、相邻血管、轻微断裂），降低敏感性。
- **仅针对Aβ免疫组化染色**：未验证对其他染色（如H&E、刚果红）的适用性；未进行交叉倍率验证（40×与10×混合）。
- **血管周围Aβ量化采用固定半径（75 μm）**，可能不适用于扩大血管周围间隙或异质性分布。
- **外部泛化仍有局限**：两机构使用相同抗体和扫描仪型号，染色流程有差异但相似；更极端的染差异可能仍会降低性能。
- **无公开代码或预训练模型**，限制可重复性和后续应用。

（完）
