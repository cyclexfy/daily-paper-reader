---
title: Hierarchical classification of hematologic malignancies using epigenetic and genetic information
title_zh: 利用表观遗传和遗传信息对血液恶性肿瘤进行分层分类
authors: "Schönung, M., Türe, M., Lajer, P., Renders, S., Rausch, T., Steinicke, T. L., Dolnik, A., Sträng, E., Oak, M. S., Heilmann, J., Roth, K., Katzenstein, L., Rohde, C., Sollier, E., Horak, P., Sauer, T., Strefford, J. C., Duran-Ferrer, M., Oakes, C. C., Martin-Subero, J. I., Germing, U., Dworzak, M., Catala, A., Flotho, C., Niemeyer, C. M., Döhner, H., Hovestadt, V., Fröhling, S., Schlenk, R. F., Heidel, F. H., Korbel, J., Gerhäuser, C., Hartmann, M., Müller-Tidow, C., Lutsik, P., Hundemer, M., Erlacher, M., Bullinger, L., Plass, C., Lipka, D. B."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.735835v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 利用表观遗传和遗传数据通过机器学习进行癌症诊断
tldr: 血液恶性肿瘤的分子检测方法不标准化，导致结果差异。本研究开发了一种结合表观遗传和遗传数据的分层分类框架，利用全基因组纳米孔测序和机器学习，基于5420份样本的DNA甲基化数据训练分类器，可诊断21种疾病实体，并进一步预测44种治疗相关亚型。结合遗传分析后，检测准确度高，并能发现标准方法遗漏的关键分子改变。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1674, \"height\": 1747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1620, \"height\": 1151, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1658, \"height\": 2107, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1620, \"height\": 2374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1665, \"height\": 870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1597, \"height\": 2375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1610, \"height\": 614, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1667, \"height\": 969, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 861, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1606, \"height\": 2253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1648, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735835-v1/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1583, \"height\": 524, \"label\": \"Figure\"}]"
motivation: 现有分子检测方法不统一，需开发单一检测实现疾病分类、风险分层和用药指导。
method: 使用全基因组纳米孔测序数据，结合DNA甲基化与突变信息，训练分层机器学习分类器。
result: 在5420样本上实现21种血液肿瘤实体分类及44种亚型预测，准确率高，检出标准法漏检的变异。
conclusion: 该单一检测框架可替代多种分子检测，统一血液肿瘤的分子诊断流程。
---

## 摘要
血液学中的分子检测需要不同的检测方法来进行疾病亚组识别、风险分层和选择合适的治疗方案。然而，诊断实验室之间的分子检测并不一定标准化，导致周转时间不一且可能产生分歧的结果。为解决这一问题并实现单一检测的分子检测，我们开发了一个分层分类框架，该框架结合了来自全基因组纳米孔测序（WGNS）的表观遗传和遗传数据与机器学习，以确定造血肿瘤的疾病实体、表观遗传亚组（表型）和遗传异常。我们整理了来自5,420个样本的DNA甲基化数据，并训练了一个分类器，允许实体级诊断，涵盖21种条件，包括健康对照、急性和慢性髓系及淋巴系肿瘤。随后，该分类器与实体特异性表型分类器相结合，预测44种治疗或预后相关状态，然后整合遗传数据。使用WGNS对联合（表观）遗传检测策略进行基准测试证实了在诊断组检测和风险分层方面的高准确性，并识别出了标准诊疗工作流程未报告的诊断定义分子改变。

## Abstract
Molecular testing in hematology requires different assays for disease subgroup identification, risk stratification and selection of appropriate treatment regimens. Yet, molecular tests are not necessarily standardized between diagnostic laboratories, resulting in varying turnaround times and potentially divergent results. To resolve this issue and enable single-assay molecular testing, we have developed a hierarchical classification framework that combines epigenetic and genetic data from whole genome nanopore sequencing (WGNS) with machine learning to determine disease entities, epigenetic subgroups (epitypes) and genetic aberrations in hematopoietic neoplasms. We curated DNA methylation data from 5,420 samples and trained a classifier allowing entity-level diagnostics featuring 21 conditions, including healthy controls, acute and chronic myeloid and lymphoid neoplasms. This classifier was subsequently combined with entity-specific epitype classifiers predicting 44 therapeutically or prognostically relevant states, followed by integration of genetic data. Benchmarking of the combined (epi-)genetic testing strategy using WGNS confirmed high accuracy in the detection of diagnostic groups and risk stratification, and identified diagnosis-defining molecular alterations that were not reported by standard-of-care work-up.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的详细中文总结。

