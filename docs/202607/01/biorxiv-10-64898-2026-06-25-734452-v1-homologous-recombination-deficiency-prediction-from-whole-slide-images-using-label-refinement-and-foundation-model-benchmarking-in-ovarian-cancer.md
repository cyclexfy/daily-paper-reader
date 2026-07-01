---
title: Homologous recombination deficiency prediction from whole slide images using label refinement and foundation-model benchmarking in ovarian cancer
title_zh: 利用标签细化和基础模型基准测试在卵巢癌全切片图像中预测同源重组缺陷
authors: "Shah, N. A., Sarwar, M., Ullah, E."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734452v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 利用标签细化和基础模型从全切片图像预测卵巢癌HRD
tldr: 针对卵巢癌中同源重组缺陷（HRD）的预测，使用TCGA-OV的HE全切片图像，通过标签细化（结合BRCA1启动子甲基化）和多种基础模型（UNI2-h等）进行患者级注意力多实例学习。最佳模型AUROC达0.634，表明存在微弱的形态学信号，但无法支持临床解释。本研究为计算病理学中基于HE的HRD预测提供了基准框架和方法基础。
source: biorxiv
selection_source: fresh_fetch
motivation: HRD是高级别浆液性卵巢癌铂类敏感性和PARPi疗效的关键标志，但缺乏整合HE图像与临床验证HRD检测的公开数据集，阻碍计算病理学模型开发。
method: 使用TCGA-OV中316例患者的717张冰冻切片HE WSI，经标签细化（整合BRCA1甲基化），采用UNI2-h等6种编码器提取特征，以注意力多实例学习进行患者级分类。
result: UNI2-h结合细化标签取得最佳性能：AUROC 0.634，AUPRC 0.468，平衡准确率0.597；其他模型或基线均低于该值。
conclusion: TCGA-OV HE WSI存在与HRD相关的微弱信号，但性能不足临床应用；本研究作为概念验证基准，为未来基于临床PARPi反应队列的建模奠定方法基础。
---

## 摘要
背景：同源重组缺陷（HRD）在高浆液性卵巢癌（HGSOC）中具有临床重要性，特别是因为其与铂类敏感性的关联以及从聚（ADP-核糖）聚合酶抑制剂（PARPi）治疗中获益。然而，公共数据集很少包含诊断性苏木精和伊红（H&E）全切片图像（WSI）、经过验证的临床HRD检测结果、基因组疤痕评分、BRCA1启动子甲基化数据以及治疗反应结局的完整组合。这为旨在从常规组织学中开发临床可解释的HRD或PARPi反应模型的计算病理学研究造成了主要障碍。目的：我们进行了一项探索性的、泄漏控制的计算病理学基准测试研究，以评估来自TCGA-OV的H&E WSI是否包含与科研级分子HRD标签相关的可测量的形态学相关信号，以及标签细化和病理学基础模型嵌入是否改变预测性能。方法：我们组装了一个冷冻原发TCGA-OV WSI队列，包括来自316名患者的717张组织切片/生物标本切片。由于与冷冻原发队列的患者完全重叠，诊断性FFPE DX切片被排除在模型选择之外。评估了两种HRD标签：基于BRCA/HR基因突变证据的初始仅突变分子标签，以及额外纳入BRCA1启动子甲基化的细化甲基化增强分子标签。使用ResNet50、UNI、CONCH、Virchow2、Phikon-v2和UNI2-h编码器进行特征提取。采用基于注意力的多实例学习（ABMIL），以患者为袋进行建模。评估使用了患者级别的分组5折×5次重复分层交叉验证，共25折，自助法置信区间，以及患者级别的泄漏控制。结果：初始仅突变标签将78名患者分类为阳性，238名为阴性。细化的甲基化增强标签额外恢复了33名阳性患者，结果为111名阳性和205名阴性患者。使用UNI2-h特征的患者级别ABMIL在细化标签上达到最强性能：AUROC 0.634（95% CI 0.571-0.698），AUPRC 0.468（95% CI 0.390-0.562），平衡准确率0.597，敏感性0.532，特异性0.663，F1分数0.494，Brier分数0.233。校准阈值为0.512，得到TN=136，FP=69，FN=52，TP=59。对比模型显示出较低的辨别能力，包括使用初始标签的UNI2-h（AUROC 0.628），Phikon-v2细化（0.582），Virchow2细化（0.582），CONCH初始（0.587），ResNet50细化（0.570），以及临床基线（AUROC 0.54-0.57）。结论：TCGA-OV H&E WSI包含与科研级分子HRD状态相关的适度但可重复的形态学相关信号。然而，AUROC约为0.63，缺乏临床HRD检测标签，实施工作流程中缺少基因组疤痕终点，以及缺乏PARPi/铂类反应目标，阻碍了临床解释。本研究应被解释为概念验证的基准测试框架和方法学基础，用于未来在临床精选的PARPi反应队列中进行基于H&E的预测建模。

