---
title: Generative Augmentation Reveals Previously Overlooked Signals in Transcriptomic Datasets
title_zh: 生成式增强揭示了转录组数据集中此前被忽视的信号
authors: "Sethi, T., Anand, A., Pratiti, M., Ali, S. Y., Kamra, S., Verma, S., Singh, S., Bajaj, T."
date: 2026-04-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.23.720348v1.full.pdf"
tags: ["query:cpath"]
score: 6.0
evidence: 转录组数据集的生成式增强与生物标志物发现
tldr: "针对转录组研究中样本量小（p >> n）导致生物标志物发现困难的问题，本文提出了 GeneLift 框架。该框架结合了生成式数据增强（特别是高斯混合模型 GMM）、稳定性测试和基于 PubMed 的生物学验证（BayesScore）。通过对 36 个微阵列数据集的测试，GeneLift 成功挖掘出原研究中被忽视的稳健基因信号，并得到了后续文献的证实，显著提升了小样本组学数据的分析效能。"
source: biorxiv
selection_source: fresh_fetch
motivation: 转录组研究常面临样本量极小而特征维度极高的问题，导致统计效能不足，难以发现可靠的生物标志物。
method: 开发了 GeneLift 框架，利用高斯混合模型进行数据增强，并结合稳定性感知签名发现及基于贝叶斯后验概率的生物学验证。
result: 实验表明 GMM 优于深度生成模型，且该方法识别出了原分析中遗漏的、具有生物学意义的候选基因，部分基因在多年后的研究中得到了证实。
conclusion: 生成式增强结合多源验证能有效提升小样本转录组数据的信号挖掘能力，为生物标志物发现提供了新工具。
---

## 摘要
从样本量较小的转录组研究中识别稳健的基因表达特征仍然是计算生物学中最持久的挑战之一。基因表达数据集拥有数千个特征，但仅有少量生物样本。这呈现了经典的 p >> n 不平衡问题，限制了统计效力，并使得发现可靠的生物标志物变得困难。在成像领域，生成模型（如 GAN、VAE 和扩散模型）在数据增强方面展示了广阔的应用前景，但它们在组学数据中的有效性尚未得到系统测试。更重要的是，现有的框架均未将合成数据生成、稳定性感知特征发现和多源生物学验证整合到一个单一的流程中。在这项工作中，我们提出了 GeneLift，其假设是：将生成式数据增强、稳定性测试和生物学证据评估相结合的计算流程，将有助于在小队列转录组研究中发现新的基因特征。我们在涵盖五种疾病（脓毒症、乳腺癌、卵巢癌、结核病和糖尿病）的 36 个微阵列数据集上测试了这一假设。对 GeneLift 的组件测试表明，高斯混合模型（GMM）的表现优于深度生成方法，并能忠实地重现基因水平的分布。通过一种滴定增强水平的新方法，我们识别出了在原始效力不足的分析中未出现的具有生物学意义的候选基因。我们还开发了 BayesScore，这是一种根据 PubMed 共现情况计算的基因-疾病关联贝叶斯后验概率，它既能找回被标准差异表达分析遗漏的特征明确的疾病基因，也能发现其疾病相关性在随后的出版物中得到独立证实的候选基因，且从源数据集到首次疾病特异性引用之间的时间跨度长达 18 年。GeneLift 可在 tavlab-iiitd/GeneLift 免费获取。

## Abstract
Identifying robust gene expression signatures from transcriptomic studies with small sample sizes remains one of the most persistent challenges in computational biology. Gene expression datasets have thousands of features but only a handful of biological samples. This presents the classic p >> n imbalance, which limits statistical power and makes it difficult to discover reliable biomarkers. In imaging, generative models such as GANs, VAEs, and diffusion models have demonstrated promising applications in data augmentation, but their usefulness for omics data has not been systematically tested. More importantly, no existing framework integrates synthetic data generation, stability-aware signature discovery, and multi-source biological validation into a single pipeline.

In this work, we present GeneLift, with the hypothesis that a computational pipeline of generative data augmentation, stability testing, and evaluating biological evidence will aid novel gene-signature discovery in small-cohort transcriptomic studies. We tested this hypothesis across 36 microarray datasets covering five diseases: sepsis, breast cancer, ovarian cancer, tuberculosis, and diabetes. A component-wise testing of GeneLift revealed that Gaussian Mixture Models (GMMs) outperformed deep generative approaches and faithfully reproduced gene-level distributions. By a novel approach of titrating the level of augmentation, we identified biologically meaningful gene candidates that did not appear in the original, underpowered analyses. We also developed BayesScore, a Bayesian posterior probability of gene-disease association computed from PubMed co-occurrence, which both recovers well-characterised disease genes missed by standard differential expression and surfaces candidates whose disease relevance was independently confirmed in subsequent publications, with lead times of up to 18 years between the source dataset and the first disease-specific citation. GeneLift is freely available at tavlab-iiitd/GeneLift.

O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=103 SRC="FIGDIR/small/720348v1_ufig1.gif" ALT="Figure 1">
View larger version (41K):
org.highwire.dtl.DTLVardef@102b8aeorg.highwire.dtl.DTLVardef@1aacae7org.highwire.dtl.DTLVardef@1ef1f37org.highwire.dtl.DTLVardef@1ea8515_HPS_FORMAT_FIGEXP  M_FIG C_FIG