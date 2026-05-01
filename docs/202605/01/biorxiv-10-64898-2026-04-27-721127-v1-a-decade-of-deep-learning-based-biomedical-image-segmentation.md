---
title: A Decade of Deep Learning-based Biomedical Image Segmentation
title_zh: 基于深度学习的生物医学图像分割十年综述
authors: "Yu, S., Wang, H., Wang, N., Chen, S., Wu, J., Yuan, Z., Qi, T., Zhou, Z., Xia, F., Ma, J., Zhou, Y."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.27.721127v1.full.pdf"
tags: ["query:cpath"]
score: 8.5
evidence: 生物医学图像分割基础模型综述
tldr: 综述了生物医学图像分割从专用模型向通用基础模型演进的十年历程。
source: biorxiv
selection_source: fresh_fetch
motivation: 生物医学图像分割基础模型综述。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## 摘要
生物医学图像分割是计算生物医学中的一个基础问题，旨在精确描绘生物医学图像中的解剖和生物结构、组织类型或病理区域。准确的分割对于广泛的生物和医学应用中的解释、决策和定量分析至关重要。在过去的十年中，该领域经历了深刻的范式转变，从特定任务的专家模型演变为通用的基础模型。本综述对这一演变进行了深入分析，追溯了局部判别学习的局限性如何推动了向基于 Transformer 的全局建模和大规模生成式预训练的转变。为了帮助理解多样化的交互范式，我们首次提出了可提示（promptable）生物医学图像分割的系统分类法，将现有方法分为六种不同的类型，使用户能够根据视觉演示直观地选择合适的提示策略，并快速定位相关文献。除了模型架构，我们还讨论了在数据集开发、评估协议以及放射学、病理学和生物学中特定应用适配方面的并行进展。将这些强大的基础模型与严格的领域特定适配相结合，在改善患者预后和医疗效率方面具有巨大潜力。最后，我们强调了在可信度和临床集成方面必须克服的关键挑战，以实现下一代生物和医学通用模型的潜力。

