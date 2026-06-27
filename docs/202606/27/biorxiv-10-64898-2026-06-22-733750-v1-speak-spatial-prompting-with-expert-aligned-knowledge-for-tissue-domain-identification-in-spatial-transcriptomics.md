---
title: "SPEAK: Spatial Prompting with Expert Aligned Knowledge for Tissue Domain Identification in Spatial Transcriptomics"
title_zh: SPEAK：利用专家对齐知识的空间提示方法进行空间转录组组织域识别
authors: "Wei, H., Luo, X., Yu, H., Liang, J., Yang, L., Sauler, M., Kaminski, N., Popa, A., Yan, X."
date: 2026-06-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.22.733750v1.full.pdf"
tags: ["query:cpath"]
score: 8.0
evidence: 利用大语言模型和组织学先验的空间转录组组织域识别
tldr: 空间转录组学数据需要准确识别组织域。SPEAK方法利用大语言模型和人类专家知识，通过构建空间上下文提示实现零样本推理、专家引导微调和原型更新。在STARmap、Visium等数据集上，SPEAK在域预测精度、鲁棒性和可解释性方面优于现有方法，并能高效泛化到其他切片。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有空间域识别方法缺乏先验知识整合，且对有限标记数据鲁棒性不足。
method: SPEAK构建基于细胞类型和标记基因的空间上下文提示，通过两阶段提示实现零样本推理和专家引导微调。
result: 在多个SRT数据集上，SPEAK的域预测精度、鲁棒性和可解释性均优于现有方法。
conclusion: SPEAK有效结合LLM和人类专家知识，提升空间域识别性能并支持高效微调与泛化。
---

## 摘要
空间分辨转录组（SRT）数据需要进行空间域识别，以实现组织微环境特异性的下游分析。本文提出SPEAK（利用专家对齐知识的空间提示方法），一种基于大语言模型（LLM）的方法，通过利用LLM和人类专家的先验知识来从SRT数据中识别空间域。SPEAK根据每个细胞/点的邻近细胞的细胞类型和标记基因构建空间上下文提示，通过两阶段提示实现零样本推理、专家引导微调和原型更新。对STARmap、Visium、MERFISH和Xenium数据集的应用表明，与现有空间域识别方法相比，SPEAK在域预测准确性、对有限先验知识的鲁棒性、生物学可解释性以及高效专家引导微调并泛化到其他组织切片的能力方面具有优势。

## Abstract
Spatially resolved transcriptomic (SRT) data requires spatial domain identification to enable tissue microenvironment-specific downstream analyses. Here we present SPEAK (Spatial Prompting with Expert-Aligned Knowledge), a large language model (LLM) -based method to identify spatial domains from SRT data by taking advantage of the prior knowledge from both LLM and human experts. SPEAK constructs a spatial context prompt for each cell/spot based on cell types and marker genes of its neighboring cells, enabling zero-shot inference, expert-guided fine-tuning, and prototype updating through two-stage prompting. Applications to STARmap, Visium, MERFISH and Xenium datasets showed advantages of SPEAK over existing spatial domain identification methods in domain prediction accuracy, robustness to limited prior knowledge, biological interpretability, and capacity for efficient expert-guided fine-tuning with generalizability to other tissue sections.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，以下是对您提供的论文进行的结构化、深入且客观的中文总结。

### 论文的源代码链接
*   **GitHub:** `https://github.com/wJDKnight/SPEAK`

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题：** 空间转录组学（SRT）数据需要进行“空间域识别”，以划分出具有特定功能的组织结构（如皮层分层、肺泡区域等）。现有方法主要依赖无监督学习，存在以下几个关键瓶颈：
    *   **缺乏先验知识整合：** 无法利用已有的生物学文献、病理学家经验等大量先验知识。
    *   **难以跨样本迁移：** 模型通常需要针对每个新数据集重新从头训练，不能直接迁移应用。
    *   **结果缺乏生物学意义：** 聚类输出的是抽象的簇编号（如 “Cluster 1”），无法直接对应到有实际意义的组织区域，需要人工注释。
    *   **参数敏感性强：** 方法性能高度依赖于预先设定的聚类数量（K值）或分辨率参数，而这些参数通常是未知的。
