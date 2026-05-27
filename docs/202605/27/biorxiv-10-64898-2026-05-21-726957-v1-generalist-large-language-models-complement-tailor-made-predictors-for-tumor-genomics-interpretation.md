---
title: Generalist large language models complement tailor-made predictors for tumor genomics interpretation
title_zh: 通用大语言模型补充定制预测器用于肿瘤基因组学解读
authors: "Yu, J., Darmofal, M., Waters, M., Choy, J., Tran, T. N., Fu, C., Morales, L., U, K., Levine, R. L., Schultz, N., Berger, M. F., Morris, Q., Jee, J."
date: 2026-05-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.726957v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 评估通用大语言模型在肿瘤基因组解释任务上的表现
tldr: 本研究评估了通用大语言模型（LLM）在三个肿瘤基因组解读任务上的表现：区分肿瘤与非肿瘤突变、驱动与乘客突变、推断癌症类型。结果表明，LLM在第一个任务上与特制模型相当，集成可提升性能；在分布外数据上LLM表现更优。结论是无需微调，LLM即可通过补充特制模型在临床基因组解读中发挥价值。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估通用大语言模型能否替代或增强特制预测器在肿瘤基因组解读中的能力。
method: 在三个难度递增的真实临床肿瘤基因组解读任务上，比较通用LLM和特制模型的性能，并尝试集成。
result: 在区分肿瘤与非肿瘤突变任务上通用LLM与特制模型相当；在推断癌症类型等分布外数据上LLM表现更优；集成可提升性能。
conclusion: 当前通用LLM无需微调即可通过补充特制模型在临床基因组解读中发挥作用。
---

## 摘要
通用大语言模型（LLMs）通过大规模语料库训练获得广泛知识，但LLMs能否取代或增强任务特定模型尚不清楚。我们在三个真实世界、临床重要的肿瘤基因组解读任务上评估了LLMs，按难度递增顺序：（i）区分肿瘤与非肿瘤突变（n=34,415个变异），（ii）区分驱动突变与乘客突变（n=13,469个变异），（iii）从跨检测方法和机构的肿瘤测序报告中推断癌症类型（n=102,791个样本）。最佳通用LLMs在任务（i）上表现与基准定制预测器相当。将定制模型与零样本LLMs集成提升了任务（i）和（ii）的性能。对于任务（iii），在分布外数据上，LLMs表现优于或补充了定制模型。无需微调，当前的LLMs已能通过为定制的最新预测器补充专业知识，在临床基因组解读中发挥作用。

## Abstract
General-purpose large language models (LLMs) are trained on large corpora to acquire broad knowledge, but whether LLMs can replace, or augment, task-specific models is unclear. We evaluated LLMs on three real-world, clinically important tumor genomic interpretation tasks, in order of increasing difficulty: (i) distinguishing tumor from non-tumor mutations (n=34,415 variants), (ii) distinguishing driver from passenger mutations (n=13,469 variants), and (iii) inferring cancer type from tumor sequencing reports across multiple assays and institutions (n=102,791 samples). The best general-purpose LLMs performed as well as the benchmark tailor-made predictor for task (i). Ensembling tailor-made models with zero-shot LLMs improved their performance for tasks (i) and (ii). For task (iii), LLMs outperformed or supplemented tailor-made models on out-of-distribution data. Without fine-tuning, current LLMs already can be useful in clinical genomic interpretation by adding complementary expertise to tailor-made, state-of-the-art predictors.