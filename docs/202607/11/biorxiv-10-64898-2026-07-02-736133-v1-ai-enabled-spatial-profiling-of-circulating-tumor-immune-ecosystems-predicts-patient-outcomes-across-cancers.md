---
title: AI-enabled Spatial Profiling of Circulating Tumor-Immune Ecosystems Predicts Patient Outcomes Across Cancers
title_zh: AI驱动的循环肿瘤-免疫生态系统空间分析预测跨癌种患者预后
authors: "Squires, J. R., Sun, Y., Hoffmann, A., Zhang, Y., Pan, H., Tong, F., He, Y., Scholten, D., Almubarak, H., Gurley, M., Minor, A., Singh, A., Zhang, J., Ding, H., Mao, C., Platanias, L. C., Yu, J., Hussain, M., Luo, Y., Gradishar, W. J., Cristofanilli, M., Cooper, L. A. D., Zhao, L., Fang, D., Stringer, C., Liu, H."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.736133v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 基于AI的循环肿瘤-免疫生态系统空间分析用于癌症预后
tldr: 循环肿瘤细胞与免疫细胞在血液中形成动态多细胞生态系统，但空间组织与临床相关性尚不明确。我们开发了基于AI的CCIP框架，自动分析多重免疫荧光血片，识别细胞类型并量化多细胞簇及肿瘤-免疫互作。在2693张血片、1399名患者中分析超6000万细胞，14个影像特征模型可预测乳腺癌总生存期，优于传统临床变量和CTC计数，并推广至前列腺癌。研究连接了循环肿瘤免疫架构与全身免疫功能障碍，为无创预后评估提供新方法。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736133-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 2160, \"height\": 2135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736133-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1908, \"height\": 2610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736133-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 2116, \"height\": 2746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736133-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1862, \"height\": 1098, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736133-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 2017, \"height\": 2741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736133-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 2207, \"height\": 2795, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736133-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1677, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736133-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1878, \"height\": 969, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736133-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1862, \"height\": 1098, \"label\": \"Table\"}]"
motivation: 循环肿瘤细胞与免疫细胞在血液中的空间组织及临床意义尚未被系统表征，亟需自动化工具量化肿瘤-免疫微环境。
method: 开发AI框架CCIP，对多重免疫荧光血片进行细胞分割、六类细胞识别、多细胞簇及互作量化，分析超6000万细胞。
result: 14个影像特征模型在乳腺癌中预测总生存期优于传统变量，泛化至前列腺癌，并与治疗响应及免疫抑制状态相关。
conclusion: 基于AI的血液空间分析可无创评估肿瘤免疫状态，为多癌种预后和治疗监测提供新工具。
---

## 摘要
循环肿瘤细胞（CTCs）和免疫细胞在血液中形成动态的多细胞生态系统，但其空间组织及临床相关性尚未被系统表征。我们开发了细胞和聚类识别程序（CCIP），这是一种基于人工智能的框架，能够分析常规多重免疫荧光血液扫描，高精度地分割细胞、识别CTCs及五种免疫谱系，并量化多细胞簇及肿瘤-免疫相互作用。将CCIP应用于来自1,399名患者的2,693份血液扫描，我们分析了超过6000万个细胞（>700万个多细胞簇），并将影像衍生特征与患者预后联系起来。与循环肿瘤DNA突变负荷相关的一个14特征图像模型预测了乳腺癌的总生存期，优于临床病理变量和CTC计数，并泛化至前列腺癌。预后影像特征还与治疗反应相关的无进展生存期以及单细胞RNA测序衍生的免疫抑制状态相关，将循环肿瘤-免疫结构与系统性免疫功能障碍联系起来。

## Abstract
Circulating tumor cells (CTCs) and immune cells form dynamic multicellular ecosystems in blood, but their spatial organization and clinical relevance have not been systematically characterized. We developed the Cell and Cluster Identification Program (CCIP), an artificial intelligence-based framework that analyzes routine multiplex immunofluorescence blood scans to segment cells, identify CTCs and five immune lineages with high accuracy, and quantify multicellular clusters and tumor-immune interactions. Applying CCIP to 2,693 blood scans from 1,399 patients, we profiled over 60 million cells (>7 million multi-cell clusters) and linked imaging-derived features to patient outcomes. Correlated with circulating-tumor DNA mutation burdens, a 14-feature image model predicted overall survival in breast cancer, outperformed clinicopathologic variables and CTC enumeration, and generalized to prostate cancer. Prognostic imaging signatures were also associated with therapy response-related progression-free survival as well as with single-cell RNA sequencing-derived immune suppression states, connecting circulating tumor-immune architecture with systemic immune dysfunction.