## Abstract
Background: Homologous recombination deficiency (HRD) is clinically imperative in high-grade serous ovarian carcinoma (HGSOC), particularly because of its association with platinum sensitivity and benefit from poly(ADP-ribose) polymerase inhibitor (PARPi) therapy. However, public datasets rarely contain a complete combination of diagnostic haematoxylin and eosin (H&E) whole-slide images (WSIs), validated clinical HRD assay results, genomic scar scores, BRCA1 promoter methylation data, and treatment-response outcomes. This creates a major barrier for computational pathology studies seeking to develop clinically interpretable models of HRD or PARPi response from routine histology. Objective: We performed an exploratory, leakage-controlled computational pathology benchmarking study to evaluate whether H&E WSIs from TCGA-OV contain a measurable morphology-linked signal associated with research-grade molecular HRD labels, and whether label refinement and pathology foundation-model embeddings alter predictive performance. Methods: We assembled a frozen-primary TCGA-OV WSI cohort comprising 717 tissue-section/biospecimen slides from 316 patients. Diagnostic FFPE DX slides were excluded from model selection because of complete patient overlap with the frozen-primary cohort. Two HRD labels were evaluated: an initial mutation-only molecular label based on BRCA/HR-gene mutation evidence, and a refined methylation-enhanced molecular label that additionally incorporated BRCA1 promoter methylation. Feature extraction was performed using ResNet50, UNI, CONCH, Virchow2, Phikon-v2, and UNI2-h encoders. Patient-level attention-based multiple instance learning (ABMIL) was used with patient-as-bag modelling. Evaluation used patient-level grouped 5-fold x 5-repeat stratified cross-validation, with 25 folds total, bootstrap confidence intervals, and patient-level leakage control. Results: The initial mutation-only label classified 78 patients as positive and 238 as negative. The refined methylation-enhanced label recovered 33 additional positives, resulting in 111 positive and 205 negative patients. Patient-level ABMIL using UNI2-h features achieved the strongest performance for the refined label, with AUROC 0.634 (95% CI 0.571-0.698), AUPRC 0.468 (95% CI 0.390-0.562), balanced accuracy 0.597, sensitivity 0.532, specificity 0.663, F1 score 0.494, and Brier score 0.233. The calibrated threshold was 0.512, yielding TN=136, FP=69, FN=52, and TP=59. Comparative models showed lower discrimination, including UNI2-h with the initial label (AUROC 0.628), Phikon-v2 refined (0.582), Virchow2 refined (0.582), CONCH initial (0.587), ResNet50 refined (0.570), and clinical baselines (AUROC 0.54-0.57). Conclusions: TCGA-OV H&E WSIs contain a modest but reproducible morphology-linked signal associated with research-grade molecular HRD status. However, the AUROC around 0.63, absence of clinical HRD assay labels, lack of genomic scar endpoints in the implemented workflow, and absence of PARPi/platinum response targets prevent clinical interpretation. This study should be interpreted as a proof-of-concept benchmarking framework and methodological foundation for future H&E-based predictive modelling in clinically curated PARPi response cohorts.

---

## 论文详细总结（自动生成）

### 0. 论文的源代码链接
无。论文未提供公开的代码仓库链接，但声明可应要求提供衍生文件、标签文件和特征提取脚本。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：同源重组缺陷（HRD）是高级别浆液性卵巢癌（HGSOC）中对铂类药物和PARP抑制剂疗效的关键预测标志，但公开数据集中缺乏同时包含H&E全切片图像、验证过的临床HRD检测结果、基因组疤痕评分、BRCA1启动子甲基化数据以及治疗结局的完整组合。这阻碍了计算病理学从常规组织学中开发临床可解释的HRD或PARPi反应模型。
- **整体含义**：本文是一项探索性、泄漏控制的计算病理学基准测试研究，旨在评估TCGA-OV的H&E WSI中是否含有与科研级分子HRD标签相关的可测量形态学信号，并检验标签细化（纳入BRCA1启动子甲基化）和病理基础模型嵌入是否改变预测性能。研究明确不声称可替代临床检测，而是为未来在临床PARPi反应队列中建模提供方法学框架和基准。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：采用患者级注意力多实例学习（ABMIL），以患者为“袋”（bag），将每张WSI切为图块后经特征提取器编码，再通过注意力聚合得到患者级预测。关键创新在于**标签细化**（从仅基于BRCA/HR基因突变标签扩展为整合BRCA1启动子甲基化的标签）和**基础模型基准比较**。
- **关键技术细节**：
  - **数据预处理**：提取TCGA-OV冷冻原发（frozen-primary）WSI共717张（来自316例患者），排除诊断性FFPE DX切片（因与冷冻原发队列患者完全重叠）。
  - **标签定义**：
    - 初始标签：仅基于BRCA1/2或HR基因突变证据（78正/238负，阳性率24.7%）。
    - 细化标签：额外整合BRCA1启动子甲基化（β值≥0.30），新增33例阳转，得到111正/205负（阳性率35.1%）。
  - **特征提取器**：6种编码器——ResNet50（ImageNet预训练）、UNI、CONCH、Virchow2、Phikon-v2、UNI2-h，分别输出不同维度特征。
  - **模型架构**：患者级ABMIL，每个患者的袋包含所有可用WSI的特征，经过注意力聚合后输出二分类概率。
  - **训练与评估**：患者级分组5折×5次重复分层交叉验证（共25折），严格按患者ID分组防止泄漏；报告AUROC、AUPRC、平衡准确率、敏感性、特异性、F1、Brier分数；使用bootstrap置信区间。

