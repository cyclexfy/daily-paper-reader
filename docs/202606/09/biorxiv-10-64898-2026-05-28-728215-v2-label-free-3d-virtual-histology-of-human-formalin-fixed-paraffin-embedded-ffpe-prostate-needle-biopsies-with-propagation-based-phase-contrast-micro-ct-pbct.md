---
title: Label-free 3D virtual histology of human formalin-fixed paraffin-embedded (FFPE) prostate needle biopsies with propagation-based phase-contrast micro-CT (PBCT)
title_zh: 基于传播相位衬度显微CT对福尔马林固定石蜡包埋（FFPE）人前列腺穿刺活检组织进行无标记三维虚拟组织学成像
authors: "Sugarman, A. L., Vanselow, D. J., Chen, G., Clark, E., Parkinson, D., La Riviere, P., Silverman, J., Warrick, J., Cheng, K. C. C."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728215v2.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 前列腺癌活检的3D虚拟组织学
tldr: "传统2D组织学依赖切片，限制了对3D细胞体积和组织结构的评估。本研究使用传播相位对比微CT（PBCT）对FFPE前列腺穿刺活检进行无标记3D成像，获取0.5微米各向同性体素，并通过cycleGAN生成虚拟H&E染色。PBCT可清晰区分良性组织和Gleason模式3、4、5，展示3D腺体结构。该方法实现了无破坏性虚拟组织学，避免了采样和切片伪影，有望辅助前列腺癌诊断与定量分析。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统2D组织学受限于切片采样，无法充分评估3D细胞和组织结构，需要无破坏性的3D组织学方法。
method: "使用PBCT对FFPE前列腺活检进行无标记3D成像，结合Neuroglancer界面和cycleGAN生成虚拟H&E染色。"
result: "PBCT以0.5微米分辨率区分良性组织和Gleason模式3-5，展示3D腺体结构，虚拟H&E染色合理。"
conclusion: 基于PBCT的3D虚拟组织学可行，无破坏性获取细胞和组织结构，避免采样和人造伪影，有潜力辅助前列腺癌诊断。
---

## 摘要
一个多世纪以来，通过肿瘤活检组织评估临床预后的目标一直基于2D组织切片（仅代表所采集样本的一小部分）的组织形态学。其优势来源于组织学：1）对细胞类型的无偏表示，2）能够表征不同细胞类型健康和疾病状态的亚细胞分辨率，以及3）允许评估肿瘤异质性的多毫米视野。然而，组织学依赖于物理切片，限制了对三维细胞体积和组织结构的评估。本研究利用基于传播的相位衬度显微CT（PBCT）对残留的福尔马林固定石蜡包埋（FFPE）前列腺穿刺活检组织创建了3D组织学图像。所得的各向同性、灰度、0.5微米体素矩阵用于探索3D虚拟组织学区分诊断类别的潜力，包括良性前列腺组织和Gleason分级3、4、5的前列腺腺癌。对总计5微米“切片”的数字切片堆栈进行最大强度投影，可以研究对应于微CT成像后实际连续H&E染色组织切片的虚拟切片。与组织学类似，我们的PBCT重建能够区分良性前列腺组织的非浸润性和波状腺体、Gleason分级3的浸润性圆形腺体、Gleason分级4的筛状结构以及Gleason分级5的粉刺状坏死。与组织学不同，微CT使我们能够在体积背景下进一步探测3D组织结构。通过定制的Neuroglancer多平面和3D渲染界面实现了用户友好的样本体积探索。经过稀疏训练的cycleGAN从未染色的微CT重建中生成了逼真的虚拟H&E染色。与基于组织切片的组织学不同，基于微CT的虚拟组织学能够对癌细胞和组织结构（包括腺腔）进行无损的3D表征，且没有组织学的欠采样或切片伪影。这些发现证明了基于PBCT的前列腺癌3D虚拟组织学的可行性，并提示探索肿瘤特性的衍生定量分析可能为患者护理做出贡献。

