---
title: "Mapping Tumor-Microenvironment dependencies with TMEformer: A spatial foundation framework enabling in silico perturbation"
title_zh: TMEformer：一种实现原位扰动的空间基础框架，用于映射肿瘤-微环境依赖关系
authors: "Chen, S., Zhu, G., Yang, L., Li, S., Liu, P., Chen, Q., Tang, Y., Luo, J., Huang, L., Chen, B., Ou, S., Jiang, J."
date: 2026-05-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.17.725770v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 用于肿瘤微环境建模的空间基础框架
tldr: 现有虚拟扰动模型忽视空间背景。TMEformer利用高分辨率空间转录组数据，联合建模肿瘤细胞程序与微环境信号，在多个队列中优于大规模预训练模型，能捕捉谱系可塑性和治疗抵抗等关键转变，并通过系统扰动发现驱动疾病进展的转录因子和配体，改善肿瘤细胞空间分层。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有虚拟扰动模型忽视了空间背景在肿瘤进展中的关键作用，因此需要一种显式整合空间架构的框架。
method: TMEformer是一个肿瘤微环境感知的深度学习框架，通过高分辨率空间转录组数据联合建模内在肿瘤细胞程序与局部微环境信号。
result: 在多个肿瘤空间转录组队列中，TMEformer优于基于大规模语料预训练的基线模型，能准确捕捉谱系可塑性和治疗抵抗等关键肿瘤转变。
conclusion: TMEformer建立了将肿瘤视为空间耦合、可扰动生态系统的通用框架，有望用于体内扰动模拟和靶点发现。
---

## 摘要
尽管空间背景在驱动肿瘤进展中发挥根本作用，但目前大多数用于虚拟扰动的计算模型在很大程度上忽视了其重要性。本文介绍TMEformer，一种肿瘤微环境感知的深度学习框架，通过明确纳入空间架构，利用高分辨率空间转录组学联合建模内在肿瘤细胞程序与局部微环境信号。在多种肿瘤空间转录组队列中验证，TMEformer能够实现捕获局部细胞生态系统内功能依赖性的虚拟扰动。尽管仅在癌症特异性空间数据集上训练，TMEformer在捕获关键肿瘤转变（包括谱系可塑性和治疗耐药性的出现）方面优于在大规模语料库上预训练的基线模型。系统性扰动分析优先识别驱动疾病进展的肿瘤内在转录因子和微环境来源的配体，恢复了已知的调控因子并揭示了新的候选因子。此外，微环境来源的嵌入改善了肿瘤细胞的空间分层，并与病理结构更加一致。综上，TMEformer建立了一个将肿瘤建模为空间耦合、可扰动生态系统的通用框架。

## Abstract
Despite the fundamental role of spatial context in driving tumor progression, most current computational models for virtual perturbation have largely overlooked its importance. Here, we introduce TMEformer, a tumor microenvironment-aware deep learning framework that leverages high-resolution spatial transcriptomics to jointly model intrinsic tumor cell programs and local microenvironmental signals by explicitly incorporating spatial architecture. Validated across diverse tumor spatial transcriptomic cohorts, TMEformer enables virtual perturbations that capture functional dependencies within local cellular ecosystems. Despite being trained on cancer-specific spatial datasets, TMEformer outperforms baseline models pretrained on large-scale corpora in capturing key tumor transitions, including lineage plasticity and the emergence of therapy resistance. Systematic perturbation analyses prioritize tumor-intrinsic transcription factors and TME-derived ligands that drive disease progression, recovering established regulators and revealing novel candidates. Furthermore, TME-derived embeddings improve the spatial stratification of tumor cells and align more closely with pathological architecture. Together, TMEformer establishes a general framework for modeling tumors as spatially coupled, perturbable ecosystems.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将根据您提供的论文内容，生成一份结构化、深入、客观的中文总结。

### 0. 论文的源代码链接
https://github.com/lishensuo/tmeformer

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：现有的计算模型在模拟肿瘤进展的虚拟扰动时，大多将肿瘤细胞视为孤立的个体，**严重忽视了肿瘤微环境（TME）的空间上下文信息**。肿瘤细胞的适应性（如谱系可塑性、治疗抵抗）是由其与周围空间组织化的微环境的动态相互作用所决定的，而现有模型无法捕捉这种耦合关系。
*   **研究动机**：为了更真实地模拟肿瘤生态系统，需要构建一个能够显式整合空间信息、建模肿瘤细胞与微环境双向作用的计算框架，从而实现在空间背景下的因果推断和虚拟扰动。
*   **整体含义**：该研究引入了TMEformer，一个**肿瘤微环境感知的空间基础模型**。它将肿瘤从孤立的细胞重新定义为空间耦合生态系统的一部分，为理解肿瘤进化、发现新的治疗靶点提供了强大的计算机模拟平台。

