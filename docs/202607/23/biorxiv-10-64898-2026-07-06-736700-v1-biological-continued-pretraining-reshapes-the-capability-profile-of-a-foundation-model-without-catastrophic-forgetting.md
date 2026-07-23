---
title: Biological Continued Pretraining Reshapes the Capability Profile of a Foundation Model Without Catastrophic Forgetting
title_zh: 生物学持续预训练重塑基础模型的能力轮廓而无灾难性遗忘
authors: "Wang, L."
date: 2026-07-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.06.736700v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 研究基础模型在生物数据上的持续预训练
tldr: "通常认为在狭窄领域继续预训练会导致通用能力下降（灾难性遗忘）。本研究不进行新训练，通过直接比较Gemma-4-26B模型同源的三个检查点（基础、生物CPT后、SFT后），测定CPT对通用、代码、生物三个能力轴的影响。结果显示生物CPT未引发遗忘，反而全面提升：MMLU+13、MBPP pass@1 0.33→0.63、BixBench MCC从0.23升至0.92，链式推理缩短41%，仅TruthfulQA降8.8分。后续SFT使能力回落，揭示CPT重塑能力轮廓而SFT兑现目标，两者互补，生物序列是结构化科学数据而非容量竞争者。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-06-736700-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1352, \"height\": 795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-06-736700-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1534, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-06-736700-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 964, \"height\": 880, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-06-736700-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1040, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-06-736700-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1784, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-06-736700-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1506, \"height\": 287, \"label\": \"Table\"}]"
motivation: 挑战领域继续预训练必然导致灾难性遗忘的普遍假设，旨在通过零训练分析直接验证CPT对模型能力的影响。
method: 直接比较Gemma-4-26B模型同源三个检查点（基础、CPT后、SFT后），在MMLU、MBPP、BixBench等基准上零训练评估CPT效应。
result: "生物CPT使MMLU提升13点、MBPP pass@1翻倍至0.63、BixBench MCC升至0.92，链式推理缩短41%，仅TruthfulQA降8.8分；后续SFT使所有指标回落至基值。"
conclusion: CPT与SFT是互补而非替代阶段：CPT重塑模型能力轮廓，SFT将其兑现到具体任务；生物序列应视为结构化科学数据，可重塑基础模型能力。
---

## 摘要
人们普遍认为，在一个狭窄的分布外语料库（如原始生物序列）上进行持续预训练（CPT），必然要以牺牲通用模型的广泛能力为代价——即所谓的“对齐税”或灾难性遗忘直觉。我们直接检验了这一假设，无需任何新训练，通过重新分析来自26B参数混合专家模型（Gemma-4-26B-A4B）同一谱系的三个检查点：指令微调基础模型、经过生物CPT（87亿个DNA、蛋白质和生物医学文本token）后的同一模型，以及随后经过监督微调（SFT）的模型。在三个独立的能力轴——通用知识/推理（MMLU、ARC、HellaSwag）、代码生成（MBPP）和生物医学知识（BixBench）上，我们发现生物CPT并未降低模型性能，反而提升了它：MMLU提高13个百分点，MBPP pass@1几乎翻倍（从0.33增至0.63），BixBench区分度大幅上升（MCC从0.23增至0.92）。唯一测量的回归是真实性（TruthfulQA下降8.8个百分点），这是一种较小且可解释的领域漂移。一项干净的词汇扩展消融实验（在每项通用指标上<0.4个百分点）证实了这些提升归因于CPT，而非分词器变化。关键是，后续的SFT将模型性能拉回：所有三个轴都降至接近基础模型水平，揭示了一致的分工——CPT重新组织并提升共享的能力基础；SFT将其兑现到目标任务上。我们认为，这重新定义了生物序列并非基础模型能力的竞争者，而是一种结构化科学数据，重塑其能力轮廓，并且CPT和SFT应被视为互补而非可替代的阶段。所有检查点、评估代码和每个示例的输出均已公开。

亮点：
- 对26B MoE谱系进行免训练重新分析，将生物持续预训练（CPT）的效果与分词器变化和微调分离。
- 生物CPT不会导致灾难性遗忘；它提升了通用知识（MMLU提高13分）和代码生成（MBPP pass@1从0.33增至0.63）。
- CPT还使思维链推理缩短41%，且几乎无回溯，同时保持准确性——这一效果对准确率指标不可见。
- 一致的CPT提升/SFT缩窄分工在四个轴上重复出现，将生物序列重新定义为重塑模型能力轮廓的结构化科学数据。

