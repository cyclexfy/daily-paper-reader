---
title: "DIANNE: Segmentation-Free Localization of Histology Differential Attributes"
title_zh: DIANNE：组织学差异属性的免分割定位
authors: "Domanskyi, S., Rubinstein, J. C., Sheridan, T. B., Thiesen, A., Noorbakhsh, J., Alcoforado Diniz, J., Ramasamy, R., Baker, D. S., Sheldon, R., Wu, Q., Kuchel, G., Robson, P., Chuang, J. H."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721103v1.full.pdf"
tags: ["query:cpath"]
score: 9.0
evidence: 用于组织学和空间组学图像的数字病理学方法
tldr: 本研究提出DIANNE，一种用于组织病理图像空间差异属性快速训练与推理的方法。针对传统方法依赖耗时标注且难以应对新型空间行为的问题，DIANNE利用正类混合增强和基础模型特征，实现了无需分割的实时定位。该系统仅需少量标注即可在数秒内完成全切片图像的分类器训练，支持多种成像模态，为定量理解复杂空间表型提供了高效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统数字病理方法依赖耗时的人工预标注，难以灵活应对标注标准不确定的新型空间生物学行为研究。
method: 提出基于正类混合增强（PCMA）和基础模型特征的DIANNE框架，通过弱监督学习实现无需分割的空间差异属性定位。
result: 该方法仅需数十个标注块即可在数秒内完成全切片图像的实时训练与推理，并成功应用于肿瘤检测及多模态空间组学数据。
conclusion: DIANNE提供了一个高效、交互式的工具包，显著提升了对已知和新型组织空间表型的定量分析与探索能力。
---

## 摘要
病理学家引导的组织学和空间组学图像区分提供了对健康和疾病的见解，而数字病理学则利用人工智能来自动化此类评估。为了训练计算模型，当前的数字病理学方法依赖于前期的手动标注，而生成这些标注非常耗时。预标注不太适合研究新的空间行为——这是由空间分析技术的进步所驱动的主要需求——因为其标注标准和数据需求尚不确定。为了应对这些挑战，我们提出了 DIANNE，这是一种基于训练时正类 Mixup 增强（Positive Class Mixup Augmentation）的数字病理学方法，用于空间差异属性的快速训练和推理。DIANNE 可以在工作站上数秒内计算出基于基础模型的、跨全切片 H&E 图像的差异分类器免分割定位，从而实现对空间生态位（spatial niches）的交互式研究。预测模型可以根据图像块（patch）或区域标注的变化进行实时重新训练，仅需几十个标注的图像块即可阐明跨切片的决定性生物学属性。我们展示了 DIANNE 在肿瘤检测、伪影识别以及胰腺、胎膜和肾脏组织结构探索方面的有效性。DIANNE 还为 IHC、多重免疫荧光以及配准的空间转录组学+H&E 图像提供了类似的功能。DIANNE 在 Jupyter 工具包中实现，能够通过弱监督训练快速开发高分辨率分类器。DIANNE 提供了一个实用的系统，用于定量理解已知和新型的空间表型。

## Abstract
Pathologist-guided distinctions within histology and spatial omic images provide insights into health and disease, with digital pathology leveraging artificial intelligence to automate such assessments. To train computational models, current digital pathology methods rely on upfront manual annotations, which are time-consuming to generate. Pre-annotation is poorly suited to investigating novel spatial behaviors - a major need driven by advances in spatial profiling - for which annotation criteria and data needs will be uncertain. To address these challenges, we present DIANNE, a digital pathology approach for rapid training and inference of spatial differential attributes based on train-time Positive Class Mixup Augmentation. DIANNE can compute foundation model-derived segmentation-free localization of differential classifiers across whole slide H&E images within seconds on a workstation, enabling interactive investigation of spatial niches. Predictive models can be re-trained in real-time in response to patch or regional annotation changes, clarifying determinative biological attributes across slides from only a few dozen annotated patches. We demonstrate the effectiveness of DIANNE for tumor detection, artifact identification, and exploration of pancreatic, fetal membranes and kidney tissue structures. DIANNE also provides analogous capabilities for IHC, multiplex immunofluorescence, and registered spatial transcriptomic+H&E images. DIANNE is implemented in a Jupyter toolkit, enabling rapid development of high-resolution classifiers from weakly-supervised training. DIANNE provides a practical system to quantitatively understand known and novel spatial phenotypes.

---

## 论文详细总结（自动生成）

以下是对论文《DIANNE: Segmentation-Free Localization of Histology Differential Attributes》的结构化深入总结：