### 2. 论文提出的方法论：核心思想、关键技术细节（算法流程）
*   **核心思想**：TMEformer通过一个**TME上下文编码模块（TME-CEM）**，将每个肿瘤细胞周围的微环境信息（来自空间转录组数据）编码成一个紧凑的“上下文令牌”，然后将其与肿瘤细胞自身的转录组嵌入融合，共同输入到一个共享的Transformer编码器中。这使得模型能够同时学习肿瘤内在的基因程序以及由微环境调控的依赖性。
*   **关键技术细节与流程**：
    1.  **数据输入**：使用高分辨率空间转录组数据（如10x Xenium），获取每个细胞的基因表达和空间坐标。
    2.  **TME上下文编码（TME-CEM）**：
        *   **邻域选择**：对于每个目标肿瘤细胞，从其空间上最近的K个细胞中随机采样k个作为其微环境细胞。
        *   **细胞嵌入**：每个微环境细胞的初始嵌入由两部分通过元素求和组成：① 一个预训练单细胞模型（GF_CL）提取的转录组嵌入；② 一个可学习的细胞类型嵌入（基于细胞注释）。
        *   **上下文聚合**：这些嵌入经过两阶段注意力处理：① **自注意力**：建模微环境细胞间的相互作用；② **可学习查询向量的注意力池化**：将所有微环境信息聚合为一个单一的TME上下文令牌。
    3.  **融合与编码**：TME上下文令牌通过一个固定权重（α=0.2）与目标肿瘤细胞的初始嵌入融合，再与基因令牌和位置嵌入结合，作为Transformer编码器的最终输入。
    4.  **训练与基准模型**：训练使用掩码基因预测任务。基线模型GF_PCa使用相同数据和架构，但**不包含TME-CEM模块**。

### 3. 实验设计：使用的数据集、Benchmark、对比方法
*   **数据集**：
    *   **核心数据集**：作者使用10x Xenium平台对8例前列腺癌（PCa）临床样本进行了5,051个基因的空间转录组学测序，涵盖治疗初治、ADT治疗后和去势抵抗性前列腺癌（CRPC）等关键阶段。
    *   **外部验证集**：
        *   来自10x Genomics的公开Xenium前列腺癌、乳腺癌、卵巢癌数据集。
        *   来自Vizgen的MERFISH平台（500基因面板）的前列腺癌数据集。
        *   用于验证的公共scRNA-seq（小鼠NEPC模型）和bulk RNA-seq（TCGA-PRAD， MSKCC）数据。
*   **Benchmark任务**：
    *   **神经内分泌前列腺癌（NEPC）标志物基因表达预测**：模拟已知驱动因子（如SOX2、ASCL1过表达，TP53/RB1/PTEN三敲除，LIF-LIFR配体-受体对过表达）对NEPC标志基因（SYP， CHGA, ENO2, NCAM1）表达的影响。
    *   **细胞状态转变预测**：评估虚拟扰动（如雄激素信号通路激活、IL-23过表达、SPP1过表达）是否能将ADT状态下的细胞推向CRPC状态（零样本设置）。
    *   **大规模筛选**：系统性筛选495个转录因子和618个微环境配体，以发现驱动NEPC、CRPC和Gleason分级进展的关键因子。
    *   **TME嵌入分析**：评估TME嵌入在无监督聚类和有监督Gleason分级分类中对肿瘤细胞进行空间和病理相关分层的效果。
*   **对比方法**：
    *   **Geneformer衍生的基线模型**：包括原始预训练模型（GF_PR）、在泛癌scRNA-seq上进一步增强的模型（GF_CL）、以及在PCa空间转录组数据上继续训练但**没有空间信息的**模型（GF_PCa）。
    *   **其他基础模型**：Nicheformer、CellPLM、STACK以及传统降维方法（PCA， scVI）。

### 4. 资源与算力
*   **论文未明确说明**：文中主要提到训练batch size为6，梯度累积4步，学习率为0.0001，训练1个epoch。但没有提供具体的GPU型号、数量和训练时长等算力信息。