更大图景：将通用AI模型适应到专业领域——这里指DNA和蛋白质的语言——通常被认为是有代价的：教会它生物学，它就会忘记如何推理其他一切。这种“没有免费午餐”的直觉影响着实践者如何分配计算资源，以及他们是否尝试领域适应。我们直接检验了这一假设，无需运行任何新训练，通过比较同一模型在生物训练前后的三个快照。结果推翻了这一直觉：给模型喂食原始生物序列使其在通用知识、代码编写方面表现得更好，甚至改变了它的推理方式——产生更短、更果断的思维链而不损失准确性。这些提升出现在序列预训练阶段，并在任务特定微调时部分回退，揭示出两个阶段扮演互补而非可互换的角色。这为数据为中心的AI提出了一个更广泛的原则：结构化科学数据——当今的生物序列，以及扩展至代码、数学和化学——不仅是需要吸收的知识，更是一种杠杆，重塑基础模型的能力。

## Abstract
It is widely assumed that continued pretraining (CPT) on a narrow, out-of-distribution corpus such as raw biological sequence must trade away a general-purpose models broad competence -- the "alignment tax" or catastrophic-forgetting intuition. We test this directly, without any new training, by re-analyzing three checkpoints from a single lineage of a 26B-parameter Mixture-of-Experts model (Gemma-4-26B-A4B): the instruction-tuned base, the same model after biological CPT (8.7B tokens of DNA, protein, and biomedical text), and after subsequent supervised fine-tuning (SFT). Across three independent capability axes -- general knowledge/reasoning (MMLU, ARC, HellaSwag), code generation (MBPP), and biomedical knowledge (BixBench) -- we find that biological CPT does not degrade the model; it lifts it: MMLU +13 points, MBPP pass@1 nearly doubles (0.33 [-&gt;]0.63), and BixBench discrimination rises sharply (MCC 0.23 [-&gt;] 0.92). The single measured regression is truthfulness (TruthfulQA 8.8 points), a small and interpretable domain drift. A clean vocabulary-expansion ablation (< 0.4 pt on every general metric) confirms the gains are attributable to CPT, not tokenizer changes. Crucially, subsequent SFT narrows the model back: all three axes fall to near-base levels, revealing a consistent division of labor -- CPT re-organizes and lifts the shared capability substrate; SFT cashes it out onto target tasks. We argue this reframes biological sequence not as a competitor for a foundation models capacity but as a form of structured scientific data that reshapes its capability profile, and that CPT and SFT should be budgeted as complementary rather than substitutable stages. All checkpoints, evaluation code, and per-example outputs are public.

HighlightsO_LIA training-free re-analysis of one 26B MoE lineage isolates the effect of biological continued pretraining (CPT) from tokenizer changes and from fine-tuning.
C_LIO_LIBiological CPT does not cause catastrophic forgetting; it raises general knowledge (MMLU +13 pts) and code generation (MBPP pass@1 0.33[-&gt;] 0.63).
C_LIO_LICPT also makes chain-of-thought reasoning 41% shorter and near-backtrack-free while pre-serving accuracy -- an effect invisible to accuracy metrics.
C_LIO_LIA consistent CPT-lifts / SFT-narrows division of labor recurs across four axes, reframing biological sequence as structured scientific data that reshapes a models capability profile.
C_LI

The Bigger PictureAdapting a general-purpose AI model to a specialized domain -- here, the language of DNA and proteins -- is usually assumed to come at a cost: teach it biology and it forgets how to reason about everything else. This "no free lunch" intuition shapes how practitioners budget compute and whether they attempt domain adaptation at all. We test the assumption directly, and without running any new training, by comparing three snapshots of the same model taken before and after biological training. The result overturns the intuition: feeding the model raw biological sequence made it better at general knowledge, at writing code, and even changed how it reasons -- producing shorter, more decisive chains of thought without losing accuracy. The gains appear during the sequence-pretraining stage and are partly given back during task-specific fine-tuning, revealing that the two stages play complementary rather than interchangeable roles. This suggests a broader principle for data-centric AI: structured scientific data -- biological sequence today, and by extension code, mathematics, and chemistry -- is not merely knowledge to be absorbed but a lever that reshapes what a foundation model can do.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 0. 论文的源代码链接