### 0. 论文源代码链接
*   **GitHub 链接**：[https://github.com/TheJacksonLaboratory/image-differential-annotator](https://github.com/TheJacksonLaboratory/image-differential-annotator)
*   **相关工具包**：STQ (H&E 处理) [https://github.com/TheJacksonLaboratory/STQ](https://github.com/TheJacksonLaboratory/STQ)；SOT (多重荧光处理) [https://github.com/TheJacksonLaboratory/spatial-omics-tools](https://github.com/TheJacksonLaboratory/spatial-omics-tools)。

### 1. 核心问题与整体含义（研究动机）
*   **研究动机**：传统的数字病理 AI 模型训练依赖大量耗时的人工预标注（如像素级分割），且难以应对空间组学中不断涌现的新型、未定义的空间结构。
*   **核心问题**：如何在缺乏大规模标注的情况下，快速、交互式地训练出能够准确定位组织差异属性（如肿瘤、特定细胞生态位、伪影）的分类器。
*   **整体含义**：DIANNE 旨在通过“免分割”和“实时交互”的方式，将病理学家的专业知识与基础模型（Foundation Models）结合，实现对复杂组织表型的快速探索与定量分析。

### 2. 核心方法论
DIANNE 的核心在于结合了高效的特征表示与创新的数据增强技术：
*   **SAMPLER 特征表示**：不直接处理原始像素，而是将图像分解为切片（tiles），利用预训练基础模型（如 CTransPath, UNI）提取特征，并计算这些特征的**分位数分布（CDF）**。这种表示法能捕捉区域内的统计特征，且计算极其高效。
*   **正类混合增强（PCMA, Positive Class Mixup Augmentation）**：
    *   **核心思想**：在 SAMPLER 潜空间中，将正样本（如肿瘤）与负样本（如正常组织）进行加权混合，生成增强的正样本。
    *   **技术细节**：通过混合两个样本的离散概率密度函数（PDF）并重新积分得到新的 CDF。这种方法在不增加原始数据处理负担的情况下，提供了强大的正则化效果，使模型能从极少量（几十个）标注块中学习到稳健的分类边界。
*   **四种工作流**：
    1.  **组织学静态/交互式**：处理 H&E、IHC 或 mIF 图像。
    2.  **分子静态/交互式**：将空间转录组（ST）数据与 H&E 图像配准，利用分子信号引导图像分类器的训练。

### 3. 实验设计
*   **数据集与场景**：
    *   **肿瘤检测**：儿童肉瘤（887 张）、TCGA 正常组织、CAMELYON16 淋巴结。
    *   **组织结构探索**：人胰腺（胰岛、PanIN 癌前病变）、肾脏（肾小球、纤维化）、胎膜结构。
    *   **多模态应用**：HER2 乳腺癌 IHC 图像、PhenoCycler 多重蛋白图像、Xenium/Atera 空间转录组数据。
*   **对比方法（Benchmark）**：
    *   **CLAM**：基于注意力机制的弱监督学习框架。
    *   **Segmenter**：基于 Vision Transformer 的像素级分割模型。
    *   **Moment-based**：基于矩（均值、方差等）的特征表示法。
*   **验证方式**：由临床病理学家进行像素级手动标注作为金标准，计算 AUROC、AUPRC 和假阳性率（FPR）。

### 4. 资源与算力
*   **训练效率**：
    *   **DIANNE**：在 **1 个 CPU** 上训练仅需 **15 秒**（针对肉瘤数据集）。
    *   **CLAM**：在 NVIDIA A100 GPU 上需 30 分钟。
    *   **Segmenter**：在 NVIDIA A100 GPU 上需 6 小时。
*   **推理速度**：全切片图像（WSI）推理小于 60 秒；交互界面加载图像块小于 1 秒。
*   **算力需求**：极低，支持在普通工作站甚至笔记本电脑上进行实时交互式训练。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了从大规模临床队列（肉瘤）到精细的空间组学案例（胰腺、肾脏）。
*   **消融与参数分析**：详细测试了增强参数 $\alpha$ 的影响、训练样本量对性能的贡献，以及不同基础模型（UNI, CTransPath 等）的适配性。
*   **客观性**：采用了留一供体交叉验证（Leave-one-donor-out），并对比了不同扫描仪和染色协议下的表现，证明了方法的鲁棒性。实验设计较为充分且公平。

### 6. 主要结论与发现
*   **高效性**：DIANNE 仅需少量标注（通常 <50 个图像块）即可达到或超过需要大量标注的深度学习模型的性能。
*   **PCMA 的作用**：正类混合增强显著提升了分类器的特异性，尤其是在处理包含大量正常组织的肿瘤切片时。
*   **多模态融合**：证明了 H&E 图像特征与空间转录组/蛋白组信号之间存在强相关性，可以通过图像特征预测分子表型。
*   **交互式发现**：系统支持实时重新训练，允许研究人员在探索过程中不断修正分类标准，适合发现未知的生物学结构。

### 7. 优点（亮点）
*   **极速反馈**：实现了“人机耦合”的实时训练，病理学家标注后可立即看到全图预测结果。
*   **免分割定位**：避开了复杂的像素级分割任务，通过块级（patch-level）分析实现了高精度的空间定位。
*   **通用性强**：一套框架兼容 H&E、IHC、mIF 和 ST 多种模态，且支持模块化更换基础模型。
*   **低门槛**：基于 Jupyter Toolkit 开发，易于集成到现有的生物信息学工作流中。

### 8. 不足与局限
*   **分辨率限制**：默认基于图像块（如 8x8 tiles）进行预测，虽然可以调整，但其原生分辨率低于像素级分割模型。
*   **依赖基础模型**：分类效果高度依赖于底层基础模型提取特征的质量，若基础模型未见过特定组织类型，性能可能受限。
*   **批次效应风险**：研究发现如果将过多不同来源的切片混合进行增强，可能会引入批次效应，降低分类性能。
*   **应用限制**：目前主要针对二分类或差异属性定位，对于极其复杂的多分类任务，交互式标注的负担可能会增加。

（完）