## Abstract
For over a century, the goal of estimating clinical outcome from tumor biopsies has been based on histomorphology of 2D tissue slices that represent a small fraction of collected samples. Its power derives from histologys 1) unbiased representation of cell types, 2) subcellular resolution that allows the characterization of health and disease states across cell types, and 3) multi-millimeter fields of view that allow assessment of tumor heterogeneity. Histologys dependence upon physical slices, however, limits assessment of 3-dimensional cellular volumes and tissue architecture. Here, we used propagation-based phase-contrast micro-CT (PBCT) to create 3D histological images of residual formalin-fixed, paraffin-embedded (FFPE) prostate needle biopsies. The resulting isotropic, grey-scale, 0.5 micron voxel matrices were used to explore the potential of for the 3D virtual histology to distinguish diagnostic categories including benign prostatic tissue and prostatic adenocarcinoma of Gleason patterns 3, 4, and 5. Maximum intensity projections of stacks of digital slices totaling 5 microns "slices" allowed the study of virtual sections corresponding to actual serial H&E-stained sections of tissue cut after micro-CT imaging. Like histology, our PBCT reconstructions allowed us to distinguish between non-infiltrative and undulating glands of benign prostatic tissue, infiltrative round glands of Gleason pattern 3, cribriform structures of Gleason pattern 4, and comedonecrosis of Gleason pattern 5. Unlike histology, micro-CT allowed us to further probe 3D tissue architecture in volumetric context. User-friendly exploration of sample volumes was achieved using a customized Neuroglancer multiplanar and 3D rendering interface. Sparsely trained cycleGAN produced plausible virtual H&E staining from the unstained micro-CT reconstructions. Unlike tissue-section based histology, micro-CT-based virtual histology yields nondestructive 3D characterization of cancer cell and tissue architecture, including glandular spaces, without the undersampling or cutting artifacts of histology. These findings demonstrate the feasibility of PBCT-based 3D virtual histology of prostate cancer and suggest the exploration of derived quantitative analyses of tumor properties for potential contributions to patient care.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容生成的中文详细总结。

### 0. 论文的源代码链接
无（该论文为预印本，未提供源代码链接）。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：传统2D组织学依赖物理切片，只能分析样本的一小部分，无法充分评估三维细胞体积和组织结构，存在采样偏差和切片伪影。
- **研究动机**：需要一种无破坏性的3D组织学方法，能够以亚细胞分辨率、大视场、无偏地表征完整的活检组织，从而更准确地评估前列腺癌的Gleason分级和肿瘤异质性。
- **整体含义**：本研究探索了基于传播相位衬度显微CT（PBCT）对福尔马林固定石蜡包埋（FFPE）前列腺穿刺活检组织进行无标记3D成像的可行性，旨在提供一种可替代传统组织学的3D虚拟组织学技术，有望改善前列腺癌诊断和定量分析。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用PBCT对未染色的FFPE组织进行高分辨3D成像，获取各向同性灰度体素数据，再通过深度学习生成虚拟H&E染色，实现3D虚拟组织学。
- **关键技术细节**：
  - **成像技术**：基于传播的相位衬度显微CT（PBCT），利用X射线通过组织后的相位变化增强对比度，无需染色或标记即可获得0.5微米各向同性体素分辨率的3D灰度图像。
  - **虚拟切片生成**：对PBCT重建的3D体素矩阵，沿轴向提取厚度为5微米的数字切片堆栈，通过最大强度投影（MIP）生成虚拟切片，模拟传统H&E染色组织切片的2D图像。
  - **3D可视化**：使用定制的Neuroglancer多平面和3D渲染界面，实现用户友好的样本体积探索，可交互查看任意平面和3D结构。
  - **虚拟H&E染色**：采用稀疏训练的cycleGAN（循环生成对抗网络），将未染色的PBCT灰度重建图像转换为逼真的虚拟H&E染色图像。训练过程中仅使用少量配对的PBCT与真实H&E染色图像对（稀疏训练）。
- **算法流程**：FFPE样本 → PBCT扫描 → 3D各向同性灰度重建 → 数字切片MIP → 2D虚拟切片 → 输入cycleGAN（稀疏训练） → 输出虚拟H&E染色图像。同时，通过Neuroglancer进行3D体积渲染和交互分析。

