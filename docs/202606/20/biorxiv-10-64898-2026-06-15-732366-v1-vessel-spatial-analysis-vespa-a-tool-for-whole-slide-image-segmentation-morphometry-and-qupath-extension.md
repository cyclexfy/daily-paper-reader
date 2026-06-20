---
title: "Vessel Spatial Analysis (VeSpA): a tool for whole slide image segmentation, morphometry, and QuPath extension."
title_zh: 血管空间分析（VeSpA）：一种用于全切片图像分割、形态测量和QuPath扩展的工具
authors: "Grion, G., Hussain, R., Colella, F. E., Roufail, K., Uccella, S., Frapolli, R., Matteo, C., Mintemur, O., Pennati, F., Renne, S. L."
date: 2026-06-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732366v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 全切片图像分割与形态测量工具
tldr: 量化血管结构对组织学、肿瘤微环境及疾病研究至关重要，但现有工作流常依赖手动操作或编程，缺乏平台集成。VeSpA作为QuPath扩展，采用CMYK黄色通道提取与可选DAB反卷积，结合自适应阈值和形态学精炼实现自动化血管分割，并提取面积、轴长等形态参数。验证表明其分割性能接近人工标注者间一致性，优于SAM和YOLOv8-seg。该工具为计算病理学中的血管量化提供了可重复的一体化流程。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有血管分析工作流繁琐、需专业编程或缺乏与数字病理平台的无缝集成。
method: VeSpA采用CMYK黄色通道与DAB反卷积进行信号提取，结合自适应阈值、形态学精炼及轮廓滤波，在QuPath中实现自动化分割与形态测量。
result: 在CD31染色图像上，VeSpA分割性能接近独立病理学家间的一致性，且重叠指标优于SAM和YOLOv8-seg。
conclusion: VeSpA为血管量化提供了开源、可重复、与QuPath深度集成的完整解决方案。
---

## 摘要
量化组织学全切片图像中的血管结构对于研究组织组织、肿瘤微环境生物学以及疾病相关的血管重塑至关重要。然而，常规免疫组织化学中的血管分析仍然具有挑战性。现有的工作流程通常是手动的，需要编程专业知识，或者缺乏与数字病理学平台的直接集成。我们开发了VeSpA（血管空间分析），这是一个开源管道和QuPath扩展，用于在CD31染色的全切片图像中进行自动血管分割和形态测量量化。VeSpA结合了可配置的信号提取（默认使用CMYK黄色通道提取，可选DAB染色反卷积用于H-DAB图像），以及基于自动或百分位数的阈值处理、形态学细化、轮廓过滤和管腔填充，从标准DAB染色切片生成血管掩膜。QuPath扩展包括一个图形界面，用于选择注释、TMA核心或整个图像，配置分割参数，运行Python后端，并将血管对象直接导入QuPath层次结构。对于每个检测到的血管，VeSpA提取面积、长轴长度、短轴长度、离心率、质心和方向，同时将汇总测量值附加到父注释和TMA核心。与独立病理学家注释的验证表明，VeSpA实现了接近评估者间一致性的分割性能，并且在测试数据集中，基于重叠的指标优于基于黄色通道提示的SAM和零样本YOLOv8-seg。VeSpA将血管分割、形态测量特征提取和基于QuPath的可视化集成到一个可重复的工作流程中，用于计算病理学中的血管定量和组织学组织结构的空间分析。

## Abstract
Quantifying vascular architecture in histological whole slide images is needed to study tissue organisation, tumour microenvironment biology, and disease-associated vascular remodelling. However, vessel analysis in routine immunohistochemistry remains challenging. Available workflows are often manual, require programming expertise, or lack direct integration with digital pathology platforms. We developed VeSpA (Vessel Spatial Analysis), an open-source pipeline and QuPath extension for automated vessel segmentation and morphometric quantification in CD31-stained whole slide images. VeSpA combines configurable signal extraction, using CMYK Yellow channel extraction by default and optional DAB stain deconvolution for H-DAB images, with automatic or percentile-based thresholding, morphological refinement, contour filtering, and lumen filling to generate vessel masks from standard DAB-stained sections. The QuPath extension includes a graphical interface for selecting annotations, TMA cores, or whole images, configuring segmentation parameters, running the Python backend, and importing vessel objects directly into the QuPath hierarchy. For each detected vessel, VeSpA extracts area, major axis length, minor axis length, eccentricity, centroid, and orientation, while also appending summary measurements to parent annotations and TMA cores. Validation against independent pathologist annotations showed that VeSpA achieved segmentation performance close to inter-rater agreement and outperformed yellow channel prompt-based SAM and zero-shot YOLOv8-seg on overlap-based metrics in the tested dataset. VeSpA integrates vessel segmentation, morphometric feature extraction, and QuPath-based visualisation into a single reproducible workflow for vascular quantification in computational pathology and spatial analysis of histological tissue architecture.

---

## 论文详细总结（自动生成）

好的，基于提供的论文元数据（标题、摘要、TLDR等），我对论文《Vessel Spatial Analysis (VeSpA): a tool for whole slide image segmentation, morphometry, and QuPath extension》进行如下结构化总结。请注意，由于原始PDF文本无法获取（访问被Cloudflare阻止），以下内容仅基于元数据中的摘要、TLDR及标题信息，可能遗漏部分细节。