无（论文中仅提及检查点和评估代码已公开，但未提供具体链接）。

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：挑战“在狭窄领域（如生物序列）上持续预训练必然导致通用能力衰退（灾难性遗忘）”的普遍假设。
- **研究背景**：领域适应通常被认为是有代价的（“对齐税”），使实践者在预算计算资源和是否尝试领域适应时产生犹豫。此前研究多关注密集模型，且将遗忘视为需要最小化的成本，未见报道生物CPT能提升通用和代码基准，也未发现它能改变推理风格。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：通过“免训练重新分析”现有检查点，直接比较同一模型谱系在生物CPT前后的能力变化，无需任何新训练。这避免了训练引入的混淆因素，使能力差异可明确归因于特定训练阶段。
- **关键技术细节**：
  - 使用Gemma-4-26B-A4B Mixture-of-Experts模型（128个专家/层，top-8路由，约3.8B活跃参数）。
  - 对比四个检查点（谱系）：
    1. 基础指令微调模型（it）。
    2. 词汇扩展后的基础模型（it-bio）：仅将词汇表从262,144扩展到290,172（增加28,028个生物BPE token），但未进行任何训练，用于隔离分词器变化的影响。
    3. 生物CPT后的模型（BioCPT）：在it-bio基础上对8.7B token的混合生物语料（DNA、蛋白质序列、生物医学文本）进行持续预训练，使用LoRA（r=64）覆盖注意力、MLP和MoE路由器，嵌入层解冻，最终合并为全权重。
    4. 生物CPT + SFT后的模型（BioCPT+SFT）：在BioCPT基础上对生物指令数据（双头结构变体“v5”）进行监督微调，合并为全权重。
  - 验证：通过直接权重比较确认it和it-bio共享路由器/专家权重（逐位平均绝对差为0），仅嵌入层不同；BioCPT的路由器和专家权重已有可测量变化。
- **流程文字说明**：利用同一模型谱系（it → it-bio → BioCPT → BioCPT+SFT），通过免训练评估，将每个阶段的独立效果分离：词汇扩展效果通过it vs it-bio对比，CPT效果通过it-bio vs BioCPT对比，SFT效果通过BioCPT vs BioCPT+SFT对比。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **评估基准**：
  - 通用知识/推理：MMLU（5-shot）、ARC-Challenge（25-shot）、HellaSwag（10-shot）、TruthfulQA-mc2（0-shot）。
  - 代码生成：MBPP（3-shot）、HumanEval（0-shot，但被排除在结论外）。
  - 生物医学知识：BixBench（MCC）。
  - 推理行为：GSM8K（200题，k=5次采样，共享8-shot CoT支架），测量链长度、自纠正标记、对冲标记、自一致性。
- **对比方法**：未对比其他方法，而是对比同一模型谱系的四个检查点（it、it-bio、BioCPT、BioCPT+SFT），即自身对比。论文强调这是“免训练重新分析”，不引入外部模型。
- **使用的工具**：lm-evaluation-harness（v0.4.12），所有多选任务采用loglikelihood评分，对输出格式鲁棒。

## 4. 资源与算力

- 论文指出**所有评估在单张96 GB GPU上以bfloat16精度运行**，全模型（约52 GB）可装入一张卡。整个研究**无需训练**（training-free re-analysis），因此未报告训练所需算力。CPT和SFT是现有公开检查点，论文未说明它们消耗的算力。

## 5. 实验数量与充分性