### 3. 实验设计
- **数据集**：使用了福尔马林固定石蜡包埋（FFPE）的人前列腺穿刺活检组织，包含良性前列腺组织以及Gleason模式3、4、5的前列腺腺癌样本。具体样本数量文中未明确，但展示了不同诊断类别的代表性结果。
- **基准（Benchmark）**：没有显式的外部基准数据集。实验以传统H&E组织学作为金标准进行对比：在对同一组织进行PBCT成像后，再实际切片并H&E染色，将PBCT虚拟切片与真实H&E切片进行比较。
- **对比方法**：主要与传统2D组织学（H&E染色）进行定性和定量结构对比，验证PBCT虚拟组织学能否区分良性、Gleason 3、4、5的形态学特征（如良性腺体的波浪状、Gleason 3的浸润性圆形腺体、Gleason 4的筛状结构、Gleason 5的粉刺状坏死）。未与其他3D成像方法（如传统微CT、组织切片三维重建等）进行系统性比较。

### 4. 资源与算力
- 论文中未明确说明使用的GPU型号、数量、训练时长等算力资源。仅提及cycleGAN采用“稀疏训练”（sparsely trained），暗示训练数据量不大，但具体资源消耗未提供。

### 5. 实验数量与充分性
- **实验数量**：论文未列出详细的实验组数或统计数字。主要展示了几个代表性样本（良性、Gleason 3、4、5）的定性对比结果，以及虚拟H&E染色的效果示例。没有进行大规模队列验证或定量指标（如分类准确率、结构相似性指数等）的系统评估。
- **充分性与公平性**：实验作为可行性验证是初步的，但不够充分。缺乏多个独立样本的重复性测试、不同成像参数下的稳定性测试，以及与传统组织学诊断一致性的定量分析（如病理医生双盲阅片对比）。对比方法也仅与金标准组织学进行主观比较，未与其他先进3D组织学技术（如光片显微镜、多光子显微镜等）对比。因此，实验的客观性和公平性有待补充更多数据支持。

### 6. 论文的主要结论与发现
- PBCT能够以0.5微米各向同性分辨率对FFPE前列腺穿刺活检组织进行无标记3D成像，并清晰区分良性组织与Gleason模式3、4、5的肿瘤特征。
- 通过虚拟切片（MIP）和cycleGAN虚拟染色，PBCT重建图像可产生与真实H&E组织学高度相似的2D图像，并保留腺腔等3D空间结构信息。
- 基于PBCT的3D虚拟组织学相比传统组织学具有无损、无欠采样、无切片伪影的优势，能够提供完整的3D细胞和组织结构视图，有助于更准确的Gleason分级和肿瘤异质性评估。
- 该方法为开发衍生的定量分析（如腺体形态、肿瘤体积、浸润模式等）提供了可能性，有望为前列腺癌患者护理做出贡献。

### 7. 优点：方法或实验设计上的亮点
- **技术创新**：首次将传播相位衬度微CT（PBCT）应用于FFPE前列腺活检的无标记3D虚拟组织学，实现了亚微米级各向同性分辨率，无需任何外源对比剂。
- **3D无破坏性**：整个FFPE样本可反复扫描，不破坏组织，允许后续进行实际组织学切片或分子分析。
- **避免传统组织学固有缺陷**：消除了2D切片引起的欠采样（遗漏关键结构）和切片伪影（如折叠、撕裂、染色不均），能完整观察肿瘤的三维形态。
- **用户友好可视化**：利用Neuroglancer界面支持多平面重切和3D渲染，便于病理医生直观探索样本体积。
- **虚拟染色可行性**：稀疏训练的cycleGAN能够从灰度PBCT图像生成合理的虚拟H&E染色，减少了染色化学依赖。

### 8. 不足与局限
- **样本量小**：仅展示少量代表性样本，缺乏大样本验证，诊断准确性、重复性未量化评估，证据等级较低。
- **缺少定量基准**：未进行病理医生双盲诊断一致性测试，也未计算虚拟染色与真实H&E之间的定量相似性指标（如SSIM、PSNR等）。
- **硬件限制**：PBCT成像速度、通量（能否处理大量活检样本）以及设备普及性未讨论，可能限制临床转化。
- **虚拟染色局限性**：cycleGAN虚拟染色基于灰度图像，可能无法重现所有组织化学染色特征（如免疫组化），且稀疏训练对未见过的组织类型泛化能力未知。
- **成像伪影**：虽然PBCT减少切片伪影，但可能存在相位包裹、束硬化等CT固有伪影，文中未充分分析。
- **应用局限**：目前仅针对前列腺癌Gleason分级，未扩展到其他癌症或非肿瘤性疾病；且仅评估了FFPE样本，对新鲜或冰冻样本适用性未提及。

（完）
