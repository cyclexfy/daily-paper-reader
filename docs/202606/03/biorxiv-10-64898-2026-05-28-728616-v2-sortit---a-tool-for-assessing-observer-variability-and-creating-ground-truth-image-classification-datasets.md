---
title: SortIT - A Tool For Assessing Observer Variability And Creating Ground Truth Image Classification Datasets
title_zh: SortIT - 评估观察者变异性并创建真实图像分类数据集的工具
authors: "Uegami, W., Bisson, T., Okoshi, E. N., Costa da Silva, F. G., Munkhdelger, J., Lami, K., Zerbe, N., Bychkov, A., Fukuoka, J."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728616v2.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 用于病理全玻片图像标注和真实数据集创建的工具
tldr: 病理评估中的观察者间变异性影响诊断可靠性，AI辅助诊断需依赖高质量地面真值数据集。SortIT作为开源Web应用，支持多位注释者独立标记图块并导出数据，用于统计观察者变异和生成共识标签。该工具已成功应用于有丝分裂分割、前列腺癌分级评估及肉芽肿分类等场景。SortIT的易部署性和开放性使其成为建立可靠数据集、评估变异性的实用工具，有助于开发准确泛化的诊断AI。
source: biorxiv
selection_source: fresh_fetch
motivation: 病理评估存在主观性导致的观察者间变异性，AI标准化需高质量共识数据集。
method: SortIT开源Web应用，允许多位注释者独立标记图块，灵活权限控制，导出数据用于变异分析和共识构建。
result: 支持有丝分裂分割、前列腺癌分级评估、肉芽肿分类等场景，成功建立共识数据集并评估变异性。
conclusion: SortIT易部署且开源，为建立高质量地面真值数据集和评估观察者变异性提供实用工具，促进诊断AI开发。
---

## 摘要
病理评估中的观察者间变异性是一个公认的挑战，影响着诊断可靠性和疾病理解。由于评估的主观性，这种变异性存在于许多亚专业领域。应用于全切片图像的人工智能（AI）有潜力标准化病理流程并减少变异性，但转向这些技术并不能保证改进。建立具有共识标注的可靠真实数据集对于开发稳健的AI解决方案至关重要。我们介绍了SortIT，一个开源网络应用程序，有助于系统地创建和评估真实图像块标注。SortIT使多个标注者能够独立对图像块进行标注，并具有灵活的用户权限控制。标注数据可以导出，用于观察者变异性的统计分析，以及从共识图像块创建真实数据集。我们概述了使用SortIT的几个用例协议：（1）肿瘤区域的核分裂分割；（2）通过与专家共识比较来评估前列腺癌分级的AI解决方案；（3）通过标注判别性图像块级特征进行肉芽肿分类。SortIT的主要优势在于其易于部署，使其对广泛用户可访问和可用。总的来说，SortIT为建立高质量的真实数据集和全面评估观察者变异性提供了一个有价值的工具。使用系统性标注方法对真实质量进行关键评估对于开发准确且可推广的诊断AI工具至关重要。其开源特性便于社区采用和进一步开发。

## Abstract
Interobserver variability in pathological assessments is a well-recognized challenge that impacts diagnostic reliability and disease understanding. This variability exists across many subspecialties due to the subjective nature of evaluations. Artificial intelligence (AI) applied to whole slide images has potential to standardize procedures and reduce variability in pathology, but transitioning to these technologies does not guarantee improvement. Establishing reliable ground truth datasets with consensus annotations is crucial for developing robust AI solutions. We introduce SortIT, an open-source web application that facilitates systematic creation and evaluation of ground truth image tile annotations. SortIT enables multiple annotators to independently label tiles, with flexible user permission controls. Annotated data can be exported for statistical analysis of observer variation and for creating ground truth datasets from consensus tiles. We outline protocols using SortIT for several use cases: (1) mitosis segmentation in tumor regions, (2) evaluating AI solutions for prostate cancer grading by comparing to expert consensus, and (3) granuloma classification by annotating discriminative tile-level features. Key strengths of SortIT lies in its ease of deployment, making it accessible and usable for a wide range of users. Overall, SortIT provides a valuable tool to establish high-quality ground truth datasets and comprehensively assess observer variability. Critical evaluation of ground truth quality using systematic annotation methodologies is crucial for developing accurate and generalizable diagnostic AI tools. Its open-source nature facilitates community adoption and further development.

---

## 论文详细总结（自动生成）

0. **源代码链接**：https://github.com/FukuokaLab/SortIT

1. **核心问题与整体含义（研究动机和背景）**  
   - 病理评估**观察者间变异性**普遍存在，影响诊断可靠性与疾病理解，尤其在罕见疾病或主观判读场景中更为突出。  
   - **AI辅助诊断**有潜力标准化流程，但模型性能依赖**高质量真实数据集（Ground Truth）**，而数据集的质量（如标注一致性）常被忽视。  
   - 现有标注工具（如CVAT、Label Studio）多聚焦目标检测/分割，缺乏专为**多专家独立标注**、**变异性评估**及**共识构建**设计的轻量级Web工具。  
   - SortIT旨在填补这一缺口：提供易部署的开源Web应用，支持多位病理学家独立对图像块（tile）分类，导出数据用于统计观察者间/内变异，并生成共识真实标签，最终帮助开发可靠、可泛化的诊断AI。

