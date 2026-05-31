---
title: "MORPHE: Bridging Image Generation and Spatial Omics for Tissue Synthesis"
title_zh: MORPHE：桥接图像生成与空间组学实现组织合成
authors: "Feng, Y., Robers, Z., Rasheed, L., Miao, Y., Wen, S., Lee, K., Sohigian, J., Brbic, M., Hickey, J. W."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.03.709377v2.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 从空间组学数据合成组织图像，可用于病理学研究
tldr: 空间组学技术虽能揭示单细胞组织结构，但受限于成本、覆盖不全和实验伪影。MORPHE提出图引导的概率嵌入，将细胞身份与空间关系映射到RGB潜空间，利用预训练扩散模型生成单细胞精度的组织图像。在大规模肠道和脑数据集上，MORPHE实现了视野外推、缺失区域修复及2D/3D跨组织拼接，为空间组学数据提供了可扩展的合成与重建方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有空间组学数据存在成本高、覆盖不全和伪影问题，亟需计算方法重构或扩展组织上下文。
method: MORPHE通过图引导概率嵌入将细胞空间映射为RGB潜空间，结合扩散模型生成并解码为生物学可解释的组织。
result: 在百万级细胞数据集上，MORPHE成功实现视野外推、损伤区域修复及2D/3D跨组织拼接。
conclusion: MORPHE为空间组学数据生成提供了新范式，有效克服了实验数据的关键局限。
---

## 摘要
空间解析组学技术以单细胞分辨率揭示组织结构，但仍受限于检测成本、不完整的空间覆盖、仅二维成像以及实验伪影。这些因素促使我们需要计算方法，以重建或扩展当前空间测量所提供的组织背景。我们提出MORPHE（结构化空间高维嵌入建模），这是一个AI框架，能够直接从空间组学数据学习合成生物学上可信的组织结构。MORPHE引入了一种基于图信息的概率嵌入，将离散的细胞身份及其空间关系映射到一个连续的、类似RGB的潜在空间，该空间与扩散建模兼容。这种表示桥梁使得空间细胞图谱能够利用大型预训练图像生成模型，同时在解码时保持生物学可解释性。通过将细胞建模为生成的基本单元，并学习它们的身份和空间关系如何共同产生大规模组织结构，MORPHE能够以单细胞分辨率生成和重建组织结构。我们将该方法应用于来自肠道的大规模单细胞蛋白质组数据集和来自大脑的单细胞转录组数据集，展示了跨数百万细胞的计算可扩展性。我们在这些数据集上使用MORPHE进行实验限制视野外的外推、缺失或实验损伤组织区域的内插，以及跨组织插补，将分离的组织区域连接成单一的连续样本（二维和三维）。MORPHE代表了一类新的组织生成算法，将有助于解决当前单细胞空间组学数据集的局限性和挑战。

## Abstract
Spatially resolved omics technologies reveal tissue organization at single-cell resolution but remain limited by the cost of the assays, incomplete spatial coverage, 2D-only imaging, and experimental artifacts. These factors motivate the need for in silico methods that can reconstruct or extend tissue context beyond what current spatial measurements provide. We present MORPHE (MOdeling of stRuctured sPatial High-dimensional Embeddings), an AI framework that learns to synthesize biologically faithful tissue architecture directly from spatial-omics data. MORPHE introduces a graph-informed probabilistic embedding that maps discrete cell identities and their spatial relationships into a continuous RGB-like latent space compatible with diffusion modeling. This representational bridge enables spatial cellular maps to leverage large pre-trained image-generative models while preserving biological interpretability upon decoding. By modeling cells as the fundamental units of generation and learning how their identities and spatial relationships collectively give rise to large-scale tissue structure, MORPHE enables generation and reconstruction of tissue architecture at single-cell resolution. We applied the method across large-scale single-cell proteomic datasets from the intestine and single-cell transcriptomic datasets from the brain, showing computational scalability acrosss millions of cells. We used MORPHE on these datasets to outpaint beyond experimentally restricted fields of view, inpaint missing or experimentally damaged tissue regions, and perform cross-tissue imputation, connecting separated tissue regions into a single contiguous sample in both 2D and 3D. MORPHE represents a new class of tissue generation algorithms that will help solve current limitations and challenges with single-cell spatial-omics datasets.