*   **整体含义：** 本文提出了一种创新的、基于大语言模型（LLM）的方法，旨在通过整合LLM的通用生物学知识和人类专家的特定领域知识，克服上述局限，实现更准确、更具生物学可解释性且泛化能力更强的空间域识别。

### 2. 论文提出的方法论：核心思想、关键技术细节
*   **核心思想：** SPEAK将空间域识别任务转化为一个对LLM的文本提示（Prompt）任务。通过为每个细胞/点构建一个描述其“空间微环境”的提示词，引导预训练的LLM利用其内化的生物学知识，预测该细胞所属的组织区域。
*   **关键技术细节与流程：**
    1.  **空间上下文提示构建：** 针对每个细胞/点，以其为中心定义一个半径（δ）的邻域，并从SRT数据中提取两方面的信息，排序后构成本文形式的“空间档案”：
        *   **邻域细胞类型列表：** 按邻域内各类细胞出现的频率降序排列。
        *   **邻域标记基因列表：** 按邻域内所有细胞中标记基因的平均表达水平降序排列。
        *   该“空间档案”与任务描述（如“请识别这个细胞属于哪个皮层区域”）组成完整的提示词。
    2.  **三种应用模式：**
        *   **SPEAK-Z（零样本）：** 直接将构造好的提示词输入预训练LLM，在目标数据上不进行任何训练，直接输出域预测结果。这是验证LLM本身知识能力的关键。
        *   **SPEAK-F（微调）：** 当零样本性能不佳时，利用少量人工标注的细胞及其所属域，通过低秩适应（LoRA）技术对LLM进行高效微调。微调时，提示词会加入从已标注细胞中计算出的“域原型”（Domain Prototypes，即各域的典型“空间档案”）。
        *   **SPEAK-Fs（两阶段提示）：** 用于提升微调模型对新样本的泛化能力。**第一阶段**，用微调后的模型对样本进行初步预测，挑选出高置信度的细胞（邻域内多数细胞预测一致）来更新计算样本特异的“域原型”。**第二阶段**，用更新后的“域原型”和原始提示词，让微调模型对低置信度的细胞进行二次预测。
*   **后处理：** 对所有预测结果进行空间平滑处理，强制邻域内大多数细胞的标签一致。

### 3. 实验设计：数据集、基准测试、对比方法
*   **数据集：** 涵盖多种技术、物种和组织类型，共4个：
    *   **STARmap（小鼠视觉皮层）：** 单细胞分辨率，3个样本，4个皮层域（L1/L2-3/L5/L6）。用作零样本性能的基准测试。
    *   **Visium（人背外侧前额叶皮层）：** 点阵分辨率，3个受试者共12个切片，7个域（6层白质）。用于微调和跨样本/跨受试者泛化性测试。
    *   **MERFISH（小鼠下丘脑视前区）：** 单细胞分辨率，1个受试者5个切片，8个域。用于微调效率和标注比例影响分析。
    *   **Xenium（人COPD肺）：** 单细胞分辨率，1个样本，8个域（病理学家定义）。作为真实世界验证案例，对比人类专家注释的H&E染色结果。
*   **基准测试与对比方法：** 使用了包括准确性和空间连续性在内的多种指标。
    *   **16种SOTA方法：** 全面对比了主流空间域识别方法，包括 **BASS**, **Seurat**, **GraphST**, **STAGATE**, **SpaGCN**, **IRIS** 等。
    *   **多种LLM后端：** 测试了闭源模型 (GPT-4o mini, GPT-4o, Gemini 1.5 Pro) 和开源模型 (Llama-3.1-8B/70B, Qwen3-30B)。
*   **对比指标：**
    *   **准确性：** NMI (归一化互信息), HOM (同质性), COM (完整性)。
    *   **空间连续性：** CHAOS, PAS, ASW。 (更高或更低的值代表更好)

### 4. 资源与算力
*   **明确说明：** 论文明确提到了使用的硬件：
    *   **开源LLM推理：** 使用了 **2个 NVIDIA H200 GPUs** 和 **2个 CPU 核心** 部署vLLM进行推理，速度从每1024个细胞3秒（Qwen3-30B）到18秒（Llama-3.1-70B）不等。
    *   **闭源LLM：** 使用官方API，处理时间取决于网络和负载。
    *   **微调：** 通过OpenAI的微调API进行，训练3个epochs，batch size为2，使用默认学习率。使用的具体GPU型号和数量未在API场景下说明。