- **实验维度**：覆盖了通用知识（4个基准）、代码（1个基准）、生物医学（1个基准）、推理行为（GSM8K上4个指标）。共约6个独立基准+1个行为诊断。
- **消融实验**：词汇扩展消融（it vs it-bio）用于分离分词器效果；SFT消融（BioCPT vs BioCPT+SFT）用于分离监督微调效果。
- **充分性评估**：
  - 优点：实验设计干净，通过单一谱系直接比较，消除了架构、数据版本等混淆因素。每个阶段仅改变一个变量，结论因果关系明确。
  - 局限性：仅在一个模型（Gemma-4-26B-A4B）的一个谱系上进行，未在不同模型大小或不同领域上验证泛化性。部分指标（如ARC/HellaSwag）的部分提升被指出是格式效应（指令vs完成loglikelihood），但MMLU的提升不受此影响。生物序列同源性能力无法通过简单零样本探测量化，因此该轴仅间接论证。总计实验组数相对有限（4个检查点，约6个基准），但每个基准上的结果模式一致（CPT升、SFT降），增强了可信度。

## 6. 论文的主要结论与发现

- **核心结论**：在所有测量的能力轴上，生物CPT提升模型性能，后续SFT将其拉回（模式：Base < BioCPT > SFT，BioCPT为峰值）。
- **具体发现**：
  - 词汇扩展成本为零：it vs it-bio在所有通用指标上差异≤0.4个百分点。
  - 通用知识/推理显著提升：MMLU +13.0分（0.646→0.776），ARC-Challenge准确率近乎翻倍（0.367→0.700），HellaSwag +36.7分。
  - 代码能力近乎翻倍：MBPP pass@1从0.33升至0.63。
  - 生物医学知识大幅提升：BixBench MCC从0.232升至0.924。
  - 唯一回归：TruthfulQA下降8.8个百分点（0.533→0.445），视为可解释的领域漂移。
  - 推理行为改变：CPT使思维链缩短41%（108.8→64.4 token），自纠正几乎消失（0.370→0.006回溯/生成），而准确率未降（0.667→0.689），自一致性不变（0.745）。SFT逆转这些变化。
  - 共同模式：CPT是提升能力轮廓的“投资”阶段，SFT是将其兑现到目标任务的“兑现”阶段。两者互补，不可互换。
- **重新框架**：生物序列应视为“结构化科学数据”，其价值不仅在于承载事实，更在于迫使模型内化结构规律，这些规律可迁移到其他结构化语言（如代码）。生物序列不是容量的竞争者，而是能力重塑的杠杆。

## 7. 优点：方法或实验设计上的亮点

- **训练自由**：完全免训练，仅使用现有检查点，大幅降低实验门槛，且避免了新训练引入的随机噪声。
- **干净对比**：通过单一谱系，将分词器变化、CPT、SFT的效果逐层分离，因果推断清晰。
- **多维度评估**：覆盖通用知识、代码、生物医学、推理行为四个独立轴，且每个轴结果模式一致，增强了结论的鲁棒性。
- **深入行为分析**：不仅关注准确率，还关注推理过程（链长度、自纠正等），揭示了准确率不可见的效果。
- **诚实局限性说明**：主动指出部分提升的格式效应、HumanEval的不公平性、同源性测量的困难性，体现科研诚信。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **实验覆盖窄**：仅基于一个模型（26B MoE）的一个CPT/SFT谱系，未在不同大小、不同架构（如密集模型）或不同领域（如数学、化学）上验证，无法确认是否普适。
- **部分提升的混淆**：ARC/HellaSwag的部分提升归因于指令模型在loglikelihood多选上的弱势，CPT恢复为类似基础模型行为，这并非纯粹能力提升。MMLU的提升不受此影响，但仍需谨慎解释。
- **缺失关键轴测量**：零样本序列同源性无法通过简单探针评估，使得生物序列迁移的完整画面缺失。
- **单一回归**：TruthfulQA下降8.8分，虽解释为领域漂移，但若实际应用中真实性至关重要，则此代价不可忽略。
- **CPT数据配方未优化**：仅使用现有的混合生物语料（8.7B token），未探索最优数据比例，无法回答“应该用多少生物数据”等工程问题。
- **无不同阶段内的消融**：未报告不同CPT步数、不同LoRA秩、不同学习率等超参数的影响，仅表征了该特定谱系。
- **公平性边界**：HumanEval 0-shot被排除，因为它对指令/SFT检查点不公平，这限制了代码能力评估的广度。
- **应用限制**：结论基于MoE模型，可能不直接适用于密集模型或更小参数量模型；且CPT和SFT的任务分布高度相关（均为生物领域），跨领域泛化未验证。

（完）
