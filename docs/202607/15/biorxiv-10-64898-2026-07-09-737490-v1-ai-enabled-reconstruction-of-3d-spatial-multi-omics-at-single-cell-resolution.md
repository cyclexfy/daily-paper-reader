---
title: AI-enabled reconstruction of 3D spatial multi-omics at single-cell resolution
title_zh: 基于人工智能的单细胞分辨率三维空间多组学重构
authors: "Wang, Z., Yan, Y., Yang, X., Zhang, D., Han, C., Zou, Q., Du, Y., Hu, Z., Yuan, Z."
date: 2026-07-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.09.737490v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 整合组织学图像和多组学数据进行3D空间重建，多模态学习
tldr: "3D空间多组学技术稀缺，难以实现单细胞分辨率。Histo3D-MO整合稀疏空间测量与H&E染色，通过SPONGE模型预测多组学，重构单细胞3D图谱。在肝癌数据中，揭示翻译效率空间模式、恶性细胞与单核细胞体积解耦及深度相关分化轨迹。可扩展的方法为复杂组织单细胞分辨率3D多组学研究提供新工具。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737490-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 2109, \"height\": 2642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737490-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 2143, \"height\": 1432, \"label\": \"Figure\"}]"
motivation: 3D空间多组学提供独特生物学视角，但现有技术无法在单细胞分辨率下实现多组学重构。
method: "Histo3D-MO结合稀疏空间组学测量与H&E染色图像，利用SPONGE模型预测多组学，重构单细胞分辨率3D空间图谱。"
result: 在肝癌数据中，成功揭示翻译效率空间异质性、恶性细胞与单核细胞解耦以及深度依赖的单核细胞分化轨迹。
conclusion: Histo3D-MO为单细胞分辨率3D空间多组学重构提供可扩展框架，助力肿瘤微环境等复杂系统研究。
---

## 摘要
三维（3D）空间多组学为生物活动提供了无与伦比的见解，但在技术上仍然难以实现。在此，我们介绍了Histo3D-MO，一个用于重构单细胞分辨率3D空间多组学图谱的混合实验-计算流程。值得注意的是，Histo3D-MO通过基于H&E图像的空间多组学（SPONGE），将稀疏的、组学不相交的空间测量与密集的苏木精和伊红（H&E）组织学相结合，实现了跨多个组学层的细胞级3D映射。使用保留切片的验证表明，SPONGE明显优于现有的组学预测方法。我们进一步开发了一套用于3D细胞类型传播和组织域注释的算法，实现了肿瘤微环境的全容积表征。应用于内部肝细胞癌数据时，Histo3D-MO揭示了翻译效率的空间组织模式、恶性细胞与单核细胞之间的体积解耦，以及与深度相关的单核细胞分化轨迹。总之，这些结果确立了Histo3D-MO作为一个可扩展的框架，用于重构单细胞分辨率的3D空间多组学，并在复杂生物系统中探究组织组织。

## Abstract
Three-dimensional (3D) spatial multi-omics provides unparalleled insights into biological activities, yet remains technically prohibitive. Here, we introduce Histo3D-MO, a hybrid experimental-computational pipeline for reconstructing single-cell-resolution 3D spatial multi-omics maps. Notably, Histo3D-MO integrates sparse, omics-disjoint spatial measurements with dense Hematoxylin and Eosin (H&E) histology through SPatial multi-Omics from h&E imaGEs (SPONGE), achieving cell-level 3D mapping across multiple omics layers. Validated using held-out slices, SPONGE substantially outperforms existing omics prediction methods. We further developed an algorithmic suite for 3D cell-type propagation and tissue-domain annotation, enabling whole-volume characterization of the tumor microenvironment. Applied to the in-house hepatocellular carcinoma data, Histo3D-MO revealed spatially organized patterns of translation efficiency, volumetric decoupling between malignant cells and monocytes, and depth-associated monocyte differentiation trajectories. Together, these results establish Histo3D-MO as a scalable framework for reconstructing single-cell-resolution 3D spatial multi-omics and interrogating tissue organization across complex biological systems.

---

## 论文详细总结（自动生成）

### 论文总结：AI-enabled reconstruction of 3D spatial multi-omics at single-cell resolution