### 5. 实验数量与充分性
*   **实验数量：** 非常充足。论文进行了多组系统的实验，包括：
    *   在STARmap上对**6种LLM**和**16种SOTA方法**进行全面基准测试。
    *   针对域列表**鲁棒性测试**（遗漏、多余、替换域）。
    *   在Visium和MERFISH上验证**微调**的有效性，并进行了**跨切片**和**跨受试者**的泛化测试。
    *   在MERFISH上分析**不同标注比例（5%-70%）** 对微调性能的影响。
    *   在Xenium数据上，与Seurat和IRIS**定性比较**，并通过病理学家的H&E染色**人工验证**。
*   **充分性与公平性：**
    *   **充分性：** 实验覆盖了零样本、微调、泛化、鲁棒性、标注效率等多个维度，足以全面展示方法的优势和探索其边界。真实世界验证增加了可信度。
    *   **公平性：** 为了与无监督方法（如BASS）公平比较微调效率，作者采取了特殊的后处理方式（将无监督聚类结果匹配到少数标注标签上），确保了比较的公平性。对比实验参数采用了先前基准研究中的优化结果。
    *   **潜在偏差：** Visium和MERFISH数据集的零样本性能不佳，归因于细胞类型注释粗粒度或不准确，虽然合理，但暗示SPEAK-Z对输入数据的质量有较高要求。STARmap有完整单细胞注释和简单清晰的结构，可能更有利于SPEAK-Z。

### 6. 论文的主要结论与发现
1.  **卓越的零样本能力：** SPEAK-Z在STARmap数据集上显著优于所有非LLM方法，证明了预训练LLM具备足够的先验知识用于空间域识别。模型越大（如Gemini 1.5 Pro），性能越好。
2.  **强鲁棒性和可解释性：** SPEAK-Z对域列表冗余不敏感，对缺失会降低性能但优于同等条件下的非LLM方法。更重要的是，它能直接输出有意义的域名称（如“Layer 1”）。
3.  **微调显著提升性能：** 对于零样本效果不好的数据（如Visium, MERFISH），通过微调（SPEAK-F）可以大幅提升性能，甚至超越SOTA。仅需标记30%的细胞即可达到很好的性能。
4.  **两阶段提示增强泛化性：** SPEAK-Fs通过样本内高置信度细胞更新原型，有效解决了切片间和受试者间的差异性问题，使模型能“无标注”应用于新样本，且性能稳定。
5.  **人机协同有效：** 在人类COPD肺数据上，SPEAK-F在病理学家的指导和验证下，成功纠正了零样本预测的偏差，并进一步挖掘出了疾病相关的病理变化，展示了其作为分析工具的实用价值。

### 7. 优点
*   **创新性：** 首次系统地将LLM的语义理解和推理能力与空间转录组学分析深度结合，开辟了新范式。
*   **实用性强：** 具有“端到端”的生物学意义标注，无需后处理；支持零样本、少样本微调和跨样本泛化，非常符合生物医学研究人员需要交互、调整的工作流程。
*   **效率高：** 细胞级别的提示可以并行处理，没有图神经网络（GNN）方法随着数据量增长的内存瓶颈，计算效率高。
*   **可解释性好：** LLM可以输出推理步骤，研究人员可以检查模型是否基于正确的生物学知识进行判断，既是一种诊断工具，也增强了结果的可信度。
*   **鲁棒性好：** 对缺失或冗余的域列表不敏感，降低了参数调节的难度。

### 8. 不足与局限
*   **对LLM先验知识的依赖：** 方法性能高度依赖于LLM本身对特定组织和疾病的了解程度。对于研究较少或不典型的情况，零样本性能会受限（如Visium/MERFISH案例）。
*   **仍需部分人工先验：** 方法仍需用户提供一个潜在域列表，虽然鲁棒，但该列表的构建仍然依赖专家知识。未来可以探索让LLM自行生成这个列表。
*   **邻域大小是超参数：** 邻域半径（δ）是手动设定的，未被研究对不同组织或域的最优选择，可能需针对新场景进行调整。
*   **大模型微调难度：** 论文指出，更大、性能更好的模型（如Llama-3.1-70B）更难进行微调。这对其在资源受限的环境中部署和应用提出了挑战。未来可探索知识蒸馏等方案。

（完）