### 5. 实验数量与充分性
*   **实验数量**：实验非常充分，涵盖了多个层面：
    *   **性能基准测试**：在4个NEPC扰动任务上进行定量比较。
    *   **L-R对筛选**：测试了15个配体-受体对的影响。
    *   **大规模TF筛选**：系统扰动495个转录因子。
    *   **大规模配体筛选**：系统扰动618个配体。
    *   **TME组成扰动**：对每种微环境细胞类型进行扩增/删除实验。
    *   **跨平台/癌种验证**：在Xenium、MERFISH平台，以及乳腺癌、卵巢癌数据集上测试泛化性。
    *   **消融实验**：评估了TME-CEM模块不同组件的贡献。
    *   **嵌入对比实验**：在无监督聚类和有监督分类任务中，比较TME嵌入与表达嵌入的效果。
*   **充分性与公平性**：
    *   **高度充分**：实验设计严谨，从预测单个基因表达到大规模因果筛选再到跨癌种验证，全面地展示了模型的性能。
    *   **公平性**：与多个强大的基线模型进行对比，并特别设置了“GF_PCa”模型来控制数据量差异，清晰地证明了“引入空间信息”的价值。统计检验方法（如Wilcoxon符号秩检验、Fisher精确检验）使用得当。

### 6. 论文的主要结论与发现
1.  **性能优越**：TMEformer在预测肿瘤细胞对扰动的转录响应方面，显著优于所有基线模型（包括在大型语料上预训练的模型），证明了整合TME空间信息的必要性。
2.  **捕获关键转变**：TMEformer能够准确模拟NE分化和CRPC进展等关键肿瘤转变，并能从微环境细胞（如髓系细胞、成纤维细胞）的扰动中预测其对肿瘤细胞的影响。
3.  **发现新的调控因子**：通过大规模扰动筛选，不仅恢复了SRF、TWIST1等已知驱动因子，还优先发现了如MRC1（髓系细胞中）、CD274、CXCL3等新的调控肿瘤状态的候选配体和转录因子。
4.  **改善空间表征**：TMEformer学习到的“TME嵌入”在聚类和分类任务中，比仅基于转录组的嵌入更能体现空间结构和病理相关性（如Gleason分级）。
5.  **跨平台/癌种泛化**：TMEformer在Xenium和MERFISH两种平台以及前列腺癌、乳腺癌、卵巢癌数据集上均表现出良好的泛化能力，表明其捕获了保守的肿瘤-微环境互作调控原理。

### 7. 优点：方法或实验设计上的亮点
*   **创新性**：首次将显式的空间上下文编码模块（TME-CEM）集成到单细胞Transformer基础模型中，用于系统的虚拟扰动和因果推断。
*   **设计优雅**：两阶段注意力机制能有效建模微环境内部异质性并聚合成一个动态的上下文表示，比简单的固定邻域或池化操作更灵活。固定权重融合保证了模型训练的稳定性。
*   **实验系统性强**：从单基因预测到大规模筛选，再到跨平台/癌种验证，实验链条完整，证明了方法的鲁棒性和实用性。
*   **临床相关性高**：直接对临床样本（不同治疗阶段、不同Gleason分级）的空间数据进行建模和扰动，其结果更贴近体内真实情况。
*   **分析工具全面**：开发了“靶向-排名”、“TME-组成”、“TME-排名”三种扰动策略，以及“终点分数”和“面积分数”两种扰动效果评估指标，分析工具包全面。

### 8. 不足与局限
*   **依赖高分辨率数据**：TMEformer的有效性高度依赖于高分辨率的空间转录组数据（如Xenium的亚细胞分辨率），这限制了其在较低分辨率数据上的应用。
*   **预定义邻域与静态权重**：模型使用空间最近的k个细胞作为邻域，并使用固定的融合权重（α=0.2），这可能无法捕捉动态的、长程的或微妙的细胞间相互作用。
*   **转录组局限性**：当前模型仅限于转录组数据，无法整合蛋白质组、染色质可及性等多模态信息，无法完全反映细胞状态的调控全貌。
*   **预测与验证的差距**：虽然模型通过计算机模拟扰动提出了大量假设，但论文中并未包含对所发现的新调控因子（如TWIST1、MRC1）的体内/体外实验验证，其生物学功能和治疗潜力仍需进一步证实。
*   **潜在偏差风险**：训练数据全部来自前列腺癌，虽然泛化到其他癌种，但模型性能能否完全适用于所有肿瘤类型可能仍有待更多验证。细胞类型注释的质量也会直接影响TME-CEM模块的效果。

（完）