## Abstract
Biomedical image segmentation is a fundamental problem in computational biomedicine that aims to precisely delineate anatomical and biological structures, tissue types, or pathological regions in biomedical images. Accurate segmentation is essential for interpretation, decision-making, and quantitative analysis across a wide range of biological and medical applications. Over the past decade, the field has undergone a profound paradigm shift, evolving from task-specific specialist models to universal foundation models. This review provides an in-depth analysis of the evolution, tracing how the limitations of local discriminative learning drove the transition toward transformer-based global modeling, and large-scale generative pre-training. To help navigate the diverse landscape of interaction paradigms, we introduce the first systematic taxonomy of promptable biomedical image segmentation, categorizing existing methods into six distinct types, enabling users to intuitively select appropriate prompting strategies based on visual demonstrations and quickly pinpoint relevant literature (\href{https://suhaoyu1020.github.io/MedicalSegmentation-PromptType-Website/}{Prompt Type Visualization}). Beyond model architectures, we discuss parallel advancements in dataset development, evaluation protocols, and application-specific adaptations across radiology, pathology, and biology. Integrating these powerful foundation models with rigorous domain-specific adaptation has great potential to improve patient outcomes and healthcare efficiency. Finally, we highlight key challenges in trustworthiness and clinical integration that must be overcome to realize the potential of the next generation of biological and medical generalists.

---

## 论文详细总结（自动生成）

这篇论文是对过去十年（2015-2025年）基于深度学习的生物医学图像分割领域的深度综述，重点探讨了从“特定任务专家模型”向“通用可提示基础模型”的范式转变。

### 0. 论文的源代码链接
*   **项目可视化主页**：[Prompt Type Visualization](https://suhaoyu1020.github.io/MedicalSegmentation-PromptType-Website/)
*   **代码链接**：文中未直接给出统一的综述代码库，但详细列举并引用了如 MedSAM、CellSAM、BiomedParse 等核心研究的开源资源。

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何克服传统生物医学分割模型（如 U-Net）在面对多样化临床场景时泛化性差、标注成本高、模型冗余（一任务一模型）的问题。
*   **研究动机**：
    *   **范式转移**：记录从局部判别学习（CNN）到全局上下文建模（Transformer），再到大规模预训练（基础模型）的演进。
    *   **交互变革**：探讨如何通过“提示（Prompting）”机制实现无需重新训练的零样本或少样本分割。
    *   **临床鸿沟**：分析算法进步与实际临床应用（如可靠性、3D一致性）之间的差距。

### 2. 论文提出的方法论
论文通过三个维度构建了生物医学分割的技术框架：
*   **架构演进**：
    *   **CNN 时代**：以 U-Net 为核心，通过嵌套连接（UNet++）、全尺度融合（UNet 3+）和系统优化（nnU-Net）提升性能。
    *   **混合架构**：将 CNN 的局部归纳偏置与 Transformer 的全局注意力结合（如 TransUNet, Swin UNETR）。
    *   **Transformer-only/基础模型**：以 SAM 为代表，利用海量数据预训练，实现可提示的通用分割。
*   **可提示分割分类法（首次系统提出）**：
    1.  **显式空间提示**：点（Points）、框（Boxes）、掩码（Masks）。
    2.  **语义提示**：文本（Text）、嵌入（Embeddings）。
    3.  **多模态集成提示**：结合空间与语义信息。
*   **学习范式**：
    *   **数据效率**：通过自监督学习（SSL）、半监督学习和弱监督学习（如 Scribbles 标注）缓解标注稀缺。
    *   **分布式学习**：利用领域自适应（DA）和联邦学习（FL）解决跨机构数据隐私和领域偏移问题。

### 3. 实验设计
作为综述论文，其“实验”体现在对过去十年主流研究的系统性梳理和对比分析：
*   **数据集/场景**：涵盖放射学（CT, MRI, X-ray）、病理学（WSI）、生物显微成像（电镜、光学显微镜）。
*   **Benchmark**：引用了超过 60 个核心基准测试，包括 BraTS（脑肿瘤）、TotalSegmentator（全器官）、AMOS（腹部多器官）、Cell Tracking Challenge 等。
*   **对比方法**：对比了传统专家模型（nnU-Net 等）与新兴基础模型（SAM, MedSAM, SAM-Med3D 等）在零样本、微调及交互式场景下的表现。

### 4. 资源与算力
*   **综述本身**：未提及撰写此综述所消耗的具体算力。
*   **文中提及的模型**：强调了基础模型训练的高昂成本。例如，MedSAM 在 157 万个图像-掩码对上进行训练；一些 3D 基础模型需要处理海量的体积数据，通常依赖大规模 GPU 集群（如 A100/H100 级别）。

### 5. 实验数量与充分性
*   **文献覆盖**：引用了约 150 篇核心文献，跨度从 2015 年到 2025 年（包含部分 2026 年预印本信息），覆盖了从亚细胞到器官级的全尺度任务。
*   **充分性**：论文不仅讨论了算法，还深入探讨了数据集治理、评估指标（Dice, HD, NSD 等）以及临床集成挑战，实验性总结非常全面且客观。

### 6. 主要结论与发现
*   **通用性提升**：基础模型（如 MedSAM）在处理多样化解剖结构和模态方面展现了巨大潜力，正在取代单一任务模型。
*   **提示机制的威力**：通过点、框或文本提示，非专家用户也能快速获得高质量分割结果，极大地降低了 AI 使用门槛。
*   **3D 与时间一致性**：目前的 2D 基础模型在处理 3D 医疗体积数据时仍存在空间不连续问题，MedSAM2 等模型正尝试通过记忆机制解决。
*   **“理解”的幻觉**：基础模型往往基于低级视觉特征（纹理、边缘）而非真正的解剖学逻辑进行分割，存在鲁棒性风险。

### 7. 优点
*   **系统性强**：首次为“可提示生物医学分割”建立了清晰的分类体系。
*   **前瞻性**：不仅总结过去，还提出了“医疗通用智能体（Medical Generalist Agents）”和“视觉链式思考（Visual Chain-of-Thought）”等未来方向。
*   **可视化支持**：提供了专门的网站演示不同提示类型的差异，便于读者直观理解。

### 8. 不足与局限
*   **评估体系滞后**：现有的 Benchmark 大多仍是静态、闭集的，缺乏针对“交互式/提示式”模型的动态评估标准。
*   **黑盒与可信度**：基础模型在安全敏感的临床环境（如手术导航）中缺乏不确定性量化和可解释性。
*   **算力壁垒**：高性能基础模型的微调和部署对基层医疗机构而言仍存在较高的硬件门槛。

（完）
