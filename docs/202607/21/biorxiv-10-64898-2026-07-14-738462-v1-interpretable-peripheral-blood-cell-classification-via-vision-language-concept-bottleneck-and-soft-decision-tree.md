---
title: Interpretable Peripheral Blood Cell Classification via Vision-Language Concept Bottleneck and Soft Decision Tree
title_zh: 通过视觉语言概念瓶颈和软决策树的可解释外周血细胞分类
authors: "Chen, K., Hu, T."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.14.738462v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 使用视觉-语言概念瓶颈实现可解释细胞分类，直接涉及视觉语言模型
tldr: "外周血细胞分类面临黑盒问题，缺乏可解释性。提出两阶段管道：先用域自适应视觉语言模型ConceptCLIP将细胞图像零样本映射为70维形态概念得分，再用软决策树进行分类并生成可追踪的决策路径。在BloodMNIST数据集上达到94.86%准确率，仅比黑盒模型低约3个百分点，且决策逻辑符合血液学标准，甚至无监督地分离了未成熟粒细胞亚型（早幼粒细胞与中幼粒细胞）。该方法实现了概念级可解释性，同时保持了较高性能。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738462-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1763, \"height\": 572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738462-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 877, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738462-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1833, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738462-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1295, \"height\": 2488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738462-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 809, \"height\": 442, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738462-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 905, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738462-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 904, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738462-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 920, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738462-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1852, \"height\": 356, \"label\": \"Table\"}]"
motivation: 现有深度学习分类器不提供可解释性，无法用形态学标准说明推理过程，阻碍临床审计与验证。
method: 使用域自适应视觉语言模型ConceptCLIP零样本提取70个形态概念得分，再以软决策树分类并产生可追踪的决策路径。
result: "在BloodMNIST上测试准确率94.86%，仅比黑盒模型低3%，决策路径与血液学形态标准一致。"
conclusion: 概念瓶颈与决策树结合实现可解释分类，并能无监督区分未成熟粒细胞亚型，超越训练标签粒度。
---

## 摘要
动机：用于医学图像分析的深度学习分类器通常作为黑箱运行，既不揭示其预测所依据的图像特征，也不揭示单个决策的推理过程。外周血细胞分类体现了这一挑战：经验丰富的实验室专业人员通过结构化的形态学标准——细胞核形状、染色质纹理、核质比、颗粒度和染色特性——来识别细胞类型，然而现有的自动化系统无法用这些术语表达其推理，阻碍了临床审核和验证。结果：我们提出了一个两阶段的可解释流水线，解决了这两个层面的不透明性。在第一阶段，一个冻结的领域自适应视觉语言模型（ConceptCLIP）通过零样本余弦相似度将每个细胞图像投影到70维的形态学概念得分向量，消除了对每个图像概念注释的需求。在第二阶段，一个软决策树（SDT）仅基于这些概念得分对细胞进行分类，为每个预测产生一个确定性的、基于概念的决策路径。在BloodMNIST（8种细胞类型，3,421张测试图像）上，完整流水线达到了94.86%的测试准确率——比黑箱上限低约3个百分点——同时提供了完全可追踪的决策逻辑。训练后的组织学注释证实，学习到的路由逻辑与既定的血液学形态学标准一致，并揭示了未成熟粒细胞亚型（早幼粒细胞与晚幼粒细胞）在无亚型监督下的涌现性分离，表明基于概念的决策树能够恢复超出训练标签粒度的临床有意义的区别。可用性和实现：源代码、训练好的SDT权重、预计算的概念得分数据和推理脚本公开于https://github.com/aquamarineaqua/CLIP-CBM-SoftDecisionTree。