#### 0. 源代码链接
[https://github.com/ZacharyWang-007/Histo3D-MO](https://github.com/ZacharyWang-007/Histo3D-MO)

#### 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：现有技术无法在单细胞分辨率下同时实现三维（3D）空间多组学映射，因为传统方法面临权衡：稀疏的切片组学测序缺乏体积连续性，而体积成像技术（如Deep-STARmap）穿透深度浅且基因覆盖有限。缺乏一种经济、可扩展的方法来重建高分辨率的3D多组学图谱。
- **整体含义**：论文提出一种混合实验-计算流程Histo3D-MO，通过整合稀疏的、不重叠的空间单组学测量（仅少数几个切片）与密集的H&E组织学图像，首次实现单细胞分辨率的3D空间多组学重构，为理解肿瘤微环境等复杂组织结构提供了新工具。

#### 2. 方法论：核心思想、关键技术细节
- **核心思想**：利用组织形态与分子表达的内在耦合，以H&E形态特征为锚点，将不同组学特征从少数“锚点”切片转移到整个组织体积（由密集H&E切片框架界定）。
- **关键步骤**：
  1. **实验范式**：将组织块连续切片（本研究为100张），选择少量（3张）不重叠组学测序的锚点切片（分别测两个转录组panel和蛋白质组），其余切片仅做H&E成像。
  2. **图像配准**：将所有切片对齐到公共坐标系（CCF）。
  3. **细胞分割与形态特征提取**：使用Cellpose对H&E图像进行实例分割，对每个细胞提取128×128像素的局部和全局图块，并通过病理基础模型UNI提取多尺度形态特征。
  4. **SPONGE模型**：核心是多组学对角线集成预测模型。它输入形态特征和切片ID（通过梯度反转层消除染色偏移），利用交叉注意力机制融合特征，通过多个组学特异解码器输出预测的转录/蛋白表达。训练时同时使用测序切片及其相邻的H&E-only切片，优化分类和重建损失。
  5. **标签推断**：细胞类型从锚点切片通过潜在嵌入的最近邻多数投票传播；空间域通过CellCharter框架（基于GMM）从锚点切片学习并应用于H&E-only切片。
- **公式/算法流程**（文字说明）：
  - 形态特征提取：`f = Concat(avgpool(UNI(patch)[:4,:4]), avgpool(UNI(patch)[:,:]))`。
  - SPONGE训练：输入`(f, slice_id)` → 共享编码器 → 交叉注意力融合 → 梯度反转层（对抗去偏）→ 组学特异解码器 → 输出预测表达。
  - 细胞类型传播：对于每个待预测细胞，计算其潜在嵌入与参考锚点细胞嵌入的欧氏距离，取top-k近邻，若某类型票数>k/2则分配，否则排除。
  - 空间域识别：对锚点切片嵌入做PCA降维，加上空间坐标，用CellCharter的GMM建模，将H&E-only切片嵌入用同一PCA变换后输入训练好的GMM。

#### 3. 实验设计
- **数据集**：内部肝细胞癌（HCC）组织块，连续切片100张（ID1~ID100）。锚点切片：ID1（转录组Panel A，284基因）、ID10（转录组Panel B，285基因）、ID100（蛋白质组21蛋白）。其余97张仅H&E成像。
- **Benchmark**：保留切片（如ID1预测其他组学）进行定量评估。
- **对比方法**：OmiCLIP、wo ft、STnet、STMCL、DeepPT、iStar、EGN、OmiCLIP ft、SpatialEx、mclSTExp等10种方法。
- **评价指标**：omics级Pearson相关系数（PCC，越高越好）、相关性矩阵距离（CMD，越低越好）、空间保守性（Moran's I的PCC）。细胞类型传播用标签一致性，空间域用多个聚类指标。

#### 4. 资源与算力
- 文中未明确说明使用的GPU型号、数量或训练时长。仅在方法中提到“GPU加速启用”（用于Cellpose分割和模型推理），但未给出具体算力细节。

#### 5. 实验数量与充分性
- **主要实验**：1）SPONGE多组学预测性能对比（图1d，包括PCC、CMD、空间保守性，涉及三个组学层）；2）细胞类型传播验证（图1d-vii，图S4）；3）空间域识别一致性（图1d-viii，图S5）；4）重建的3D数据下游分析（图2）：PTR空间模式、细胞密度图谱、体积IoU、基因表达趋势、细胞-细胞互作分析。
- **充分性**：实验覆盖了预测、传播、域识别、生物学验证等多个方面，对比方法全面（10个），评价指标多样（PCC、SPCC、CMD等）。但仅使用一个内部HCC数据集，缺乏跨组织、跨疾病的外部验证，可能影响泛化性。消融实验较少（仅图S1提及染色偏移的处理），也未详细报告超参数敏感性。

#### 6. 主要结论与发现
- Histo3D-MO能够以经济、可扩展的方式重构单细胞分辨率的3D空间多组学图谱。
- SPONGE在跨组学对角线集成预测上显著优于现有方法（PCC提升23.5%~66.3%）。
- 在HCC数据中，揭示了3D空间中翻译效率（PTR）的异质性：单核细胞中CD14、CD68、CD44的PTR在不同病理区域存在差异。
- 发现恶性细胞与单核细胞在体积上解耦（沿z轴逐渐减弱），伴随单核细胞向免疫抑制型肿瘤相关巨噬细胞（TAM）表型转变（代谢应激标志物下调、免疫检查点上调）。
- 3D细胞-细胞互作分析显示肿瘤核心内单核细胞与恶性细胞互作降低，而基质区肝星状细胞与巨噬细胞共定位，形成结构屏障。

#### 7. 优点
- **混合范式创新**：首次将H&E组织学作为桥梁，实现稀疏单组学到密集3D多组学的重构，突破了技术瓶颈。
- **对角线集成**：SPONGE在训练时同时利用多个不重叠组学，增强了跨组学预测能力。
- **细胞-域联合推断**：提供了完整的细胞类型传播和空间域标注流程，无需额外测序。
- **验证扎实**：通过保留切片和多种指标系统验证了预测、传播、域识别效果，并展示了有生物学意义的发现（如PTR、单核细胞分化轨迹）。

#### 8. 不足与局限
- **实验覆盖有限**：仅使用一个内部肝癌数据集，未在公开数据集或不同组织类型上验证，泛化性存疑。
- **资源开销未透明**：未报告训练SPONGE所需的算力资源，影响可重复性。
- **配准误差风险**：依赖图像配准，连续切片可能导致对齐伪影，影响3D重建保真度。
- **细胞类型传播依赖阈值**：top-k多数投票策略的参数（如k值）未充分讨论，可能影响传播准确率。
- **缺乏消融分析**：未系统评估各模块（如梯度反转层、多尺度特征）的贡献，也未对比其他H&E预测方法作为基线的3D扩展性能。
- **PTR定义的局限性**：论文指出PTR不能代表严格翻译效率，仅用于比较，但下游分析仍将其作为“翻译效率”代理，可能过度解释。

（完）
