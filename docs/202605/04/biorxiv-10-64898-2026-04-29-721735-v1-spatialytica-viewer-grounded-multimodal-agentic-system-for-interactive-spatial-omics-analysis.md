---
title: "spatiAlytica: Viewer-Grounded Multimodal Agentic System for Interactive Spatial Omics Analysis"
title_zh: spatiAlytica：面向交互式空间组学分析的基于查看器的多模态智能体系统
authors: "Das, A., Zhang, K., Song, J., Han, M., Chen, A., Meng, W., Galloway, H., Chen, P.-Y., Jo, S., Liu, Z., Hasib, M. M., Officer, A., Sinha, H., Chiu, Y.-C., Gao, S.-J., Li, L., Huang, Y."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.29.721735v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于空间组学分析的多模态智能体系统
tldr: 针对空间转录组学和蛋白质组学分析中编程门槛高、现有AI智能体缺乏视觉感知等挑战，本文推出了spatiAlytica。这是一个嵌入Napari查看器的多模态交互式智能体系统，支持非编程背景的生物学家通过自然语言进行迭代式、假设驱动的空间组学分析。该系统集成了状态序列化、代码生成及视觉问答等功能，并在新发布的spatiAlyticaBench基准测试中展现出超越现有基准的性能，有效辅助了癌症研究中的空间模式发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的空间组学分析工具对编程能力要求较高，且现有的AI智能体在处理交互式视觉上下文和跨轮对话方面存在局限。
method: 开发了一个嵌入Napari查看器的多模态智能体系统，通过状态序列化、智能体记忆、代码生成与调试以及空间视觉问答实现交互式分析。
result: 在包含单轮、多轮及图像推理的spatiAlyticaBench基准测试中，该系统在效率和准确性上均优于强基准模型，并成功应用于多种癌症的案例研究。
conclusion: spatiAlytica为生物学家提供了一个强大的交互式工具，能够降低空间组学分析的门槛并支持复杂的科学推理工作流。
---

## 摘要
空间转录组学和蛋白质组学能够绘制组织架构和细胞相互作用图谱，但其分析仍受限于编程需求以及缺乏查看器锚定（viewer grounding）和跨轮次上下文的以文本为中心的 AI 智能体。我们提出了 spatiAlytica，这是一个嵌入在 Napari 查看器中的以查看器为中心的多模态交互式智能体系统，使非编程背景的生物学家能够通过自然语言进行迭代式、假设驱动的空间组学分析。spatiAlytica 结合了查看器状态序列化、智能体记忆、生物学概念到数据字段的映射、代码生成与调试、空间视觉问答（Spatial VQA）以及锚定解释，以支持探索性分析和解释性推理工作流。我们引入了 spatiAlyticaBench，这是一个全面的基准测试，涵盖了 222 个单轮空间分析编码问题、178 个多轮顺序工作流问题以及 7,350 个基于图像的推理问题。spatiAlytica 的表现优于强大的智能体基准模型，同时消耗的时间和 Token 更少。在卡波西肉瘤、结直肠癌和卵巢癌的案例研究中，该系统重现了已知的空间模式，并揭示了卡波西肉瘤进展过程中 CD8 T 细胞的渐进性功能障碍。

## Abstract
Spatial transcriptomics and proteomics map tissue architecture and cellular interactions, but analysis remains limited by programming demands and text-centered AI agents that lack viewer grounding and cross-turn context. We present spatiAlytica, a viewer-centric multimodal interactive agentic system embedded in the Napari viewer that enables non-programmer biologists to perform iterative, hypothesis-driven spatial omics analysis via natural language. spatiAlytica couples viewer-state serialization, agentic memory, biological concept-to-data-field mapping, code generation and debugging, Spatial VQA, and grounded interpretation to support an exploratory analysis and interpretive reasoning workflow. We introduce spatiAlyticaBench, a comprehensive benchmark spanning 222 single-turn spatial analytical coding questions, 178 multi-turn sequential workflow questions, and 7,350 image-grounded reasoning questions. spatiAlytica outperformed strong agentic baselines, while using less time and tokens. Case studies across Kaposi's sarcoma, colorectal cancer, and ovarian cancer recapitulated known spatial patterns and uncovered progressive CD8 T-cell dysfunction during KS progression.