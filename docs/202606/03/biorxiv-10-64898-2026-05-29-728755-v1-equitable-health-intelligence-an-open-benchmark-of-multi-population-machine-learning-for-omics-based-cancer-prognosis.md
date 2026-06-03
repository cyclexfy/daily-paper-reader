---
title: "Equitable Health Intelligence: An Open Benchmark of Multi-Population Machine Learning for Omics-Based Cancer Prognosis"
title_zh: 公平健康智能：面向组学癌症预后的多人群机器学习开放基准
authors: "Sharma, T., Chopra, A. P., Agrawal, L., Verma, N. K., Starlard-Davenport, A., Wang, J., Hayes, D. N., Cui, Y."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728755v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 多群体组学癌症预后基准
tldr: 现有机器学习模型在基于组学的癌症预后中对欧洲血统以外人群存在预测性能偏差，而公平性基准多关注结果平等。为此，我们构建了EHI开源基准，包含1475个ML任务，覆盖40种癌症类型、4种组学特征和4种临床终点，训练了10325个模型，评估混合、独立及迁移学习等方案。结果表明迁移学习可部分缓解性能差异。EHI提供交互平台，有助于检测和解决多群体性能不平等，推动精准肿瘤学公平AI的发展。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有组学癌症预后模型对非欧洲血统人群预测性能差，缺乏系统公平性基准。
method: 构建EHI基准，含1475个ML任务，采用深度神经网络在三种多群体ML方案下训练。
result: 通过10325个实验揭示性能差异，迁移学习可缓解部分差异。
conclusion: EHI作为开放基准可评估并解决多群体ML性能不平等，促进公平精准肿瘤学。
---

## 摘要
目的：基于组学的癌症预后机器学习模型通常使用主要来自欧洲血统人群的数据进行训练，从而对其他人群产生有偏见的预测，有损公平的基因组医学。现有公平性基准主要关注结果均等性而非各人群间的预测性能均等性。亟需公共基准资源来系统性地检测和减轻多人群癌症预后中的此类性能差异。方法：我们开发了公平健康智能（EHI, https://ehiportal.org），这是一个面向组学癌症预后的多人群机器学习开源基准。EHI包含1,475项机器学习任务，涵盖40种癌症/泛癌类型、4组组学特征集、4个临床终点、5个事件时间阈值，以及相对于多数欧洲血统人群的3个数据弱势人群群体。深度神经网络模型在三种多人群机器学习方案（混合、独立和迁移学习）下训练，并包含朴素迁移作为无自适应对照，共计10,325次机器学习实验。结果：EHI平台提供了一个交互式环境，配备可视化和探索工具，使用户能够检查多数欧洲血统人群与数据弱势人群之间的预测性能差异，评估迁移学习减轻这些差异的程度，并检查特征工程方法在不同癌症类型、组学特征和临床终点上的影响。结论：EHI是一个开放、可交互、可扩展的基准，用于识别和解决面向组学癌症预后的多人群机器学习中的性能差异。它为应对因生物医学数据不平等和人群水平分布偏移导致的机器学习性能差异的方法不断增长的生态系统奠定了基础，从而推动精准肿瘤学中的公平人工智能。