## Abstract
Motivation: Deep learning classifiers for medical image analysis typically function as black boxes, disclosing neither the image features underlying their predictions nor the reasoning by which individual decisions are reached. Peripheral blood cell classification exemplifies this challenge: experienced laboratory professionals identify cell types through structured morphological criteria---nucleus shape, chromatin texture, nucleus-to-cytoplasm ratio, granularity, and staining properties---yet existing automated systems cannot express their reasoning in these same terms, impeding clinical audit and verification. Results: We present a two-stage interpretable pipeline that addresses both levels of opacity. In the first stage, a frozen domain-adapted vision-language model (ConceptCLIP) projects each cell image onto a 70-dimensional vector of morphological concept scores via zero-shot cosine similarity, eliminating the need for per-image concept annotations. In the second stage, a Soft Decision Tree (SDT) classifies cells solely on these concept scores, producing a deterministic, concept-based decision path for each prediction. On BloodMNIST (eight cell types, 3,421 test images), the full pipeline achieves 94.86% test accuracy---approximately 3 percentage points below the black-box ceiling---while providing fully traceable decision logic. Post-training histological annotation confirms that the learned routing logic aligns with established hematological morphology criteria and reveals an emergent separation of immature granulocyte subtypes (promyelocyte versus metamyelocyte) without subtype supervision, demonstrating that concept-based decision trees can recover clinically meaningful distinctions beyond the granularity of the training labels. Availability and implementation: The source code, trained SDT weights, precomputed concept score data, and inference scripts are publicly available at https://github.com/aquamarineaqua/CLIP-CBM-SoftDecisionTree.

---

## 论文详细总结（自动生成）

### 0. 论文的源代码链接
- https://github.com/aquamarineaqua/CLIP-CBM-SoftDecisionTree

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：深度学习分类器在外周血细胞分类任务中表现优异，但作为“黑箱”无法揭示预测所依据的图像特征及推理过程，阻碍了临床审计、验证和信任。
- **临床背景**：血液学专业人员依据结构化形态学标准（核形状、染色质纹理、核质比、颗粒度、染色特性）进行诊断，而现有自动化系统无法用同样术语表达推理。
- **研究目标**：构建一个两阶段可解释流水线，在保持较高准确率的同时，提供特征层（形态学概念）和决策层（决策路径）的完全透明度。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：利用视觉语言模型的零样本对齐能力，将细胞图像映射到预定义的形态学概念得分空间，再通过软决策树（Soft Decision Tree, SDT）实现基于概念的、可追踪的分类逻辑。
- **第一阶段：概念瓶颈（Concept Bottleneck）**
  - 使用领域自适应的预训练视觉语言模型 **ConceptCLIP**（冻结参数）。
  - 设计70个形态学概念（涵盖核形态、胞质色调、颗粒、非白细胞成分、人工制品五大类），每个概念用10个文本提示模板的嵌入均值表示。
  - 对每个输入图像，计算与每个概念文本嵌入的余弦相似度，得到70维概念得分向量 c = [c₁, c₂, ..., c₇₀]。
  - 公式：cⱼ = cos(z_img, z̄_textⱼ) = (z_img · z̄_textⱼ) / (‖z_img‖·‖z̄_textⱼ‖)
- **第二阶段：软决策树（Soft Decision Tree）**
  - 深度d=4，包含15个内部节点和16个叶节点（经实验确定）。
  - 每个内部节点 i 计算路由概率：pᵢ(c) = σ(β · (wᵢᵀc + bᵢ))，其中 wᵢ 为可学习权重向量，β为逆温度。
  - 每个样本到达叶节点 l 的概率：μₗ(c) = ∏_{i∈path(l)} [pᵢ(c) 或 1-pᵢ(c)]。
  - 最终预测：P(y|c) = Σₗ μₗ(c)·Qₗ，Qₗ为叶节点 l 的学习类分布。
  - 推理时采用硬路由（argmax）获得确定性决策路径。
  - 训练损失：交叉熵 + 平衡惩罚项（鼓励各节点左右路由比例平衡）。
  - 训练后剪枝：删除样本数<50或叶节点最大预测置信度<80%的节点；保留的节点通过分析极端得分样本进行语义注释。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：BloodMNIST（MedMNIST子集），8个正常外周血细胞类别（嗜碱性粒细胞、嗜酸性粒细胞、成红细胞、未成熟粒细胞、淋巴细胞、单核细胞、中性粒细胞、血小板）。合并训练集和验证集共13,671张图像，测试集3,421张。