0. **论文的源代码链接**：
   *   有，GitHub 仓库：`https://github.com/MaxSchoenung/nanoleukemia`

1. **论文的核心问题与整体含义（研究动机和背景）**：
   *   **背景**：在血液恶性肿瘤的分子诊断中，通常需要多种不同的检测方法（如靶向测序、核型分析、PCR等）来完成疾病亚组识别、风险分层和治疗方案选择。然而，这些方法在不同实验室间缺乏标准化，导致周转时间不一、结果可能产生分歧。
   *   **核心问题**：如何利用单一检测平台，快速、准确、标准化地整合表观遗传（DNA甲基化）和遗传（突变、结构变异）信息，一次性完成对血液恶性肿瘤的疾病实体诊断、表观遗传亚型（epitype）分类和遗传异常检测。
   *   **整体含义**：该研究旨在开发一个**分层分类框架**，通过结合**全基因组纳米孔测序（WGNS）** 和机器学习，建立一个统一的分子诊断平台，以替代目前繁琐的多重检测流程，提高诊断效率和准确性，尤其适用于需要快速诊断的临床场景。

2. **论文提出的方法论**：
   *   **核心思想**：采用**分层分类**策略。首先，基于DNA甲基化数据建立一个**广义的实体分类器**，将样本归类到21种疾病实体（包括健康对照）中的某一类。然后，根据实体分类的结果，自动选择并应用**针对该实体的特异性表观亚型（epitypes）分类器**，以预测预后或治疗相关的亚型（共44种）。最后，整合来自WGNS的遗传信息（突变、结构变异、拷贝数变异）进行综合诊断和风险分层。
   *   **关键技术细节**：
       1.  **数据收集与预处理**：收集了47个公共数据集共7,053个样本，经过严格质控后保留5,420个样本（3,796个肿瘤样本和1,624个对照）。涵盖了20种血液肿瘤和健康对照。
       2.  **实体分类器训练**：基于5,420个样本的DNA甲基化阵列数据，选择12,627个高变异CpG位点作为特征。使用**极端梯度提升（XGBoost）** 模型进行多分类训练。通过超参数调优和特征选择，最终模型使用**932个CpG位点**。设定了两个概率阈值：**Tier-1（0.972）** 和 **Tier-2（0.85）**，分别对应最高准确率（99.4%）和覆盖率（91%）的平衡。
       3.  **亚型分类器**：针对不同疾病（如B-ALL、CLL、JMML）使用不同的模型。B-ALL使用随机森林（MARLIN-RF），CLL使用XGBoost，JMML也使用XGBoost。这些亚型分类器在实体分类结果基础上运行。
       4.  **WGNS数据集成**：为了兼容WGNS数据（通常为二值化甲基化调用），训练了一个基于二值化甲基化标记的XGBoost实体分类器。遗传分析（SNV、SV、CNV、FLT3-ITD）使用专门的生物信息学流程（如ClairS-TO、delly、Severus、QDNAseq等）。

3. **实验设计**：
   *   **数据集/场景**：
       *   **训练集**：从公共数据库和内部数据收集的5,420个样本（甲基化阵列数据），其中3,844个用于训练，958个用于测试。
       *   **独立验证队列**：
           *   B-ALL：133例（GSE56600）
           *   CLL：706例
           *   JMML：114例（EWOG-MDS研究组）
           *   WGNS技术验证：20例（15例AML，3例JMML，2例对照）
           *   WGNS独立验证：59例（包含AML、ALL、CLL，来自不同中心）
       *   **基准测试队列**：45例AML患者（来自ASTRAL-1试验等）。
   *   **Benchmark**：**标准诊疗（SOC）**，包括靶向基因panel测序、核型分析和PCR/qPCR。
   *   **对比的方法**：主要与SOC在疾病诊断分组（WHO 5th）和风险分层（ELN2022）上的一致性进行比较，并比较WGNS与SOC在检测基因突变、结构变异和拷贝数变异方面的能力。没有与其他分类器或算法进行直接比较。

