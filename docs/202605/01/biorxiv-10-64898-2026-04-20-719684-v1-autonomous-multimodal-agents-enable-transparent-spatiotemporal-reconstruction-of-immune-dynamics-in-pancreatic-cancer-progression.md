---
title: "Autonomous multimodal agents enable transparent, spatiotemporal reconstruction of immune dynamics in pancreatic cancer progression"
authors: "Huang, B., Zhu, B."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.20.719684v1.full.pdf"
tags: ["query:cpath"]
score: 10.0
evidence: "使用大语言模型进行H&E组织学分析的智能体计算病理学框架"
tldr: "ROSIE利用大语言模型智能体在常规H&E组织切片上实现透明且具有病理学家水平的推理分析。"
source: biorxiv
selection_source: fresh_fetch
motivation: "使用大语言模型进行H&E组织学分析的智能体计算病理学框架。"
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## Abstract
Pancreatic cancer progression is orchestrated by dynamic shifts in immune and stromal cellular ecosystems, yet the temporal and spatial principles governing these transitions remain poorly understood. Here, we present an agentic computational pathology framework that leverages large language models to orchestrate modular biomarker inference and spatiotemporal reasoning directly from routine H&E histology. Our approach, ROSIE (RObust in Silico Immunofluorescence), combines deep-learning-based multiplex inference with LLM-driven agent logic that emulates pathologist-level reasoning, enabling transparent and reproducible analysis of complex tissue microarchitectures.

Applying this workflow to pancreatic intraepithelial neoplasia (PanIN) progression in KSC transgenic mice (n=24, ages 4-12 weeks), we generated 10.44 million single-cell profiles and identified a temporally ordered immune trajectory comprising three spatially distinct immune-stromal states: (1) early immune-surveillance niche: sharply bounded window of adaptive immune activation and antigen-presentation enrichment; (2) transitional mixed state: declining lymphoid activity, emerging exhaustion programs, and early EMT/angiogenesis signals; (3) stromal-dominant terminal state: fibroblast expansion, vascular remodeling, and immune silence.

These findings establish pancreatic cancer progression as a temporally ordered sequence of immune activation, exhaustion, and stromal takeover. The agentic framework transcends static AI models by offering dynamic, tool-augmented reasoning that bridges high-dimensional tissue data with clinical interpretability--providing a scalable foundation for identifying therapeutic inflection points in early tumor evolution.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个基于大语言模型（LLM）编排的自主多模态智能体框架，用于通过常规 H&E 染色组织切片重建胰腺癌进展过程中的时空免疫动力学。

