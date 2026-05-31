---
title: "dbGIST: An LLM-Assisted Multi-Omics Resource for Target Exploration and Cross-Dataset Validation in Gastrointestinal Stromal Tumors"
title_zh: dbGIST：一个LLM辅助的多组学资源，用于胃肠道间质瘤的靶点探索和跨数据集验证
authors: "Sun, Z., Zhao, Q., Li, J.-H., Li, J.-J., Liu, H., Guo, Y.-X., Tang, Y.-D., Yang, F., Liu, X., Peng, S.-F., Mi, W.-n., Zhang, G., Zhang, Z., Yuan, M.-L., Li, G.-H., Wang, Y.-F., Liu, C., Li, S.-L., Yang, J.-H., Fu, Y."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727292v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 胃肠道间质瘤的多组学资源
tldr: 胃肠道间质瘤（GIST）的组学证据分散在不同小样本队列中，缺乏专用数据库。dbGIST整合了来自37个中心、1991例样本的多组学数据（基因组、转录组、蛋白质组等）及临床注释，提供交互式分析与API访问，并配有LLM辅助接口。以MCM7为例，验证了其与生存、风险特征、转移及伊马替尼反应的关联。该资源为GIST靶点探索和精准肿瘤学研究提供了可追踪、可互操作的平台。
source: biorxiv
selection_source: fresh_fetch
motivation: GIST特异性多组学证据分散，缺乏专用疾病项目，限制可重复靶点探索。
method: 构建dbGIST资源，整合37中心1991样本的多组学数据及临床注释，提供交互式分析和API，附带LLM辅助接口。
result: 以MCM7为案例，验证其与生存、风险特征、转移、伊马替尼反应及体外细胞行为的关联。
conclusion: dbGIST为GIST精准肿瘤学提供可追溯、可互操作的靶点探索资源。
---

## 摘要
胃肠道间质瘤（GIST）是胃肠道最常见的间叶源性肿瘤，然而GIST特异性的组学证据仍分散于小规模队列中，且未作为独立疾病项目被纳入主要癌症基因组学资源，这限制了可重复的靶点探索。在此，我们提出dbGIST（https://www.dbgist.com），这是一个专为GIST构建的多组学资源，旨在使分散的GIST证据变得可搜索、可分析和可重复利用。dbGIST整合了来自37个中心和1,991个样本的数据，包括经病理验证的内部队列，涵盖基因组学、批量转录组学、蛋白质组学、磷酸化蛋白质组学和单细胞转录组学，并将这些数据与精心整理的临床注释（包括生存、突变状态、风险分层、转移或复发、有丝分裂指数、肿瘤部位和大小以及伊马替尼反应）相结合。该平台通过交互式可视化、可下载的源数据以及用于程序化访问可重复利用分析结果和可视化数据的公共API，支持队列水平的分子-临床关联、生存、富集、免疫浸润、药物敏感性和单细胞分析。可选的LLM辅助界面帮助用户导航分析和解读输出。以MCM7为例，dbGIST将资源衍生的候选基因与生存、风险特征、转移或复发疾病、伊马替尼反应表型、增殖细胞状态以及体外GIST细胞行为联系起来。因此，dbGIST为GIST的靶点探索和精准肿瘤学研究提供了一个可追踪和可互操作的资源。

## Abstract
Gastrointestinal stromal tumors (GISTs) are the most common mesenchymal neoplasms of the gastrointestinal tract, yet GIST-specific omics evidence remains scattered across small cohorts and is not represented as a dedicated disease project in major cancer genomics resources, limiting reproducible target exploration. Here, we present dbGIST (https://www.dbgist.com), a dedicated GIST-focused multi-omics resource built to make dispersed GIST evidence searchable, analyzable, and reusable. dbGIST harmonizes data from 37 centers and 1,991 samples, including pathologically verified in-house cohorts, across genomics, bulk transcriptomics, proteomics, phosphoproteomics, and single-cell transcriptomics, and couples these data with curated clinical annotations covering survival, mutation status, risk stratification, metastasis or recurrence, mitotic index, tumor site and size, and imatinib response. The platform supports cohort-level molecular-clinical association, survival, enrichment, immune-infiltration, drug-sensitivity, and single-cell analyses through interactive visualizations, downloadable source data, and public APIs for programmatic access to reusable analysis outputs and visualization-ready data. An optional LLM-assisted interface helps users navigate analyses and interpret outputs. Using MCM7 as a case study, dbGIST linked a resource-derived candidate to survival, risk features, metastatic or recurrent disease, imatinib-response phenotypes, proliferative cell states, and in vitro GIST-cell behavior. dbGIST therefore provides a traceable and interoperable resource for target exploration and precision oncology research in GIST.