4. **资源与算力**：
   *   **文中未明确说明**。研究主要使用了XGBoost和随机森林等传统的机器学习模型，训练过程可能不需要大规模GPU集群。文中未提及GPU型号、数量或训练时长。

5. **实验数量与充分性**：
   *   **实验数量**：实验较为充分。包括：
       *   内部测试集测试（n=958）。
       *   三个独立队列（B-ALL、CLL、JMML）的验证，每个队列样本量均超过100。
       *   WGNS技术验证（n=20）和实时分类能力测试。
       *   与SOC的盲法基准测试（n=45），对诊断分组和风险分层进行了详细比较。
       *   消融分析：使用不同概率阈值（Tier-1/Tier-2）分析分类器性能。
   *   **充分性/公平性**：实验设计较为严谨，使用了独立的外部验证队列，且基准测试采用盲法并与当前临床标准（SOC）比较。但在与SOC的比较中，WGNS的检测灵敏度（特别是低VAF突变）低于深度panel测序，这种差异在文中被指出并解释。实验整体上客观地展示了新方法效能。不过，未与其他新兴的甲基化分类模型（如MARLIN本身）进行公平比较。

6. **论文的主要结论与发现**：
   *   开发并验证了一个基于DNA甲基化的**分层分类框架**，能高准确率（Tier-1阈值下99.4%）地将血液肿瘤样本分类到21种疾病实体中。
   *   该框架可无缝对接**后续的表观亚型分类**，成功识别了B-ALL、CLL和JMML的预后相关亚型。
   *   该分类器适用于**WGNS数据**，并且可以在测序开始后数小时内获得正确的实体分类结果，具备快速诊断潜力。
   *   在AML患者中，**WGNS+表观遗传分类**的联合策略在WHO诊断分组（91.7%一致）和ELN2022风险分层（97.2%一致）上与SOC高度一致。
   *   **关键发现**：该方法能检测到SOC遗漏的诊断性分子变异，例如一个**NUP98::NSD1基因融合**，该发现后来被验证为真正的治疗相关改变。

7. **优点**：
   *   **创新性**：首次提出并验证了从实体诊断到亚型分类再到遗传整合的**单平台分层诊断策略**，为血液肿瘤的精准诊断提供了新范式。
   *   **实用性**：结合WGNS技术，实现了**快速、全面、标准化的分子诊断**，有望简化临床工作流程，缩短诊断时间。
   *   **综合性强**：将表观遗传学与遗传学信息有效整合，能提供更全面的疾病图谱，并发现SOC可能遗漏的**重要变异**。
   *   **稳健性**：在多个独立队列和不同技术平台（甲基化芯片、WGNS）上验证了分类器的准确性和鲁棒性。

8. **不足与局限**：
   *   **训练数据偏差**：训练数据集中的疾病分类高度依赖于公共数据集的注释，可能存在标注错误或诊断标准演变带来的不一致性。
   *   **覆盖率问题**：对于低肿瘤细胞含量的样本、治疗后的样本或未包含在训练集中的罕见疾病亚型，分类器的预测概率可能较低，导致被标记为“未知”。
   *   **灵敏度局限**：在遗传检测方面，WGNS对低频VAF的单个核苷酸变异（SNV）的检测灵敏度低于靶向panel测序。虽然通过增加覆盖度可以改善，但这会带来更高的成本。
   *   **前瞻性验证缺失**：本研究主要为回顾性分析，缺少前瞻性临床试验来评估其在真实世界临床应用中的性能和对患者预后的影响。

（完）
