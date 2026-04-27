---
title: "Concordia: Spatial Domain Detection via Augmented Graphs for Population-Level Spatial Proteomics"
title_zh: Concordia：通过增强图进行群体级空间蛋白质组学的空间域检测
authors: "Liu, S., Hsu, L., Sun, W."
date: 2026-04-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.19.719422v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 基于GNN的肺癌组织空间域检测框架
tldr: Concordia是一个基于图神经网络（GNN）的框架，旨在解决群体级空间蛋白质组学中空间域识别的难题。针对癌症组织复杂的几何结构，它通过增强图捕捉复杂空间特征，并能同时处理数千个样本以确保定义的一致性。在肺癌研究中，该方法成功识别出与临床结果相关的特定成纤维细胞亚群，展示了其在揭示复杂空间生物学方面的优势。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的空间域检测方法难以处理癌症组织中复杂的几何结构，且难以在跨样本的大规模群体数据中保持定义的一致性。
method: 提出Concordia框架，利用增强图和图神经网络（GNN）捕捉复杂的空间特征，并支持对数千个组织样本进行同步分析。
result: 在肺癌数据集的应用中，Concordia发现了一种仅靠蛋白质表达无法识别、但与临床预后密切相关的空间定义型癌症相关成纤维细胞亚群。
conclusion: Concordia为大规模空间蛋白质组学研究提供了一个高效工具，能够揭示具有临床意义的复杂空间结构和细胞亚群。
---

## 摘要
分析群体级空间蛋白质组学数据的关键步骤是在样本间描绘定义一致的空间域。域检测对于癌症组织尤其具有挑战性，因为癌症组织具有细长或分支几何形状的复杂空间域。为了应对这些挑战，我们提出了 Concordia，这是一个基于图神经网络 (GNN) 的框架，它利用增强图来捕捉复杂的空间域，并旨在同时分析数千个组织以获得定义一致的域。应用于肺癌数据集，Concordia 揭示了一个与临床结果相关的空间定义的癌症相关成纤维细胞子集，而仅凭蛋白质表达无法识别该子集。

## Abstract
A key step in analyzing population-level spatial proteomic data is to delineate consistently defined spatial domains across samples. Domain detection is particularly challenging for cancer tissues, which have complex spatial domains with elongated or branching geometries. To address these challenges, we present Concordia, a Graph Neural Network (GNN)-based framework that uses augmented graphs to capture complex spatial domains, and it is designed to analyze thousands of tissues simultaneously to obtain consistently defined domains. Applied to a lung cancer dataset, Concordia uncovers a spatially defined cancer associated fibroblast subset linked to clinical outcomes that cannot be identified using protein expression alone.