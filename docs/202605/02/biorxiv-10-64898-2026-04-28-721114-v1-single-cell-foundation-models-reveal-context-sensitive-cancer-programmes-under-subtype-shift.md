---
title: Single-cell foundation models reveal context-sensitive cancer programmes under subtype shift
title_zh: 单细胞基础模型揭示亚型偏移下的上下文敏感癌症程序
authors: "Wallace, J., Youssef, G., Han, N."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721114v1.full.pdf"
tags: ["query:cpath"]
score: 7.0
evidence: 用于亚型偏移下癌症程序的单细胞基础模型
tldr: 本研究探讨了单细胞基础模型（scFMs）在癌症亚型偏移下的表现。通过微调Geneformer和scGPT并与LightGBM对比，发现scFMs在处理罕见或未见癌症亚型时具有显著的泛化优势。结合可解释性分析，研究证明了微调后的模型能捕捉上下文敏感的生物学程序，而非简单重复训练规则，为跨域单细胞癌症分析提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究单细胞基础模型在零样本任务中表现不佳是源于其内在缺陷，还是因为缺乏特定任务的微调适配。
method: 在多种癌症数据集上微调Geneformer和scGPT，并利用集成梯度等技术分析其在处理未知亚型时的泛化能力与生物学相关性。
result: 在跨亚型泛化测试中，微调后的基础模型在罕见癌症亚型上的表现显著优于LightGBM，并展现出更强的上下文敏感性。
conclusion: 微调后的单细胞基础模型能有效应对癌症分析中的领域偏移，且可解释性分析有助于区分生物学适应与僵化的规则重用。
---

## 摘要
单细胞基础模型 (scFMs) 在作为细胞状态的可迁移表征方面展现出潜力，但最近的零样本评估表明，它们并不总是优于更简单的基准模型。我们探究了这种明显的局限性是反映了 scFMs 的内在弱点，还是反映了在没有特定任务适配的情况下使用它们的困难。为了测试这一点，我们在来自肾癌、肺癌和乳腺癌的常见肿瘤亚型上微调了两个广泛使用的 scFMs（Geneformer 和 scGPT），并在域内验证队列以及域外更罕见、未见的癌症亚型上将它们与 LightGBM 基准进行了比较。在所有三个器官中，这些模型都实现了近乎完美的域内判别（AUROC 0.98-1.00），但在亚型偏移下出现了差异。在肾嫌色细胞癌 (chromophobe RCC) 上，scGPT 和 Geneformer 的 AUROC 分别达到 0.88 和 0.92，而 LightGBM 为 0.64；在小细胞肺癌 (SCLC) 上，Geneformer 达到 1.00，而 LightGBM 为 0.82；在三阴性乳腺癌 (TNBC) 上，scGPT 达到 0.80，而 LightGBM 为 0.49。为了确定这种泛化是否反映了有意义的适配而非任意的特征漂移，我们对微调后的 scFMs 应用了可解释性技术集成梯度 (Integrated Gradients)，并对 LightGBM 应用了 SHAP。LightGBM 在不同数据集上表现出高度稳定的基因重要性排名，而基础模型则表现出显著更强的上下文敏感性。然而，这种灵活性并非随机的：所有模型都收敛于一个共享的域内核心，而 scFMs 在迁移过程中获得了更大的罕见亚型特异性基因集和通路程序。通路富集分析进一步支持了这些归因基因的生物学相关性。总之，这些结果表明，微调后的 scFMs 可以弥合癌症单细胞分析中具有临床相关性的领域偏移，并且可解释性为区分具有生物学依据的适配与对训练期规则的僵化重用提供了一条实用路径。

## Abstract
Single-cell foundation models (scFMs) have shown promise as transferable representations of cellular state, but recent zero-shot evaluations suggest that they do not consistently outperform simpler baselines. We asked whether this apparent limitation reflects an intrinsic weakness of scFMs or instead the difficulty of using them without task-specific adaptation. To test this, we fine-tuned two widely used scFMs, Geneformer and scGPT, on common tumour subtypes from renal, lung, and breast cancer, and compared them with a LightGBM baseline on within-domain validation cohorts and on out-of-domain rarer, unseen cancer subtypes. Across all three organs, the models achieved near-perfect within-domain discrimination (AUROC 0.98-1.00), but differences emerged under subtype shift. On chromophobe RCC, scGPT and Geneformer achieved AUROC 0.88 and 0.92 respectively versus 0.64 for LightGBM; on SCLC, Geneformer reached 1.00 versus 0.82 for LightGBM; and on TNBC, scGPT achieved 0.80 versus 0.49 for LightGBM. To determine whether this generalisation reflected meaningful adaptation rather than arbitrary feature drift, we applied Integrated Gradients, an interpretability technique, to the fine-tuned scFMs and SHAP to LightGBM. LightGBM showed highly stable gene-importance rankings across datasets, whereas the foundation models were substantially more context-sensitive. However, this flexibility was not random: all models converged on a shared within-domain core, while scFMs acquired larger rare-subtype-specific gene sets and pathway programmes during transfer. Pathway enrichment further supported the biological relevance of these attributed genes. Together, these results suggest that fine-tuned scFMs can bridge clinically relevant domain shifts in cancer single-cell analysis and that interpretability provides a practical route to distinguishing biologically grounded adaptation from rigid reuse of training-era rules.