### 3. 实验设计：使用的数据集、基准、对比方法
- **数据集**：仅使用TCGA-OV的冷冻原发H&E WSI（717张，316例患者）。无外部独立验证集（DX切片因患者重叠无法用作独立集）。
- **基准（benchmark）**：无标准HRD预测基准，本文自身构建了内部评价框架（交叉验证+ bootstrap）。
- **对比方法**：
  - 6种不同编码器（ResNet50、UNI、CONCH、Virchow2、Phikon-v2、UNI2-h）在两种标签上的性能。
  - 临床基线模型：逻辑回归和随机森林（基于临床特征）。
  - 所有模型采用相同的ABMIL框架和相同的交叉验证流程。

### 4. 资源与算力
论文未明确说明GPU型号、数量或训练时长。仅提及特征提取使用编码器（如UNI2-h等）可能依赖预训练基础模型，但未提供计算资源细节。*因此，无法评估实际算力开销。*

### 5. 实验数量与充分性
- **实验数量**：主要实验包括：6种编码器 × 2种标签 = 12组ABMIL模型训练，加上2个临床基线模型。每组采用25折交叉验证，产出大量指标。此外，还有标签细化前后的比较、混淆矩阵等。
- **充分性与公平性**：实验设计较为充分——采用重复分层交叉验证、bootstrap CI、患者级泄漏控制；对比了多种基础模型和临床基线，并报告了校准阈值下的详细分类指标。不足在于：未进行外部验证（DX集无法使用），未生成注意力热图（因未保存checkpoint），未做多数据集验证；标签仅为科研级分子代理，缺乏临床HRD检测结果，因此无法评估模型在真实临床场景中的表现。

### 6. 论文的主要结论与发现
- **主要发现**：TCGA-OV的H&E WSI中存在与科研级HRD分子标签相关的适度但可重复的形态学信号。最佳模型（UNI2-h + 细化标签）AUROC为0.634（95% CI 0.571-0.698），AUPRC 0.468（高于no-skill基线0.351），平衡准确率0.597，敏感性0.532，特异性0.663。
- **标签细化影响**：纳入BRCA1启动子甲基化使阳性率从24.7%升至35.1%，改变了AUPRC基线并轻微提升了AUROC（UNI2-h从0.628升至0.634），但幅度有限。
- **基础模型比较**：UNI2-h表现最佳，Phikon-v2、Virchow2、CONCH、ResNet50及临床基线均低于此，表明编码器选择影响性能，但所有结果均远未达到临床可用阈值。
- **结论**：本研究是概念验证基准框架，而非临床HRD检测器。未来需在含有真实PARPi反应标签、基因组疤痕评分、完整临床数据的外部队列中验证。

### 7. 优点
- **严谨的泄漏控制**：患者级分组交叉验证，杜绝患者内切片泄漏，提升结果可信度。
- **明确的标签细化分析**：系统对比了仅突变标签与融合甲基化标签对模型的影响，凸显标签质量的重要性。
- **多种基础模型系统基准**：覆盖了当时主流病理基础模型（UNI系列、CONCH、Virchow2、Phikon-v2）及传统ResNet50，提供了可复现的对比。
- **透明度与可复现性**：详细记录了数据筛选、特征提取、模型评估流程，并声明可提供衍生数据和脚本。
- **诚实的性能报告**：明确承认AUROC仅0.63，不适合临床部署，强调研究局限性，避免过度宣称。

### 8. 不足与局限
- **标签局限性**：所用HRD标签仅为科研级分子代理（突变+甲基化），缺乏临床验证的HRD检测（如基因组疤痕评分LOH/TAI/LST）和PARPi反应终点，因此模型不能直接指导治疗。
- **无外部验证**：DX切片因患者重叠无法作为独立测试集，所有结果均基于内部交叉验证，泛化能力未知。
- **样本量偏小**：仅316例患者，AUROC置信区间较宽（如0.571-0.698），统计效力有限。
- **缺乏注意力热图解释**：未保存模型checkpoint，无法生成注意力热图进行病理学家审查，削弱了生物可解释性。
- **仅使用特征提取式建模**：未进行端到端WSI训练，可能限制对细微表型的表征学习。
- **计算资源未报告**：影响实验可复现性评估。

（完）