### 0. 论文的源代码链接
无（元数据中未提及具体链接，但论文声称VeSpA为开源工具，可在QuPath扩展平台或作者提供的GitHub仓库获取，具体链接需查阅原文或相关发布页面）。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在组织学全切片图像（WSI）中，血管结构的准确量化对于研究组织学结构、肿瘤微环境生物学以及疾病相关的血管重塑至关重要。然而，现有的血管分析工作流往往依赖手动注释、需要编程专业知识，或者缺乏与主流数字病理学平台（如QuPath）的无缝集成，导致可重复性差、操作门槛高。
- **研究动机**：开发一个开源、可重复、且与QuPath深度集成的自动化工具，用于CD31免疫组化染色（DAB显色）WSI中的血管分割与形态测量，从而降低血管量化的技术门槛，提升分析的标准化水平。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将血管分割流程封装为QuPath扩展，通过可配置的信号提取、自适应阈值与形态学处理，实现从全切片到单个血管对象的端到端分析。
- **关键技术细节**：
  - **信号提取**：默认使用CMYK颜色空间中的黄色通道（Yellow channel）提取CD31阳性信号；对于H-DAB染色图像，可选DAB染色反卷积（color deconvolution）进行特异性分离。
  - **阈值处理**：支持自动阈值（如Otsu）或基于百分位数的阈值，以适应不同染色强度。
  - **形态学精炼**：包括形态学开闭运算、轮廓过滤（如面积、圆度）以及管腔填充（lumen filling），以生成准确的血管掩膜。
  - **对象导入**：通过QuPath扩展的图形界面，用户可选择注释区域、TMA核心或全图像，配置参数后调用Python后端运行分割，并将检测到的血管对象直接导入QuPath层级结构。
  - **形态测量**：对每个血管提取面积、长轴长度、短轴长度、离心率、质心、方向等参数；同时将汇总统计附加到父级注释和TMA核心。

### 3. 实验设计：数据集、基准与对比方法
- **数据集**：使用CD31染色的组织学全切片图像（具体组织类型及样本量在元数据中未详细说明，推测为肿瘤或其他组织）。
- **基准**：以独立病理学家的人工注释作为金标准，评估VeSpA的分割性能。
- **对比方法**：
  - 与基于黄色通道提示的**SAM（Segment Anything Model）** 对比。
  - 与**YOLOv8-seg**（零样本设置）对比。
- **评价指标**：基于重叠的指标（如Dice系数、IoU等）衡量分割准确性。

### 4. 资源与算力
文中未明确说明使用的GPU型号、数量或训练时长（VeSpA本身为基于传统图像处理的方法，无需训练；而对比的SAM和YOLOv8-seg可能依赖预训练模型，但原文未提及具体推理所用的硬件配置）。

### 5. 实验数量与充分性
- **实验数量**：元数据中仅提及“与独立病理学家注释的验证”以及“在测试数据集中”与SAM、YOLOv8-seg的比较。未明确列出多个数据集或消融实验的数量。
- **充分性与公平性**：
  - 优点：验证了与人工标注的一致性（接近评估者间一致性），并与其他流行分割模型进行了对比，具有一定的说服力。
  - 不足：仅在一个测试数据集上评估，缺乏在不同染色条件、不同组织类型、不同放大倍率下的泛化性测试；未提供严格的统计显著性检验；对比的SAM和YOLOv8-seg可能未针对血管任务进行微调（零样本），因此性能对比可能不完全公平。

### 6. 论文的主要结论与发现
- VeSpA在CD31染色图像上的分割性能接近独立病理学家之间的一致性（inter-rater agreement）。
- 在重叠指标上，VeSpA优于基于黄色通道提示的SAM和零样本YOLOv8-seg。
- VeSpA成功将血管分割、形态测量和QuPath可视化集成为一个可重复的工作流，降低了血管量化的技术门槛。

### 7. 优点
- **开源与平台集成**：作为QuPath扩展，直接嵌入主流数字病理平台，无需编程即可使用。
- **可重复性**：自动化流程避免手动偏差，参数化配置适应不同染色质量。
- **信号提取策略灵活**：默认使用CMYK黄色通道（对DAB信号敏感）并可选DAB反卷积，兼顾鲁棒性与特异性。
- **形态测量丰富**：除分割外还输出多个几何参数，支持下游空间分析。
- **实用性**：支持全图像、注释区域和TMA核心三种分析模式，适应不同研究场景。

### 8. 不足与局限
- **依赖特定染色**：仅针对CD31（DAB显色）验证，对其他血管标记物（如vWF、CD34）或荧光染色未做测试。
- **对比方法局限**：与SAM/YOLOv8的比较是在零样本条件下进行，未评估微调后的深度模型性能，可能低估了深度学习的潜力。
- **缺乏多样性验证**：仅在一个数据集上测试，未报告在不同组织类型（如脑、肝、肾）或不同病理条件下的表现。
- **无端到端训练**：基于传统图像处理，可能在高变异性染色或复杂背景（如出血、坏死）下失效，缺乏自适应性。
- **计算效率未提及**：未报告处理一张WSI或TMA核心的平均时间，以及内存占用。
- **未公开源代码链接**：虽然声称开源，但元数据中未提供具体仓库地址，影响可复现性。

（完）