- **基准（黑箱上限）**：使用完整ConceptCLIP图像嵌入（768维）训练MLP（单隐层）、XGBoost、逻辑回归、SVM，最高准确率97.98%（MLP）。
- **对比方法**：
  - 概念瓶颈阶段：使用70维概念得分向量搭配不同分类器（MLP、XGBoost、逻辑回归、SVM），测试准确率。
  - 全流水线：概念瓶颈 + SDT（硬路由），记录准确率。
  - 概念集粒度实验：分别使用30、50、70、90个概念，用逻辑回归评估，确定70为最优。
- **消融实验**：分别量化概念瓶颈（约1.9pp损失）和SDT约束（约1.3pp损失）对准确率的影响。

### 4. 资源与算力
- **文中未明确说明**GPU型号、数量、训练时长等具体算力信息。仅提及使用Adam优化器，学习率5×10⁻³，权重衰减5×10⁻⁴，β=2，λ=5×10⁻⁵。ConceptCLIP骨干网络全程冻结。

### 5. 实验数量与充分性
- **实验数量**：
  - 概念集粒度实验：4组（n=30/50/70/90），每种用逻辑回归。
  - 黑箱上限实验：4种分类器（MLP、XGBoost、LR、SVM）。
  - 概念瓶颈实验：4种分类器（同前）。
  - 全流水线实验：SDT深度选择（d=3/4/5），最终选定d=4。
  - 剪枝与注释：后处理分析，展示树结构及叶节点分布。
- **充分性评价**：实验设计较为系统，对比了不同概念集大小、不同下游分类器，并分别量化了概念瓶颈和决策树造成的准确率损失。但**缺少多轮独立重复实验**（仅单次训练，未报告方差），且仅在一个数据集（BloodMNIST）上验证，未涉及其他医学图像或复杂病理场景。总体而言，在既定范围内的实验是客观、公平的，但泛化性评估不足。

### 6. 论文的主要结论与发现
- 全流水线在BloodMNIST测试集上达到 **94.86%** 准确率，仅比黑箱上限（97.98%）低约3.1个百分点（概念瓶颈损失~1.9pp，SDT损失~1.3pp）。
- 70维概念瓶颈保留了约98%的判别信息，证明零样本VLMs可有效替代昂贵的逐图像概念标注。
- SDT学到的决策路径（先按胞质染色色调粗分，再按核形态、颗粒特征细分）与临床血液学分级诊断策略高度吻合。
- **重要发现**：SDT无监督地将单一“未成熟粒细胞”类别中具有不同形态的亚型（早幼粒细胞 vs 晚幼粒细胞）分离到不同叶节点，说明基于概念的决策树能发现训练标签之外的临床有意义结构。

### 7. 优点：方法或实验设计上的亮点
- **完全可解释性两层次**：特征层（概念得分有语义名称）和决策层（硬路由给出确定性决策路径），符合临床审计需求。
- **零样本概念提取**：无需逐图像概念标注，大大降低部署成本，利用预训练VLM的跨模态对齐能力。
- **软决策树斜向分裂**：对噪声和概念间相关性具有鲁棒性，且可通过剪枝和注释提取简洁的语义规则。
- **涌现性发现**：在不提供亚型监督的情况下，自动分离未成熟粒细胞亚型，展示了模型捕捉形态学细微差异的能力，具备临床转化潜力。

### 8. 不足与局限
- **概念集设计**：手动选择，缺乏完备性保证，可能存在冗余或遗漏相关特征。概念得分为余弦相似度，未经校准为概率，解释时需谨慎。
- **实验覆盖有限**：
  - 仅使用一个公开数据集（BloodMNIST），缺乏对病理变异、罕见细胞类型、类不平衡等真实临床场景的验证。
  - 仅报告单次运行结果，未量化随机初始化导致的方差。
- **可扩展性限制**：深度4对应16个叶节点，对更多类别或更细粒度分类任务，树深度需增加，但叶节点数指数增长会降低人工可解释性。
- **性能差距**：虽比黑箱低仅3pp，但在要求极高精度的诊断场景（如白血病筛查）中，该差距可能仍不可接受。文中也指出是否可接受取决于应用场景（筛查 vs 诊断）。

（完）