## Abstract
Purpose: Machine learning (ML) models for omics-based cancer prognosis are often trained on data from predominantly European-ancestry populations, producing biased predictions for other populations and undermining equitable genomic medicine. Existing fairness benchmarks mainly focus on outcome parity rather than predictive performance parity across populations. Public benchmark resources are needed for systematically detecting and mitigating such performance disparities in multi-population cancer prognosis. Methods: We developed Equitable Health Intelligence (EHI, https://ehiportal.org), an open-source benchmark of multi-population ML for omics-based cancer prognosis. EHI contains 1,475 ML tasks across 40 cancer/pan-cancer types, 4 omics feature sets, 4 clinical endpoints, 5 event-time thresholds, and 3 data-disadvantaged population (DDP) groups relative to a majority European Ancestry population group. Deep neural network models are trained under three multi-population ML schemes (Mixture, Independent, and Transfer Learning), with Naive Transfer included as a no-adaptation control, comprising a total of 10,325 ML experiments. Results: The EHI platform provides an interactive environment with visualization and exploratory tools for users to inspect predictive performance disparities between the majority European-ancestry group and data-disadvantaged populations, evaluate the extent to which transfer learning mitigates these disparities, and examine the impact of feature engineering methods across cancer types, omics features, and clinical endpoints. Conclusion: EHI is an open, interactive, and extensible benchmark for identifying and addressing performance disparities in multi-population ML for omics-based cancer prognosis. It provides a foundation for a growing ecosystem of methods targeting ML performance disparities arising from biomedical data inequality and population-level distribution shifts, thereby advancing equitable AI in precision oncology.

---

## 论文详细总结（自动生成）

### 0. 论文的源代码链接
无（论文未提供源代码链接）。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有基于组学（omics）的癌症预后机器学习模型主要使用欧洲血统人群的数据进行训练，导致对非欧洲血统人群（尤其是数据弱势群体）的预测性能出现显著下降，损害了精准肿瘤学的公平性。
- **背景**：现有公平性基准多关注“结果均等性”（如不同群体间预测错误率相等），而非“预测性能均等性”（即模型在不同人群中的判别能力、校准度等指标的一致性）。缺乏系统、公开的基准资源来检测和减轻多人群癌症预后中的性能差异。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：构建开源、可交互、可扩展的基准（Equitable Health Intelligence, EHI），系统性地评估和缓解组学癌症预后模型在不同人群间的性能差异。
- **关键技术细节**：
  - **任务构建**：包含1,475个机器学习任务，覆盖：
    - 40种癌症类型（含泛癌类型）
    - 4种组学特征集（如基因表达、甲基化、突变等）
    - 4个临床终点（如总生存期、无病生存期等）
    - 5个事件时间阈值（用于时间-事件预测的截断点）
    - 3个数据弱势群体（DDP，相对于多数欧洲血统人群）
  - **模型训练**：采用深度神经网络（DNN），在三种多人群机器学习方案下训练：
    - **混合方案**（Mixture）：将所有人群数据合并训练单一模型。
    - **独立方案**（Independent）：分别对每个群体单独训练模型。
    - **迁移学习方案**（Transfer Learning）：先在多数欧洲血统人群上训练，再向数据弱势群体进行微调/自适应。
    - **朴素迁移**（Naive Transfer）：作为无自适应对照（即直接用欧洲血统模型预测其他群体）。
  - **平台功能**：提供交互式可视化与探索工具，允许用户检查性能差异、评估迁移学习缓解差异的程度、分析特征工程方法的影响。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：未明确说明具体数据来源（如TCGA等），但提到涵盖40种癌症类型和多种组学特征，推测基于公开的癌症基因组学数据库。
- **基准**：自身构建的EHI基准，包含1,475个ML任务。
- **对比方法**：
  - 三种多人群方案（混合、独立、迁移学习）之间互相对比。
  - 朴素迁移作为无迁移的基线。
  - 另外可能还考察了不同特征工程方法（如特征选择、归一化等）的影响。

### 4. 资源与算力
- **文中未明确说明**使用的GPU型号、数量、训练时长等算力信息。仅提到共进行10,325次机器学习实验，未提及具体硬件资源消耗。

### 5. 实验数量与充分性
- **实验数量**：总计10,325次机器学习实验（1,475个任务 × 多种方案和设置）。
- **充分性评估**：实验规模较大，覆盖多种癌症类型、组学特征、临床终点和人群分组，可以认为比较充分；但缺乏跨数据集的外部验证（例如在完全独立的人群队列上测试），可能影响泛化性。公平性评估主要基于EHI内部划分，未涉及更多外部数据集。

### 6. 论文的主要结论与发现
- 在多数欧洲血统人群与数据弱势群体之间存在显著的预测性能差异。
- **迁移学习**能够部分缓解这些性能差异，但无法完全消除。
- EHI平台提供了有效的工具来检测和可视化这些差异，为后续研究公平性方法提供了基础。
- 该基准为应对生物医学数据不平等和人群水平分布偏移带来的性能差异奠定了基础，有助于推动精准肿瘤学中的公平AI。

### 7. 优点：方法或实验设计上的亮点
- **系统性强**：覆盖大量任务（40种癌症、4种组学、4个终点），形成全面基准。
- **关注性能均等性**：不同于传统公平性基准仅关注结果均等，此处直接衡量预测性能差异，更贴合临床需求。
- **交互式平台**：提供EHI门户（https://ehiportal.org），便于其他研究者探索和验证。
- **开源可扩展**：允许未来新增方法、人群、数据等。
- **对比多种方案**：混合、独立、迁移学习三种范式均有评估，并设朴素迁移作为基线，设计合理。

### 8. 不足与局限
- **数据来源单一**：可能主要基于TCGA等公开数据库，其本身人群组成偏欧洲血统，数据弱势群体样本量可能过小，导致统计效力不足。
- **缺乏外部验证**：未在完全独立的、非构建数据库中出现的人群队列上进行验证，泛化性存疑。
- **仅使用深度神经网络**：未对比其他经典机器学习方法（如随机森林、Cox回归等），方法覆盖不够全面。
- **未深入分析偏差来源**：未区分性能差异是因样本数量不足、分布偏移还是生物学差异（如人群特异性遗传变异）造成。
- **资源算力信息缺失**：不利于后续复现或估算成本。
- **未涉及联邦学习等隐私保护方案**：迁移学习虽被评估，但更先进的分布式学习范式未被探讨。

（完）
