---
title: "NEURA: An agentic system for autonomous neuroimaging workflows"
title_zh: NEURA：一种用于自主神经影像工作流的智能体系统
authors: "Xie, J., Wang, J., Wu, X., Liu, X., Mi, Y., Liu, Q., Xu, T., Liu, C., Chen, H., Guo, J."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.27.721217v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 多模态神经影像数据集和LLM驱动的智能体系统
tldr: "神经影像学研究门槛高，限制了其临床应用。本文提出NEURA，一个基于大语言模型的智能体系统，旨在实现神经影像工作流的自动化。NEURA能处理自然语言问题和多模态数据，生成分析计划、可执行脚本及结构化报告。实验显示其规划准确率达89.5%，显著优于直接使用LLM，并在脊髓小脑共济失调症案例中成功识别病理特征，推动了神经影像研究向自动化、可解释化发展。"
source: biorxiv
selection_source: fresh_fetch
motivation: 神经影像学分析需要深厚的跨学科专业知识，导致研究门槛极高且难以广泛应用。
method: 开发了基于大语言模型的智能体系统NEURA，通过自然语言处理和多模态数据融合，自动生成并执行端到端的神经影像分析工作流。
result: "NEURA在基准测试中达到89.5%的规划准确率，在工具选择和排序上显著超越传统LLM，并成功复现了专家的临床病理分析结果。"
conclusion: 该系统实现了从简单的流程自动化到严谨、可扩展且具解释性的神经影像研究系统的跨越。
---

## 摘要
神经影像学对于研究人类大脑至关重要；然而，其所需的深厚跨学科专业知识设定了极高的门槛，限制了其更广泛的临床和科学应用。我们推出了 NEURA，这是一个由大语言模型（LLM）驱动的智能体系统，用于自动化的神经影像工作流规划与分析。NEURA 处理自由文本形式的研究问题和多模态神经影像数据集，生成有据可依的分析计划、可执行脚本、经过验证的统计结果和结构化报告，并提供与中间产物及完整执行记录相关联的可追溯推理过程。通过在精选基准测试上的广泛评估，NEURA 实现了 89.5% 的规划准确率，显著优于直接的 LLM 查询，在规划准确率、工具选择和工具排序方面平均分别提升了 30.5%、25.6% 和 36.7%。在脊髓小脑共济失调 3 型的案例研究中，NEURA 自主识别出了与既定病理学和专家手动分析一致的小脑萎缩和异常扩散模式。总的来说，这些结果表明，我们的工作实现了从流水线自动化向严谨、可扩展且可解释的神经影像研究系统的跨越。

## Abstract
Neuroimaging is essential for studying the human brain; however, the deep interdisciplinary expertise required imposes a very high threshold, limiting its broader clinical and scientific applications. We introduce NEURA, a large language model (LLM)-powered agentic system for automated neuroimaging workflow planning and analysis. NEURA processes free-text research questions and multimodal neuroimaging datasets to generate evidence-grounded analysis plans, executable scripts, validated statistical results and structured reports, with traceable reasoning linked to intermediate artefacts and full execution records. Through extensive evaluations on a curated benchmark, NEURA achieved an 89.5% planning accuracy and substantially outperformed direct LLM queries, with average gains of 30.5% in planning accuracy, 25.6% in tool selection and 36.7% in tool ordering. In case studies of spinocerebellar ataxia type 3, NEURA autonomously identified cerebellar atrophy and abnormal diffusivity patterns consistent with established pathologies and expert manual analyses. Collectively, these results demonstrate that our work advances from pipeline automation to rigorous, scalable and interpretable neuroimaging research systems.