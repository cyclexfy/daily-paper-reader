---
title: "Intra-African Geographic Domain Shift in Wildlife Camera Trap Species Classification: A Comparative Study of Supervised and Zero-Shot Foundation Models"
title_zh: 非洲内部野生动物相机陷阱物种分类的地理领域迁移：监督模型与零样本基础模型的比较研究
authors: "Nanduri, N., Ogundare, J., Anderson, G."
date: 2026-06-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.734283v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 使用基础模型进行野生动物分类及领域迁移评估的研究
tldr: 非洲内部地理域迁移严重影响野生动物相机陷阱物种分类模型的跨区域部署。本研究首次系统评估该问题，比较监督微调BEiTV2、检索增强DINOv2+FAISS和零样本BioCLIP在南部非洲测试集上的表现。结果显示零样本模型跨域迁移更优，但受物种可见性制约。该工作为保护AI实践者提供实用部署指导。
source: biorxiv
selection_source: fresh_fetch
motivation: 地理域迁移导致模型跨区域部署性能下降，但非洲内部缺乏系统性评估。
method: 使用三种模型（BEiTV2微调、DINOv2+FAISS检索、BioCLIP零样本）在Serengeti训练后测试于南部非洲数据集。
result: 零样本模型BioCLIP跨域迁移最佳，但受物种和图像条件影响；监督模型泛化较差。
conclusion: 首次实证刻画非洲内部域迁移，建议无标签数据时优先采用零样本或检索模型。
---

## 摘要
相机陷阱网络（如Snapshot Safari）已在非洲生成了数百万张带有标签的野生动物图像，使得训练用于自动物种分类的深度学习模型成为可能。然而，将在某一非洲区域训练的模型部署到另一个区域的效果仍知之甚少。据我们所知，本研究首次系统性地评估了非洲大陆内部在野生动物相机陷阱物种分类中的地理领域迁移问题，利用人工智能的机器学习子领域。我们使用了三种模型架构，每种架构以不同方式与Snapshot Serengeti交互：BEiTV2在Serengeti图像上进行微调作为监督基线；DINOv2结合FAISS使用Serengeti图像作为检索索引，不进行任何权重更新；BioCLIP是一个真正的零样本基础模型，完全没有接收Serengeti训练数据。然后将这三个模型在两个南部非洲测试集（Snapshot Kgalagadi和Snapshot Kruger）以及从博茨瓦纳本地收集的野生动物照片上进行评估。我们进行了八项实验，涵盖域内基线、跨数据集迁移、数据缩放、MegaDetector预处理、灰度与彩色图像条件以及每个物种的迁移分析。这项工作首次对监督和零样本架构下的非洲内部领域迁移进行了经验性表征，并为需要在南部非洲多样生态系统中部署模型而无需收集新标记数据的保护人工智能从业者提供了实用指导。

## Abstract
Camera trap networks such as Snapshot Safari have generated millions of labelled wildlife images across Africa, enabling the training of deep learning models for automated species classification. However, deploying models trained in one African region to another remains poorly understood. To the best of our knowledge, this study presents the first systematic evaluation of geographic domain shift within the African continent for wildlife camera trap species classification, using the Machine Learning sub-field of Artificial Intelligence. We use three model architectures, each interacting with Snapshot Serengeti in a different way: BEiTV2is fine-tuned on Serengeti images as a supervised baseline; DINOv2 with FAISS uses Serengeti images as a retrieval index without any weight updates; and BioCLIP is a true zero-shot foundation model that receives no Serengeti training data at all. All three are then evaluated on two Southern African test sets, Snapshot Kgalagadi and Snapshot Kruger, as well as on locally collected wildlife photographs from Botswana. We conduct eight experiments covering in-domain baselines, cross-dataset transfer, data scaling, MegaDetector preprocessing, grayscale vs. colour image conditions, and per-species transfer analysis. This work provides the first empirical characterisation of intra-African domain shift across both supervised and zero-shot architectures, and offers practical guidance for conservation AI practitioners who need to deploy models across the diverse ecosystems of Southern Africa without collecting new labelled data.