### 0. 论文的源代码链接
*   **ROSIE 深度学习框架（生物标志物推断）：** [https://gitlab.com/enable-medicine-public/rosie](https://gitlab.com/enable-medicine-public/rosie)
*   **LangGraph 编排管线（智能体工作流）：** [https://github.com/bayjuan5/LangGraphPrj_V5](https://github.com/bayjuan5/LangGraphPrj_V5)

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题：** 胰腺癌早期病变（PanIN）向浸润性癌转化的过程中，免疫和基质微环境的动态演变规律尚不明确。
*   **研究背景：** 
    *   高维分析技术（如单细胞测序、多重成像）成本高、通量低，难以进行大规模队列研究。
    *   常规 H&E 切片虽然易得，但其蕴含的深层分子和空间信息未被充分挖掘。
    *   现有的计算病理学 AI 模型多为“黑盒”系统，缺乏模块化、透明度以及跨阶段的时空推理能力。
*   **整体含义：** 本研究旨在开发一种透明、可解释的智能体框架，仅利用 H&E 图像即可实现病理学家水平的推理，重建肿瘤演化的时空图谱。

### 2. 论文提出的方法论
核心思想是结合**深度学习推断（ROSIE）**与**LLM 智能体逻辑编排**。
*   **ROSIE (RObust in Silico Immunofluorescence)：** 利用在配对的 H&E 和多重免疫荧光（mIF）数据上训练的深度学习模型，从 H&E 图像中虚拟推断出 50 种蛋白标志物的表达谱。
*   **LLM 编排框架（基于 LangGraph）：** 采用多节点（Node）架构，由 LLM 智能体根据任务模板自动生成 Python 执行脚本并触发计算：
    *   **Node 1 (自适应分块)：** 自动识别组织区域并进行标准化切片。
    *   **Node 2.1 & 2.2 (特征提取与推断)：** 提取细胞空间坐标、形态学描述符，并运行 ROSIE 推断细胞类型和分子特征。
    *   **Node 3 (时间动力学建模)：** 整合不同时间点的数据，利用**定时 Petri 网（Timed Petri Net）**和 log2 倍数变化（LFC）建模细胞状态转换。
    *   **Node 4 (空间生态位分析)：** 结合 DBSCAN 聚类和通路评分，识别具有特定生物学功能的空间微环境（Niches）。

### 3. 实验设计
*   **数据集：** 使用 KSC 转基因小鼠模型（n=24），涵盖 4 到 12 周龄的 8 个关键时间点，模拟从早期前驱病变到晚期基质丰富疾病的连续过程。
*   **数据规模：** 成功分割并分析了 **1044 万个单细胞** 谱。
*   **验证基准（Benchmark）：** 
    *   将 ROSIE 的推断结果与同一队列的**湿实验数据**（免疫组化 IHC、三色染色、免疫荧光、V-1520 示踪成像）进行对比。
    *   验证指标包括 CD68+ 骨髓细胞丰度、巨噬细胞极化状态、基质重塑程度和疾病分期的一致性。

### 4. 资源与算力
*   **算力支持：** 论文提到使用了德克萨斯高级计算中心（TACC）的资源（项目号 MCB23032）。
*   **具体配置：** 文中未明确列出具体的 GPU 型号、数量或训练总时长，但提到 LLM 后端使用了 Claude 3.5 Sonnet（主要）和 Llama 2 7B（本地迭代）。

### 5. 实验数量与充分性
*   **实验规模：** 涵盖了 8 个发育阶段的纵向采样，每阶段均进行了单细胞级别的深度挖掘。
*   **充分性评价：** 实验设计较为充分。研究不仅展示了宏观的细胞比例变化，还深入到通路活性、空间聚类和状态转换模型。
*   **客观性：** 通过与 7 项独立的生物学指标（如 TSPO 表达、M1/M2 极化等）进行交叉验证，证明了计算推断的准确性。

### 6. 论文的主要结论与发现
研究识别出胰腺癌进展的三个时空有序阶段：
1.  **早期免疫监视生态位（4-6周）：** 适应性免疫激活，富含抗原递呈信号，免疫细胞紧密围绕在新生上皮结构周围。
2.  **过渡混合状态（7-9周）：** 淋巴细胞活性下降，耗竭程序启动，早期上皮-间质转化（EMT）和血管生成信号出现。
3.  **基质主导终末态（11-12周）：** 纤维化和血管重塑加剧，免疫沉默，形成有利于肿瘤浸润的微环境。
*   **核心发现：** 免疫抑制并非突然发生，而是通过激活信号的阶段性侵蚀与骨髓/成纤维细胞程序的扩张共同驱动的。

### 7. 优点
*   **透明度与可解释性：** 引入 LLM 智能体编排，使复杂的计算流程变得模块化且可审计。
*   **低成本高通量：** 仅需常规 H&E 切片即可获得接近多重成像的高维分子信息。
*   **时空整合：** 首次在 H&E 基础上实现了大规模的时间序列建模与空间生态位分析的统一。

### 8. 不足与局限
*   **推断风险：** ROSIE 基于预测模型，对于极稀有或过渡态的细胞表型，可能仍需正交实验（如空间转录组）进一步验证。
*   **采样局限：** 实验基于横断面采样（不同个体的不同阶段）而非对单一个体的实时纵向追踪，可能忽略了克隆演化的随机性。
*   **因果关系：** 虽然识别了空间模式，但上皮、骨髓和成纤维细胞之间的具体因果互作仍需功能性实验（如扰动实验）来阐明。

（完）
