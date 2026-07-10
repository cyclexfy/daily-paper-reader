---
title: Foundation Model RNAGAN Enhances Biomedical Insight of Nasopharyngeal Carcinoma Metastasis
title_zh: 基础模型RNAGAN增强鼻咽癌转移的生物医学洞察
authors: "Hou, Z., Qian, Y., Lee, V. H.-F., Kwong, D. L.-W., Guan, X., Liu, Z., Dai, W."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.736240v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 基础模型RNAGAN应用于鼻咽癌研究
tldr: 鼻咽癌（NPC）转移机制研究缺乏有效分析工具。本文利用基础模型RNAGAN（无需NPC训练数据）对单细胞/RNA测序样本进行样本分层、向量化、伪数据生成和标记识别，分析NPC转移。结果表明，RNAGAN在预测转移风险方面与已有模型相当或更优，且识别的转移相关基因与多队列真实数据高度一致（p=1.05e-9）。更重要的是，RNAGAN揭示了S100A8/IL21R空间共定位是预测治疗响应的关键标志，适应性免疫可抑制慢性炎症驱动的转移，为NPC免疫治疗提供了新见解。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736240-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1342, \"height\": 754, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736240-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1343, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736240-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 698, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736240-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1006, \"height\": 701, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736240-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 741, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736240-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 750, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736240-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1164, \"height\": 1937, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736240-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 3125, \"height\": 1398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736240-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 1779, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736240-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1648, \"height\": 382, \"label\": \"Table\"}]"
motivation: 利用无需额外训练的基础模型RNAGAN，在鼻咽癌这一新型癌症类型中揭示转移的分子机制和生物标记。
method: 将RNAGAN以in-context few-shot形式应用于NPC数据，执行样本分层、向量化、伪数据生成和标记识别四种功能。
result: RNAGAN在转移风险预测、跨队列一致性、单/多队列DE分析中表现优异，并发现S100A8/IL21R空间共定位与治疗响应严格相关。
conclusion: RNAGAN作为基础模型可有效挖掘新癌症类型的治疗见解，揭示了适应性免疫通过空间共定位抑制先天炎症驱动的NPC转移。
---

## 摘要
RNAGAN（版本2.0，https://github.com/ZhaozhengHou-HKU/RNAGAN-2.0.git）是一个已发布的基础模型，用于分析单细胞和整体水平的RNA测序样本，并支持多种增强医学洞察的应用。本文我们将该模型以上下文少样本格式（即模型从未使用任何NPC数据进行训练）应用于鼻咽癌（NPC）。我们执行了所有四项支持功能，包括样本分层、向量化、伪数据生成和标记物识别。随后将结果用于识别转移性NPC，并研究NPC转移相关的机制。

通过分层检查表明，RNAGAN评估NPC患者转移风险的结果准确性与最近发表的风险估计线性预测模型相当或更优。向量化结果在多个队列和RNAGAN模型版本之间呈现一致性。在识别与NPC转移相关的标记物和机制任务中，整合伪数据显著增强了基于单队列差异表达（DE）分析的代表性。此外，RNAGAN基于单队列识别出的转移相关标记基因与跨多个队列获得的真实情况一致（p=1.05e-9）。

在生物医学机制方面，RNAGAN实现了二阶特征提取，揭示了一线治疗后适应性免疫应答的保护功能（由IL21R水平指示）相对于慢性、非消退性先天炎症的危害功能（由S100A8水平指示）在对抗NPC转移中的显著主导地位。这种关联与外部队列表现出高度一致性。

本研究证明了基础模型RNAGAN在无需额外训练的情况下，为新型癌症类型揭示治疗见解的实用性。我们揭示了NPC中通过体液抗肿瘤免疫防止远处转移的关键空间机制。先天抗原呈递细胞（APC）高表达S100A8触发炎症级联反应，促进上皮间质转化（EMT）和转移。然而，当生发中心IL21R+ B细胞同时与这些先天信号共定位时，它们会压制这种抑制性组织应激。空间分析显示，肿瘤区域内高S100A8/IL21R交集严格区分治疗应答者，而无应答者则表现出空间错配或S100A8+过度浸润。这种协调的先天-适应性交叉对话维持了功能性三级淋巴结构（TLS），这些TLS促使分泌IgG的浆细胞成熟，在系统性逃逸之前调理并清除新出现的EMT肿瘤细胞。因此，虽然单独的S100A8不是可靠的预后因子，但其与IL21R的空间共定位是一个被传统整体分析方法忽略的强保护性指标。

## Abstract
RNAGAN (version 2.0, https://github.com/ZhaozhengHou-HKU/RNAGAN-2.0.git) is a published foundation model that analyzes single-cell and bulk-level RNA sequencing samples and enables multiple applications that enhance medical insights. Here we applied this model to Nasopharyngeal Carcinoma (NPC) as in-context few-short format (i.e., the model was never trained with any NPC data). We conducted all four supported functions, which include sample stratification, vectorization, pseudo data generation, and marker identification. The results were then used for identifying metastatic NPC and to investigate mechanisms associated with NPC metastasis.

Examination with stratification showed that the accuracy of RNAGAN results for evaluating the metastasis risk in NPC patients are comparable to or outcompeted recently published risk estimation linear prediction model. Vectorization results present consistency across multiple cohorts and RNAGAN model versions. In the task of identifying markers and mechanisms related to NPC metastasis, incorporating pseudo data substantially enhanced the representativeness of single-cohort-based differential expression (DE) analysis. Moreover, RNAGAN identified metastasis-related marker genes based on single cohort, were concordant with the ground truth obtained across multiple cohorts (p=1.05e-9).

Regarding biomedical mechanisms, RNAGAN enabled second-order feature extraction, unveiling a remarkable domination of the protective function of adaptive immune responses (as indicated by IL21R levels) over the hazardous function of chronic, non-resolving innate inflammation (as indicated by S100A8 levels) against NPC metastasis after first-line treatment. This association demonstrates a high degree of consistency with the external cohort.

This study demonstrates the utility of the foundation model RNAGAN in uncovering therapeutic insights for novel cancer types without extra training. We reveal a critical spatial mechanism preventing distant metastasis via humoral anti-tumor immunity in NPC. High S100A8 expression by innate antigen-presenting cells (APCs) triggers an inflammatory cascade promoting epithelial-mesenchymal transition (EMT) and metastasis. However, when germinal center IL21R+ B cells simultaneously colocalize with these innate signals, they override this suppressive tissue stress. Spatial analysis shows that a high S100A8/IL21R intersection within tumor regions strictly distinguishes treatment responders, whereas non-responders display spatial mismatch or S100A8+ hyper-infiltration. This coordinated innate-adaptive cross-talk sustains functional tertiary lymphoid structures (TLS) that mature IgG-secreting plasma cells, which opsonize and eliminate emerging EMT tumor cells before systemic escape. Consequently, while S100A8 alone is an unreliable prognosticator, its spatial colocalization with IL21R is a robust protective indicator overlooked by conventional bulk analysis methods.