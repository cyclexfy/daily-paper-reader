---
title: "Semi supervised GAN for smart microscopy, fast and data efficient cell cycle classification"
title_zh: 用于智能显微镜的半监督生成对抗网络：快速且数据高效的细胞周期分类
authors: "Manick, R., El Habouz, Y., Guillout, M., Martin, C., Bonnet-gelebart, J., Ruel, L., Pastezeur, S., Chanteux, O., Bouchareb, O., Tramier, M., Pecreaux, J."
date: 2026-04-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.23.720294v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 用于显微镜细胞分类的半监督生成对抗网络
tldr: 本研究针对智能显微镜实时分析中对大规模标注数据依赖的问题，提出了一种半监督生成对抗网络（SGAN）框架。该方法通过结合少量标注图像、未标注图像及合成样本，实现了高效且稳健的细胞周期阶段分类。在Mitocheck数据集上的实验表明，该模型在极低标注量下仍能保持高准确率，且具有良好的通用性和可迁移性，为自动化显微成像提供了高效的数据处理方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的显微图像分类算法通常需要大量标注数据且通用性较差，难以满足智能显微镜实时、灵活的分析需求。
method: 提出一种半监督生成对抗网络（SGAN），通过整合未标注图像和合成样本来增强模型在低资源条件下的分类性能。
result: "在仅使用每类80张标注图像和600张未标注图像的情况下，模型在Mitocheck有丝分裂五分类任务中达到了93%的准确率。"
conclusion: 该SGAN框架具有高效、稳健且易于迁移的特点，非常适合集成到自动化显微镜系统中以实现多样化的生物图像分析。
---

## 摘要
现代光学显微镜已实现全面电动化；然而，将其转化为真正的智能系统需要根据检测到的对象和动态生物事件实时调整采集设置。其核心是分类算法，这些算法通常依赖于定制软件，且通常针对定义狭窄的生物应用而设计。此外，它们往往需要大量的标注数据集进行有效训练。我们引入了一种半监督生成对抗网络（SGAN），用于在低资源条件下进行鲁棒的细胞周期阶段分类，并可适应多种细胞结构。该框架将未标记的显微图像与合成生成的样本相结合，以缓解标注受限的问题，同时即使在未标记子集存在类别不平衡的情况下也能保持稳定的性能。在具有五个有丝分裂类别的 Mitocheck 数据集上进行的测试表明，该模型仅使用每类 80 张标记图像和 600 张未标记图像，就达到了 93±2% 的准确率。所提出的算法具有通用性，可以通过迁移学习轻松适应新的标记方案、分类目标、细胞系或显微成像模式。SGAN 非常适合集成到自动化显微镜中，从而在各种生物和显微应用中实现高效且适应性强的图像分析。

## Abstract
Modern optical microscopes are fully motorised; however, transforming them into truly smart systems requires real-time adjustment of acquisition settings in response to detected objects and dynamic biological events. At the core are classification algorithms that commonly depend on customised softwares and are generally designed for narrowly-defined biological applications. In addition, they often require substantial annotated datasets for effective training. We introduce a semi-supervised generative adversarial network (SGAN) for robust cell-cycle stage classification under low-resource conditions, adaptable to diverse cellular structures. The framework combines unlabelled microscopy images with synthetically generated samples to mitigate limited annotation, while preserving stable performance even when the unlabelled subset is class-imbalanced. Tested on the Mitocheck dataset, which features five mitosis classes, the model achieved 93{+/-}2% accuracy using only 80 labelled per class and 600 unlabelled images. The proposed algorithm is generic and can be readily adapted to new labeling schemes, classification targets, cell lines, or microscopy modalities through transfer learning. SGAN is well suited for integration into automated microscopes, enabling efficient and adaptable image analysis across diverse biological and microscopy applications.