2. **方法论：核心思想、关键技术细节、算法流程**  
   - **核心思想**：通过Web界面让多位标注者独立分类预先生成的图像块，导出CSV格式标注结果，再基于Cohen's kappa/Fleiss' kappa等指标评估变异性，最终筛选共识块作为真实训练数据。  
   - **关键技术细节**：  
     - 基于**Django框架**开发，支持本地或云端部署，可封装为Docker容器。  
     - 用户角色：**管理员**（管理数据集/用户）和**标准用户**（仅标注），管理员可灵活分配权限。  
     - 标注模式：**单类模式**（网格显示图像，点击选择不属于目标类的图像，被选图像标记为空）和**多类模式**（逐个显示图像，从多个选项中勾选适用类别）。  
     - 导出数据**CSV格式**：行=用户，列=图像，单元格=类别标签。  
     - 图块生成**不包含在SortIT内**：推荐使用openslide‑python或QuPath（附有示例脚本），可调整块大小、重叠区域、分辨率等。  
     - 评估观察者内变异性：为同一人创建多个账户，首轮标注后设置**清洗期（≥2周）**，再用另一账户重复标注。  
   - **算法流程**：  
     1. 收集WSI → 2. 生成图像块（QuPath/openslide） → 3. 上传至SortIT → 4. 多位病理学家独立标注 → 5. 导出CSV → 6. 计算统计指标 → 7. 基于共识（如多数投票）筛选共识块 → 8. 用于AI模型训练。

3. **实验设计：数据集/场景、benchmark、对比方法**  
   - **验证研究**：  
     - 3名认证病理学家（P1‑P3），对2例WSI进行“肿瘤丰富斑块选择”（要求≥70%肿瘤细胞）。  
     - 对比方法：SortIT（直接视觉判断） vs. 手动标注（在QuPath上绘制多边形区域，再提取覆盖≥70%的斑块）。  
     - 测量指标：生成斑块数量、完成时间。  
     - 结果：SortIT生成的肿瘤斑块数量显著多于手动标注（p=0.0074，95%CI=[106.1,414.2]）；时间无显著差异（p=0.50）。  
   - **用例（Use Cases）**：仅提出协议，未实际运行完整实验。  
     - 有丝分裂分割（mitosis segmentation）  
     - 前列腺癌分级AI评估（AI vs. 专家共识）  
     - 肉芽肿分类（多类标注局部特征）  
   - **Benchmark**：验证研究仅与QuPath手动标注对比，未与其他标注工具（如CVAT、Label Studio）直接比较。

4. **资源与算力**  
   - 论文**未明确说明**使用的GPU型号、数量或训练时长。验证研究仅记录人工时间（秒级），不涉及模型训练资源。用例部分仅为理论设计，无实际计算资源描述。

5. **实验数量与充分性**  
   - **验证研究**仅2例WSI、3名病理学家，样本量很小，不足以得出普遍结论；未进行统计功效分析或多种任务验证。  
   - **用例**均为协议描述，未提供实际实施数据，缺乏消融实验或与基线对比。  
   - 总体实验**不充分**，但符合**工具介绍型论文**的定位——重点展示功能而非全面验证性能。实验过程较客观（盲法、独立标注），但受限于规模。

6. **主要结论与发现**  
   - SortIT能比手动标注（QuPath）**更高效地生成更多肿瘤丰富斑块**，且耗时相当。  
   - 通过三个用例展示了SortIT在**有丝分裂分割**、**前列腺癌AI评估**、**肉芽肿分类**中的适用性，强调其可辅助评估观察者变异并建立共识真实数据集。  
   - **关键主张**：在AI开发中，必须系统评估真实数据集的质量（变异性），SortIT为此提供了低成本、易用的解决方案。

7. **优点**  
   - **完全开源**（GitHub），社区可自由使用、审计和扩展。  
   - **基于Web**，无需安装，支持手机/平板/PC，跨平台易用。  
   - **多用户独立标注**，权限可灵活配置，适合多中心协作。  
   - **Docker一键部署**简化环境配置，降低IT门槛。  
   - **验证研究证实**了实际效率提升（更多斑块，时间持平），初步证明工具有效性。  
   - **专注图块分类**，功能简洁，避免过度复杂。

8. **不足与局限**  
   - **仅支持图块级分类**，无法进行像素级分割或目标检测，应用范围受限。  
   - **不提供端到端流程**：图块生成和统计分析需用户自行完成（仅提供QuPath示例脚本）。  
   - **缺乏内置统计模块**：导出CSV后需用户用外部工具计算kappa等指标。  
   - **验证实验样本量极小**（2例WSI，3位病理学家），统计显著性存疑，结论推广性有限。  
   - **无法在标注时查看上下文**：标注者仅能查看静态图块，不能像WSI浏览器那样平移缩放，可能丢失空间信息（但可上传较大块并标记待分类区域以部分缓解）。  
   - 与其他成熟标注工具（如CVAT、Label Studio）的功能对比不够全面；论文仅列举了部分工具但未进行系统基准测试。

（完）
