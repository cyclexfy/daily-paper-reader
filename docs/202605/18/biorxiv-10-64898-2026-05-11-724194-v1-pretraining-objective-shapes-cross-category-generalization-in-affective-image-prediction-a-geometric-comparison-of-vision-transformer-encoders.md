---
title: "Pretraining Objective Shapes Cross-Category Generalization in Affective Image Prediction: A Geometric Comparison of Vision Transformer Encoders"
title_zh: 预训练目标塑造情感图像预测中的跨类别泛化：视觉 Transformer 编码器的几何比较
authors: "Tsuchimoto, S., Okazaki, Y. O., Yuasa, K., Nishijima, S., Izumiya, M., Hagihara, M., Fujihira, R., Kitajo, K."
date: 2026-05-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724194v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 比较在CLIP（语言-图像对比学习）下训练的视觉Transformer
tldr: 本研究通过对比相同ViT架构下CLIP（对比学习）与ImageNet（分类学习）预训练模型的表现，探讨了预训练目标对情感图像预测中跨类别泛化能力的影响。研究发现，对比学习预训练的特征在处理未见语义类别时显著优于分类预训练，且其情感信息在网络深度中分布更广。通过引入几何误差分析，揭示了分类预训练模型存在严重的误差吸引子和中心偏向，而CLIP则展现出更灵活的表征几何结构。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究在保持模型架构不变的情况下，预训练目标如何独立影响视觉表征的几何结构及其在情感预测任务中的跨类别泛化能力。
method: 采用OASIS数据集进行效价-唤醒度预测，通过留一类别交叉验证评估模型，并利用相位锁定和占据熵等几何指标分析预测误差。
result: CLIP预训练模型在跨类别泛化上表现卓越，而分类预训练模型则因类别锚定统计特性导致预测误差集中在少数吸引子区域。
conclusion: 预训练目标是决定特征能否跨越语义边界泛化的关键因素，对比学习相比分类学习能产生更具鲁棒性和分布性的情感表征。
---

## 摘要
深度神经网络学习到的表示几何由架构和预训练目标共同塑造，但解耦这两个因素仍然具有挑战性。本研究通过比较来自同一骨干网络家族但采用不同预训练目标的两个视觉 Transformer（Vision Transformer）来隔离预训练目标的贡献：语言-图像对比学习（CLIP）和 ImageNet-21k 分类。我们使用 OASIS 数据集上的连续效价-唤醒度（Valence-Arousal）预测作为表示质量的探针，在“留一主题出”和“留一类别出”交叉验证下评估了冻结特征，后者要求外推到完全未见的语义类别。在两种协议下，对比预训练编码器的泛化能力均显著优于分类预训练编码器，且当留出类别需要跨类别泛化时，两者差距急剧扩大。为了刻画两种表示差异的原因，我们对预测误差进行了几何分析，将每张图像的误差视为情感平面上的向量，并通过加权相位锁定、基于轨迹的占用熵和有效维度来量化其空间结构。分类预训练表示将误差坍缩到少数具有强烈向心拉力的吸引子区域，而语言对齐表示则将误差广泛分布在情感空间中。逐层线性探针进一步揭示，情感信息在对比编码器的深度方向上呈分布式，但在分类编码器的深层中日益集中，这反映了 ImageNet 训练表示所特有的纹理偏好和以类别为锚点的统计特征。这些结果从表示几何的角度说明了在保持架构不变的情况下，预训练目标的选择如何决定学习到的特征是跨越语义边界泛化，还是局限于与类别相关的视觉规律。亮点：1. 通过保持视觉 Transformer 骨干网络不变来隔离预训练目标的影响。2. 对比预训练特征可以跨越未见的语义类别进行泛化，而分类预训练特征则失败。3. 引入了基于相位锁定和占用熵的预测误差几何分析。4. 分类预训练产生集中的误差吸引子和僵化的向心偏差。5. 情感信息在 CLIP 中分布在不同深度，而在分类 ViT 中则定位于后期层。

## Abstract
The geometry of representations learned by deep neural networks is shaped jointly by architecture and pretraining objective, yet disentangling these two factors remains difficult. Here we isolate the contribution of pretraining objective by comparing two Vision Transformers from the same backbone family but trained under different objectives: language-image contrastive learning (CLIP) and ImageNet-21k classification. Using continuous Valence-Arousal prediction on the OASIS dataset as a probe of representational quality, we evaluated frozen features under Leave-One-Theme-Out and Leave-One-Category-Out cross-validation, the latter requiring extrapolation to entirely unseen semantic categories. The contrastively pretrained encoder generalized substantially better than the classification-pretrained encoder under both protocols, with the gap widening sharply when held-out categories required cross-category generalization. To characterize why the two representations differ, we developed a geometric analysis of prediction errors, treating per-image errors as vectors in the affective plane and quantifying their spatial structure via weighted phase-locking, trajectory-based occupancy entropy, and effective dimensionality. The classification-pretrained representation collapsed errors into a small number of attractor regions with a strong center-ward pull, whereas the language-aligned representation distributed errors broadly across the affective space. Layer-wise linear probing further revealed that affective information was distributed across depth in the contrastive encoder but increasingly concentrated in deeper layers of the classification encoder, mirroring the texture-bias and category-anchored statistics characteristic of ImageNet-trained representations. These results provide a representation-geometric account of how the choice of pretraining objective, holding architecture constant, determines whether learned features generalize across semantic boundaries or remain confined to category-bound visual regularities.

HighlightsO_LIIsolate the effect of pretraining objective by holding the Vision Transformer backbone constant.
C_LIO_LIContrastively pretrained features generalize across unseen semantic categories where classification-pretrained features fail.
C_LIO_LIIntroduce a geometric analysis of prediction errors based on phase-locking and occupancy entropy.
C_LIO_LIClassification pretraining produces concentrated error attractors and a rigid centerward bias.
C_LIO_LIAffective information is distributed across depth in CLIP but localized in late layers of the classification ViT.
C_LI